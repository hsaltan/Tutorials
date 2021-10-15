## Launch a Windows-based EC2 instance in Microsoft AD  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/136253899-64d4520f-1446-48d5-b398-be671110b03e.png)  
#### 1. Click on `IAM` under Security, Identity & Compliance  
---
![image](https://user-images.githubusercontent.com/40828825/136253931-4935f3f9-3a30-4cc3-814a-2b174986dc0c.png)  
#### 2. Click on `Roles` on the left pane  
#### 3. Click on `Create role`   
---
![image](https://user-images.githubusercontent.com/40828825/136253957-09401e1b-4ed6-42d2-8d4c-84be8c4b82d7.png)  
#### 4. Click on `AWS service`  
#### 5. Click on `EC2` as use case  
#### 6. Click on `Next`   
---
![image](https://user-images.githubusercontent.com/40828825/136253980-eb7b5f4f-3722-4dd1-a4f1-eb27b6a858c2.png)  
#### 7. Select the above policies 
#### 8. Click on `Next`   
---
![image](https://user-images.githubusercontent.com/40828825/136254002-69f4c333-d626-4014-a461-697cc3e01137.png)  
#### 9. Enter tag(s) 
#### 10. Click on `Next`  
---
![image](https://user-images.githubusercontent.com/40828825/136254028-ddc04725-48f2-4ea7-9309-8f506595d8cf.png)  
#### 11. Enter role name  
#### 12. Enter description  
#### 13. Click on `Create role`  
---
![image](https://user-images.githubusercontent.com/40828825/136254092-664b2934-97d1-4bed-af20-72f956ac0100.png)  
#### 14. Launch an EC2 instance as described in the above lab with exceptions shown below   
---
![image](https://user-images.githubusercontent.com/40828825/136254122-d68ccd9c-e63f-43a2-be0b-01bcdfd80536.png)  
#### 15. Select a Windows AMI 
---
![image](https://user-images.githubusercontent.com/40828825/136254177-f88ab40b-510c-4ea4-916f-25a50ebddd26.png)  
#### 16. Create a AWS Managed Microsoft AD as described in the above lab   
---
![image](https://user-images.githubusercontent.com/40828825/136254217-7fdba715-3b17-4ee1-9b1d-7728384b122a.png)  
#### 17. Choose domain join directory (corp.adexample.com)  
#### 18. Choose IAM role (DemoDirectoryServiceRole)  
#### 19. Click on `Next`   
---
![image](https://user-images.githubusercontent.com/40828825/136254261-c8d85309-e8c2-4304-8a71-78ba802fa33b.png)  
#### 20. Enter tag(s)  
#### 21. Click on `Next`    
---
![image](https://user-images.githubusercontent.com/40828825/136254294-5148ad80-985e-43b2-9b74-1a0bbfe0e3a4.png)  
#### 22. Select the security group  
#### 23. Click on `Review and Launch`    
---
![image](https://user-images.githubusercontent.com/40828825/136254328-8452b4f6-4481-4d4d-b06e-2f77de274431.png)  
#### 24. Click on `Security Groups`    
---
![image](https://user-images.githubusercontent.com/40828825/136254353-13d360f1-246b-4e4a-98e1-248b0187e6b9.png)  
#### 25. Select the security group  
#### 26. Click on `Inbound rules`  
#### 27. Click on `Edit inbound rules`    
---
![image](https://user-images.githubusercontent.com/40828825/136254395-27d0c45c-4d49-480a-bb06-ebc39ef263cd.png)  
#### 28. Click on `Add rule`  
#### 29. Select type of traffic (RDP)  
#### 30. Select source (0.0.0.0/0)  
#### 31. Click on `Save rules`  
---
