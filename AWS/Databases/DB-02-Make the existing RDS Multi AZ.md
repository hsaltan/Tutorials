## Make the existing RDS Multi AZ  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/137339001-005b2ab4-fc77-41b7-a00f-3f8072448d39.png)  
#### 1. On AWS console, click on `RDS` under Database  
---
![image](https://user-images.githubusercontent.com/40828825/137339022-e39c02a0-2cf3-4d5b-af0c-c354f4186cfa.png)  
#### 1. Click on `Databases` on the left pane  
---
![image](https://user-images.githubusercontent.com/40828825/137339053-a87e0fa7-d685-4100-a4b2-538cc88a4ac6.png)  
#### 1. Choose the database  
#### 1. Click on `Modify`
---
![image](https://user-images.githubusercontent.com/40828825/137339075-dcc4daea-7455-497e-8d50-de2e54cc9e11.png)  
#### 1. Choose _Yes_ under Multi-AZ deployment  
#### 1. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137339103-e5d2818f-4782-4d87-a70e-ce283480fc69.png)  
#### 1. Click on `Continue`  
---
![image](https://user-images.githubusercontent.com/40828825/137339137-731c4e0e-3e1f-4f3f-b857-dda6cb956ac1.png)  
#### 1. Choose _Apply immediately_  
#### 1. Click on `Modify DB Instance`
---
![image](https://user-images.githubusercontent.com/40828825/137339159-c5cb08ad-a2ff-411d-8d33-0b7e0c4b286c.png) 
#### 1. Choose the database  
#### 1. Click on `Modify`
---
![image](https://user-images.githubusercontent.com/40828825/137339189-9afb5496-8054-42c6-ac89-3a31f86bee0b.png)  
#### 1. Set backup retention period to a positive number (_14 days_)  
#### 1. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137339215-9ac73b1c-68df-4d83-99f3-b7da3f0841c7.png)  
#### 1. Click on `Continue`  
---
![image](https://user-images.githubusercontent.com/40828825/137339244-893da0f6-b037-42a1-bc1b-18b3b760f051.png)  
#### 1. Choose _Apply immediately_  
#### 1. Click on `Modify DB Instance`
---
![image](https://user-images.githubusercontent.com/40828825/137339273-aacd538b-b80e-4a20-9c21-dbaf1700416a.png)  
#### 1. Refresh the web page  
#### 1. Choose the database
#### 1. Click on `Actions`
#### 1. Click on `Create read replica`
---
![image](https://user-images.githubusercontent.com/40828825/137339300-5626cf42-ffd2-46e6-be11-25a9db7121b3.png)  
#### 1. Leave as default  
#### 1. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137339324-f386d519-8ef4-4351-83e1-da85c36ccffa.png)  
#### 1. Choose the destination region for the read replica (_keep the same region_)  
#### 1. Choose public accessibility (_No_)
#### 1. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137339357-cb958e95-e5d8-4edc-8088-e24de8e51949.png)  
#### 1. Set DB instance identifier  
#### 1. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137339378-dbcf080e-23d2-4c1f-bbe9-ae92142b7685.png)  
#### 1. Leave everything else as default  
#### 1. Click on `Create read replica`
---
![image](https://user-images.githubusercontent.com/40828825/137339406-7f0b90c3-d7a3-405d-b912-3700d437085e.png)  
#### 1. Choose the read replica  
#### 1. Click on `Actions`
#### 1. Click on `Promote`
---
![image](https://user-images.githubusercontent.com/40828825/137339443-d36aa704-98a4-444d-bcf2-809284863f0d.png)  
#### 1. Enable automatic backups as default  
#### 1. Set backup retention period as default (_1_)
#### 1. Click on `Continue`
---
![image](https://user-images.githubusercontent.com/40828825/137342354-6f58d107-19fd-4a25-9550-747a34f6632c.png)
#### 1. Click on `Promote Read Replica` 
---
![image](https://user-images.githubusercontent.com/40828825/137339722-7a70e105-b3b3-4adb-8251-ebe6e3f65d95.png)  
#### 1. Click on the database that we want to take a snapshot  
---
![image](https://user-images.githubusercontent.com/40828825/137339759-813a47dc-7dc4-40e3-91c6-43acb30d6c96.png)  
#### 1. Click on `Maintenance & backups`  
#### 1. Scroll down 
---
![image](https://user-images.githubusercontent.com/40828825/137339789-bd44cac2-0da2-485f-b157-6786c94e56b9.png)  
#### 1. Click on `Take snapshot`
---
![image](https://user-images.githubusercontent.com/40828825/137339827-1a9fc4d3-1d9c-4886-80fc-af06910fd102.png)  
#### 1. Enter a snapshot name  
#### 1. Click on `Take Snapshot`
---

