## Deploying a Flask application on Amazon Linux 2

1. Launch an Amazon Linux 2 EC2 instance on AWS.

2. SSH into the instance.

3. Update Linux:  
`sudo yum update –y`

4. Change the hostname of Amazon Linux instance:  
`sudo hostnamectl set-hostname APP-SERVER`

5. Change the permissions of host file:  
`sudo chmod a+w /etc/hosts`

6. Open the _/etc/hosts_ file and change the entry beginning with 127.0.0.1 substituting your own hostname:  
`127.0.0.1 APP-SERVER.localdomain APP-SERVER localhost4 localhost4.localdomain4`

7. Reboot the instance to pick up the new hostname:  
`sudo reboot`

8. Enhance privileges:  
`sudo su`

9. Add user:  
`sudo adduser USERNAME`

10. Sudo the new user:  
`sudo usermod -aG wheel USERNAME`

11. Change the security context to the new user:  
`sudo su - USERNAME`

12. Create a .ssh directory in the new user home directory:  
`mkdir .ssh`

13. Use the chmod command to change the .ssh directory's permissions:  
`chmod 700 .ssh`

14. Use the touch command to create the _authorized_keys_ file in the _.ssh_ directory:  
`touch .ssh/authorized_keys`

15. Use the chmod command to change the _.ssh/authorized_keys_ file permissions:  
`chmod 600 .ssh/authorized_keys`

16. Retrieve the public key for your key pair. On your local machine terminal type:  
`ssh-keygen -y -f /PATH_TO_KEY_PAIR/KEY_PAIR.pem`

17. Copy the public key returned by the above command.

18. On EC2 instance, run the following command:  
`cat >> .ssh/authorized_keys`

19. Paste the public key you copied and then press Enter.

20. Press and hold Ctrl+d to exit and return to the command line session.

21. Change and confirm password:  
`sudo passwd USERNAME`

22. Exit the command line session:  
`exit`

23. SSH back into the instance with the new user name:  
`ssh -i /PATH_TO_KEY_PAIR/KEY_PAIR.pem USERNAME@AMAZON_LINUX_PUBLIC_DNS_NAME`

24. Cancel root login to EC2:  
`sudo nano /etc/ssh/sshd_config`
Uncomment and change `PermitRootLogin` to `no`.  
Disable password authentication by uncommenting and changing `PasswordAuthentication` to `no`.

25. Restart _sshd_:  
`sudo systemctl restart sshd`

26. Copy flask app files from the local machine (Mac) to EC2 instance:  
`scp -i /PATH_TO_KEY_PAIR/KEY_PAIR.pem -r /LOCAL_PATH_TO_APP/APP USERNAME@AMAZON_LINUX_PUBLIC_DNS_NAME:~/`

27. Install python3:  
`sudo yum install python3-pip`

28. Create a virtual environment under the application folder:  
`python3 -m venv app/venv`

29. Activate the virtual environment:  
`cd app`<br>
`source venv/bin/activate`

30. Install all dependencies:  
`pip install -r requirements.txt`

31. Create environment variables on Linux:  
`sudo touch /etc/config.json`   
`sudo nano /etc/config.json`

32. Change the application config file
`sudo nano app/config.py`   
Use `config.get` to import environment variables from _/etc/config.json_

33. Install `email_validator` (for verifications by the app through email):  
`pip install email_validator`

34. Add `email_validator` to _forms.py_ in the app:  
`import email_validator`

35. Change the EC2 security group rules as below:  
<pre><code>
Inbound rules:  
Type 	Protocol 	Port range 	Source 			Description - optional  
HTTP	TCP		80		0.0.0.0/0		–  
SSH	TCP		22		LOCAL_IP/32		SSH ingress rule  
HTTPS	TCP		443		0.0.0.0/0		–  

Outbound rules:  
Type 		Protocol 	Port range 	Destination 	Description - optional  
All traffic	All		All		0.0.0.0/0	–  
</code></pre>

