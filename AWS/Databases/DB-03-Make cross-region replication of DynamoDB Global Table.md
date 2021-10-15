## Make cross-region replication of DynamoDB Global Table  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/137344800-5268858a-c3ba-4e1d-bad6-84cc0dd3e811.png)  
#### 1. On AWS console, click on `DynamoDB` under Database   
---
![image](https://user-images.githubusercontent.com/40828825/137344820-db5e3faf-c6be-40fe-8ff1-09e159f0a6b1.png)  
#### 2. Click on `Create table`  
---
![image](https://user-images.githubusercontent.com/40828825/137344842-c773f6c5-498a-456f-9e3f-d8f33cfc132c.png) 
#### 3. Enter table name  
#### 4. Enter primary key 
#### 5. Use default settings 
#### 6. Scroll down 
---
![image](https://user-images.githubusercontent.com/40828825/137344865-cfb4ab88-ac74-4d10-b0b4-3971767d2139.png)  
#### 7. Enter tag  
#### 8. Click on `Create`  
---
![image](https://user-images.githubusercontent.com/40828825/137344897-65867b7b-d492-4bb9-89de-5d04a351cfc0.png)  
#### 9. Click on `Items`  
#### 10. Click on `Create item` 
---
![image](https://user-images.githubusercontent.com/40828825/137344925-50b1e417-fbca-4f90-982d-9ce662c60682.png) 
#### 11. Enter id value (_1_)  
#### 12. Click on `+` 
#### 13. Click on `Append` 
#### 14. Choose _String_ 
---
![image](https://user-images.githubusercontent.com/40828825/137344949-1b632cd6-1222-4d46-8e0a-23a4553fdf3a.png) 
#### 15. Enter key (_message_)  
#### 16. Enter value (_Hello_) 
#### 17. Click on `Save`  
---
![image](https://user-images.githubusercontent.com/40828825/137344982-bd04c826-9bb6-40aa-94c4-a37b18810e87.png) 
#### 18. Click on `Global Tables`  
#### 19. Click on `Enable streams`  
---
![image](https://user-images.githubusercontent.com/40828825/137345005-73c23d22-8b02-4043-8e85-5dcbb75a4fea.png)
#### 20. Click on `Enable`   
---
![image](https://user-images.githubusercontent.com/40828825/137345024-b3bdc49e-c5ab-4e63-9bb2-267f9320daf6.png)
#### 21. Click on `Add region`  
---
![image](https://user-images.githubusercontent.com/40828825/137345044-4eaeb825-10d3-4bfe-b599-e2c180d3d981.png) 
#### 22. Choose region (_US East Ohio_)  
#### 23. Click on `Create replica` 
---
![image](https://user-images.githubusercontent.com/40828825/137345075-36532e2d-0a06-4bc7-a2ec-a7150ae2960b.png) 
#### 24. Click on `Capacity`  
#### 25. Click on `Read capacity and Write capacity` 
#### 26. Click on `Save`  
---
![image](https://user-images.githubusercontent.com/40828825/137345115-e6ce2edd-c0a4-4b44-924c-dcbfd986150c.png) 
#### 27. Click on `Close`   
---
![image](https://user-images.githubusercontent.com/40828825/137345191-050e32f4-8d3b-4242-9310-988a7f61ccc4.png) 
#### 28. Click on `Items`  
#### 29. Click on `Create item`  
---
![image](https://user-images.githubusercontent.com/40828825/137345222-d9532bae-a3fa-42a1-be02-71c33ef7c2cc.png) 
#### 30. Enter new item (_message: cloud_)  
#### 31. Click on `Save` 
---
![image](https://user-images.githubusercontent.com/40828825/137345252-0e954695-9fcd-4a63-94b4-a521f41f7ffd.png) 
#### 32. Go to other region of replication (_Ohio_)  
#### 33. Click on `Refresh` 
#### 34. Check the table also updated  
---

