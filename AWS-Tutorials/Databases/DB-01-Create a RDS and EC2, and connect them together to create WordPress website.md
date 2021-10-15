## Create a RDS and EC2, and connect them together to create WordPress website  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/137319882-092a1263-3adc-405e-9e3a-34f630a9b3f6.png) 
#### 1. On AWS console, click on `RDS` under Database  
---
![image](https://user-images.githubusercontent.com/40828825/137319906-8fd04c05-40ab-48b0-bff7-0ded1868ade9.png) 
#### 2. Click on `Create database`  
---
![image](https://user-images.githubusercontent.com/40828825/137319935-98f858fe-260b-4ff3-8a41-e53588b37639.png)  
#### 3. Choose a database creation method (_Standard Create_)  
#### 4. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137319962-a18bb310-707c-4336-bb6d-24ca2e005c0d.png)  
#### 5. Choose an engine (_MySQL_)  
#### 6. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137319997-3dc28c08-b36c-4c98-99d3-12c65255d919.png)  
#### 7. Choose a template (_Free tier_)  
#### 8. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137320033-f2a2c29e-413e-4ffc-8561-0d403e1f7b19.png) 
#### 9. Enter DB instance identifier  
#### 10. Enter master username
#### 11. Enter master password
#### 12. Confirm password
#### 13. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137320067-9fcea252-daf3-404a-b52e-d914ae0b8938.png) 
#### 14. Select DB instance class (_Burstable_)  
#### 15. Choose AMI (_db.t2.micro_)
#### 16. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137320099-730ca693-4c11-4036-8631-cf992979ce3f.png) 
#### 17. Leave as default  
#### 18. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137320129-e00bfda2-bf3e-4735-9780-5a46211c1be6.png) 
#### 19. Choose VPC (_default_)  
#### 20. Choose subnet group (_default; should be a private subnet group_) [A group of subnets is created on RDS page]
#### 21. Choose public access (_No_) [To access the database from outside the VPC, choose public access Yes]
#### 22. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137320157-a0907a9f-a7e0-4901-bcad-95e8d25101cd.png)  
#### 23. Choose VPC security group (_default_)  
#### 24. Choose availability zone for RDS (_No preference_)
#### 25. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137320182-8e4f1f78-8344-4148-8e4b-61f33038f4d2.png)
#### 26. Enter database name 
#### 27. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137320212-3dd8f947-b6b8-474b-a4f7-c14d7779c9f4.png)
#### 28. Enable automatic backups  
#### 29. Set backup retention period as 0 days
#### 30. Set backup window (_No preference_)
#### 31. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137320234-de992a8b-3980-4bb0-97ae-da91edf1d52e.png) 
#### 32. Select maintenance window (_Select window_)  
#### 33. Set window
#### 34. Disable _deletion protection_
#### 35. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137320252-c827c136-e5b1-4efe-8446-86db87d81a31.png) 
#### 36. Click on `Create database`  
---
![image](https://user-images.githubusercontent.com/40828825/137320306-7c841338-dc3f-4720-be1e-c7520aca25e0.png)
#### 37. Launch an EC2 instance as in the above lab with exception described below  
---
```
#!/bin/bash
yum install httpd php php-mysql -y
cd /var/www/html
wget https://wordpress.org/wordpress-5.1.1.tar.gz
tar -xzf wordpress-5.1.1.tar.gz
cp -r wordpress/* /var/www/html/
rm -rf wordpress
rm -rf wordpress-5.1.1.tar.gz
chmod -R 755 wp-content
chown -R apache:apache wp-content
service httpd start
chkconfig httpd on
```
#### 38. In Step 3: Configure Instance Details, enter the above code  
---
![image](https://user-images.githubusercontent.com/40828825/137320385-47bef572-37f8-43d0-9540-82939d83e232.png) 
#### 39. In Step 3: Configure Instance Details, enter the above code  
#### 40. Click on `Next`
#### 41. Click on `Launch`
---
![image](https://user-images.githubusercontent.com/40828825/137320412-8a1c86cf-e8aa-41f0-b540-c59a9f7c4fc0.png)
#### 42. Click on `Security Groups` on the left pane  
---
![image](https://user-images.githubusercontent.com/40828825/137320428-861440ec-30f2-45ca-8327-4eff54cd93bf.png) 
#### 43. Click on the security group that we set for the RDS database  
---
![image](https://user-images.githubusercontent.com/40828825/137320446-4d881dad-486e-44b3-ba15-6df381767dff.png) 
#### 44. Click on `Inbound rules`  
#### 45. Click on `Edit inbound rules`
---
![image](https://user-images.githubusercontent.com/40828825/137320470-16b2740d-bf9f-40d0-8d3a-1e2897546808.png)  
#### 46. Click on `Add rule`  
#### 47. Select the type of traffic (_MYSQL/Aurora with port 3306_)
#### 48. Select the source (_security group for the EC2 instance launched_)
#### 49. Click on `Save rules`
---
![image](https://user-images.githubusercontent.com/40828825/137333516-b5198918-3c6e-4240-bbb1-b9ae5626fff4.png) 
#### 50. To access the database from outside the VPC, click on Add rule  
#### 51. Select the type of traffic (_PostgreSQL with port 5432_)
#### 52. Select the source (_My IP for this example_)
#### 53. Click on `Save rules`
---
![image](https://user-images.githubusercontent.com/40828825/137320518-24ac14cc-662a-4229-ad78-4f50dc0dca3f.png)
#### 54. Go to EC2 instance page  
#### 55. Select the EC2 instance we launched
#### 56. Click on `Details`
#### 57. Copy the public IP address
---
![image](https://user-images.githubusercontent.com/40828825/137320537-81c09c0c-f53d-493b-9501-0044c4f690c2.png) 
#### 58. Paste the public IP address in URL  
---
![image](https://user-images.githubusercontent.com/40828825/137320564-17b52caf-2be4-48f2-8806-9a54bde4eee7.png)  
#### 59. Click on `Let's go!`  
---
![image](https://user-images.githubusercontent.com/40828825/137320592-0787704b-6a03-440a-b02c-0cd55bf65fbe.png)  
#### 60. Go to RDS page  
#### 61. Select the database we created
#### 62. Click on `Connectivity & security`
#### 63. Copy the endpoint
---
![image](https://user-images.githubusercontent.com/40828825/137320619-5c5f7eb1-3d08-44a0-8324-f9d7dc94268a.png) 
#### 64. Paste the endpoint in _Database Host_  
#### 65. Enter _Database Name_
#### 66. Enter _Username_
#### 67. Enter _Password_
#### 68. Click on `Submit`
---
![image](https://user-images.githubusercontent.com/40828825/137320641-f02e21fc-730e-4ad8-989b-a37c4dbaa5ae.png)  
#### 69. Copy the selected text  
---
```
Hasan-iMac:SSH hsa$ ssh ec2-user@34.243.250.252 -i IreKP.pem 
The authenticity of host '34.243.250.252 (34.243.250.252)' can't be established.
ECDSA key fingerprint is SHA256:quTialRQ+Ed+G1M++GifgiDWDre5vVq/UGXj1Q5LBNg.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '34.243.250.252' (ECDSA) to the list of known hosts.

       __|  __|_  )
       _|  (     /   Amazon Linux 2 AMI
      ___|\___|___|

https://aws.amazon.com/amazon-linux-2/
7 package(s) needed for security, out of 14 available
Run "sudo yum update" to apply all updates.
-bash: warning: setlocale: LC_CTYPE: cannot change locale (UTF-8): No such file or directory
[ec2-user@ip-172-31-34-134 ~]$ sudo su
[root@ip-172-31-34-134 ec2-user]# cd /var/www/html
[root@ip-172-31-34-134 html]# nano wp-config.php
[root@ip-172-31-34-134 html]# 
```
#### 70. SSH into the EC2 instance by typing the above code  
#### 71. Go to the nano editor _wp-config.php_ file
---
![image](https://user-images.githubusercontent.com/40828825/137320748-f0613b42-fff5-4741-9e12-31e2fb792dee.png)  
#### 72. Paste the text in the nano editor _wp-config.php_ file  
#### 73. Press `Ctrl X`
#### 74. Press `Y`
#### 75. Click `Enter`
---
```
<?php
/**
 * The base configuration for WordPress
 *
 * The wp-config.php creation script uses this file during the
 * installation. You don't have to use the web site, you can
 * copy this file to "wp-config.php" and fill in the values.
 *
 * This file contains the following configurations:
 *
 * * MySQL settings
 * * Secret keys
 * * Database table prefix
 * * ABSPATH
 *
 * @link https://codex.wordpress.org/Editing_wp-config.php
 *
 * @package WordPress
 */

// ** MySQL settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define( 'DB_NAME', 'RDSOne' );

/** MySQL database username */
define( 'DB_USER', 'rdsadmin123' );

/** MySQL database password */
define( 'DB_PASSWORD', 'rdsadmin123' );

/** MySQL hostname */
define( 'DB_HOST', 'rdsone.ctvj4m1nbr0j.eu-west-1.rds.amazonaws.com' );

/** Database Charset to use in creating database tables. */
define( 'DB_CHARSET', 'utf8mb4' );

/** The Database Collate type. Don't change this if in doubt. */
define( 'DB_COLLATE', '' );

/**#@+
 * Authentication Unique Keys and Salts.
 *
 * Change these to different unique phrases!
 * You can generate these using the {@link https://api.wordpress.org/secret-key/1.1/salt/ WordPress.org secret-key service}
 * You can change these at any point in time to invalidate all existing cookies. This will force all users to have to log in again.
 *
 * @since 2.6.0
 */
define( 'AUTH_KEY','ll_zVK.4hnvyQ16~*`H8d6JJ4Jcl1+]>sMn[G!>:OpXvtl`OtN4aLE0p[Nb7Gq2m' );
define( 'SECURE_AUTH_KEY',  'gZ7GPL1Y}y]5I2I7W*|P*oW#@XdA}A;3f$P1gy|C]YPL#Y/EkwSDX.R*lQQcsy-5' );
define( 'LOGGED_IN_KEY',    'A6`m/m<F:?is(6.$%XDa65LIXu9Lo6PNB#c>LIHc*W7e`Hnql9?7wyEnW>V+%oWv' );
define( 'NONCE_KEY','6l{pAf.|I`5Q2j/oC3H=(MjvtFvX#q<_1cSgYSIP07a8yN-wSs HN4g/ac<O?e V' );
define( 'AUTH_SALT','A,R,QKWFDccf3 `uITZp%p}hk|10yq+`ERsIgG-6!z+<gg35@#5Z,sZBzye3h0Q6' );
define( 'SECURE_AUTH_SALT', 'iOBax~k^}C,H8wM;hab)WZ*u%[a,7ABZOu8auTL|4@~-sY$q.Xpa%-Q~4C_:8$*c' );
define( 'LOGGED_IN_SALT',   ';s)Vm&</KXcv6/sDZgXeXHRkwG-RSX&7079RCQ:W](LL?>=7.M]tGRqDcnYT$mkx' );
define( 'NONCE_SALT','@C[ ZZwi<ZJC%ONqs(Z5y*xkIWcZ3xqP@q#QJLhY5AtwC&V-mjcb]h&BqN`,h8DI' );

/**#@-*/

/**
 * WordPress Database Table prefix.
 *
 * You can have multiple installations in one database if you give each
* a unique prefix. Only numbers, letters, and underscores please!
 */
$table_prefix = 'wp_';

/**
 * For developers: WordPress debugging mode.
 *
 * Change this to true to enable the display of notices during development.
 * It is strongly recommended that plugin and theme developers use WP_DEBUG
 * in their development environments.
 *
 * For information on other constants that can be used for debugging,
 * visit the Codex.
 *
 * @link https://codex.wordpress.org/Debugging_in_WordPress
 */
define( 'WP_DEBUG', false );

/* That's all, stop editing! Happy publishing. */

/** Absolute path to the WordPress directory. */
if ( ! defined( 'ABSPATH' ) ) {
define( 'ABSPATH', dirname( __FILE__ ) . '/' );
}

/** Sets up WordPress vars and included files. */
require_once( ABSPATH . 'wp-settings.php' );
```
#### 76. Paste the above text in the nano editor _wp-config.php_ file  
---
![image](https://user-images.githubusercontent.com/40828825/137321565-f5af8780-18bc-498f-8ac1-4325b68e5b5b.png)  
#### 77. Go to WordPress page  
#### 78. Click on `Run the installation`
---
![image](https://user-images.githubusercontent.com/40828825/137333623-5a9e0061-22cd-4449-b9f4-cba7f917a89f.png)
#### 79. Set title (_Hello_)  
#### 80. Enter _Username_
#### 81. Enter _Password_
#### 82. Confirm password
#### 83. Enter _your email_
#### 84. Click on `Install WordPress`
---
![image](https://user-images.githubusercontent.com/40828825/137321638-d367b6de-d615-4b40-ace6-50e7b38adeb3.png)  
#### 85. Click on `Log In`  
---
![image](https://user-images.githubusercontent.com/40828825/137321666-43684779-be89-441d-86df-292e48a68ad9.png)
#### 86. Enter _Username_  
#### 87. Enter _Password_
#### 88. Click on `Log In`
---
