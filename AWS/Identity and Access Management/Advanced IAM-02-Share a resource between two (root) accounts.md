## Share a resource between two (root) accounts  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/136244202-9df41261-fb89-45f6-9d75-3383e8acf0e1.png)
#### 1. Create a PostgreSQL-compatible Aurora with provisioned instance as described in the above lab
---
![image](https://user-images.githubusercontent.com/40828825/136244401-d29262cb-8fc6-48e9-898f-adc5dd32108c.png)
#### 2. Click on `Resource Access Manager` under Security, Identity & Compliance
---
![image](https://user-images.githubusercontent.com/40828825/136244579-29d50915-8555-48d7-a684-2cf7576113e0.png)
#### 3. Click on `Create a resource share`
---
![image](https://user-images.githubusercontent.com/40828825/136244643-733fd95a-3f67-4225-83cb-2e6a591b3239.png)
#### 4. Enter name (aurora-db-cluster)
#### 5. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/136244754-e5f4a8f0-5e05-4f19-8b8e-7cf21b003364.png)
#### 6. Select resource type (Aurora DB Clusters)
#### 7. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/136244882-bdf4e7a7-679b-4c15-95b0-61a9e23cef54.png)
#### 8. Keep "Allow external accounts" checked
#### 9. Enter the account ID of the user that we want to share the resource with
#### 10. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/136245043-ae30199f-71bd-437c-a04d-c862d4ed7433.png)
#### 11. Enter tag(s)
#### 12. Click on `Create resource share`
---
![image](https://user-images.githubusercontent.com/40828825/136245116-c8233ba2-c7f3-40ea-8b44-dc4f735c6257.png)
#### 13. On the other account, go to Resource Access Manager page
#### 14. Click on `Resource shares` under Shared with me on the left pane
---
![image](https://user-images.githubusercontent.com/40828825/136245255-59d076fc-7f90-4ac0-902c-9dbf4bbf6352.png)
#### 15. Click on the resource (aurora-db-cluster)
---
![image](https://user-images.githubusercontent.com/40828825/136245334-6ed76615-9a80-4d0b-b1c0-4b6a8c5c296f.png)
#### 16. Click on `Accept` resource share
---
![image](https://user-images.githubusercontent.com/40828825/136245401-3bc6d72e-8df3-4ff7-b83c-5c9a63a94731.png)
#### 17. Click on `OK`
---
![image](https://user-images.githubusercontent.com/40828825/136245456-f61d6748-be59-49e9-ba6a-81de054dec3a.png)
#### 18. As the invited account owner (root account), click on `RDS` in the AWS console
---
![image](https://user-images.githubusercontent.com/40828825/136245521-566e2c20-dcc9-4db8-8669-f7a80a5e2822.png)
#### 19. Click on `Databases` on the left pane
---
![image](https://user-images.githubusercontent.com/40828825/136245570-ae53ffae-bdb4-4d52-9706-b177ceae9121.png)
#### 20. Select the resource (databaseone)
#### 21. Click on `Actions`
#### 22. Click on `Create clone` to create a standalone database in the account (optional)
---
![image](https://user-images.githubusercontent.com/40828825/136245696-a305749f-5dca-4c4b-893e-da2a95429ad1.png)
#### 23. Go back to Resource Account Manager page
#### 24. Click on `Resource shares` under Shared with me on the left pane
#### 25. Select the resource (aurora-db-cluster)
#### 26. Click on `Leave resource share`
---
![image](https://user-images.githubusercontent.com/40828825/136245867-5091c417-3477-45b4-b69d-5993b3b34ae5.png)
#### 27. Click on `Leave`