36. Install _nginx_ web server:  
`sudo yum install -y epel-release`  
`sudo yum install nginx -y`

37. Check _nginx_ version:  
`sudo nginx -v`

38. Start and enable _nginx_:  
`sudo systemctl start nginx`  
`sudo systemctl enable nginx`

39. Install _gunicorn_ web server:  
`pip install gunicorn`

40. Open _nginx_ configuration folder:  
`cd /etc/nginx/conf.d`

41. Create a configuration file for the application:  
`sudo touch app.conf`

42. Use the chmod command to change the _app.conf_ file permissions:  
`sudo chmod a+w app.conf`

43. Open the configuration file and add the confguration commands:  
`sudo nano app.conf`  
<pre><code>server {  
	listen 80;  
        server_name LINUX_IP_OR_APP_DOMAIN_NAME;  
        client_max_body_size 12m;  
        location /static {  
                alias /home/USERNAME/app/app/static;  
        }  

	location / {  
                proxy_pass http://localhost:8000;>  
                include /etc/nginx/fastcgi_params;  
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;  
                proxy_set_header Host $host;  
                proxy_redirect off;  
        }  
}  </code></pre>

44. Open _nginx.conf_ configuration file:  
`sudo nano /etc/nginx/nginx.conf`

45. Add the following line in `http` block:  
<pre><code>http {
    # ...
    client_body_temp_path /tmp 1 2; (Add this line only)
    # ...
}</code></pre>

46. In _nginx.conf_ file, change 'user nginx;' to 'user USERNAME;'  

47. Check if the _nginx.conf_ file syntax is ok:  
`sudo nginx -t`

48. Restart _nginx_:  
`sudo systemctl restart nginx`

49. Find out how many CPU cores exist on the Linux machine to calculate the number of worker processes needed in gunicorn:  
Number of worker processes = (2 * CPU core) + 1  
`proc --all`

50. Go to the directory where _run.py_ file exists and run (3 worker processes to run our app):  
`gunicorn -w 3 run:app`

51. Install _supervisor_ to autostart our app if it crashes:  
`sudo yum install supervisor`

52. Go to the folder where _supervisord.conf_ file exists:  
`cd /etc`

53. Use the chmod command to change the _supervisord.conf_ file permissions:  
`sudo chmod a+w supervisord.conf`

54. Open the _supervisord.conf_ file and add the following commands at the end of the file:  
<pre><code>
[program:app]  
directory=/home/USERNAME/app  
command=/home/USERNAME/app/venv/bin/python /home/USERNAME/app/venv/bin/gunicorn -w 3 run:app -b localhost:8000  
user=USERNAME  
autostart=true  
autorestart=true  
stopasgroup=true  
killasgroup=true  
stderr_logfile=/var/log/app/app.err.log  
stdout_logfile=/var/log/app/app.out.log  
</code></pre>

55. Create a log folder:  
`sudo mkdir -p /var/log/app`

56. Create output and error log files:  
`sudo touch /var/log/app/app.err.log`  
`sudo touch /var/log/app/app.out.log`  

57. Enable restart of _supervisord_ on reboot:  
`sudo systemctl enable supervisord`

58. Reload _supervisord_  
`sudo supervisorctl reload`

59. Check _supervisord_ if it runs successfully:  
`sudo systemctl status supervisord`

60. To allow our application to access our email (gmail) to send emails to those who have forgotten their passwords, take the following steps:
+ Sign in to Gmail  
+ Click on _Manage your Google Account_ on the top right (under the _Google Account_ icon)  
+ Choose _Security_ tab on the left  
+ Scroll down to access _Less secure app access_  
+ Next to _Allow less secure apps: OFF_, select the toggle switch to turn on.  
+ Visit the Display Unlock Captcha page <https://accounts.google.com/DisplayUnlockCaptcha> and click Continue to remove the security block.

You're all set!


