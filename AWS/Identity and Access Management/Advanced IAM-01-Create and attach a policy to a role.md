## Create and attach a policy to a role  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/136229060-bc2156a9-81c5-4352-984b-dd76566084fc.png)  
#### 1. On AWS console, click on `IAM` under Security, Identity & Compliance  
---
![image](https://user-images.githubusercontent.com/40828825/136229531-b9a8f6d5-14f9-411e-8fc4-47e4331dc55e.png)
#### 2. Click on `Policies` on the left pane
#### 3. Click on `Create policy`
---
![image](https://user-images.githubusercontent.com/40828825/136236380-5c3b05e4-ac5b-45df-8d09-04c61a4dce65.png)
#### 4. Type a policy as above
#### 5. Click on `Review policy`
---
![image](https://user-images.githubusercontent.com/40828825/136236624-72dbd5bf-9608-4d1f-aa6c-39c5ccddcd03.png)
#### 6. Enter name
#### 7. Enter description
#### 8. Click on `Create policy`
---
![image](https://user-images.githubusercontent.com/40828825/136236770-a9d9adbe-c168-47dd-ad0f-4ebfee550865.png)
#### 9. Click on `Roles` on the left pane
#### 10. Click on `Create role`
---
![image](https://user-images.githubusercontent.com/40828825/136236956-7f720376-6047-42c1-a820-c3daedb05228.png)
#### 11. Click on `AWS service`
---
![image](https://user-images.githubusercontent.com/40828825/136237164-8f8e64de-5f5b-403d-8026-48670721f7bf.png)
#### 12. Click on `CloudFormation`
#### 13. Click on `Next: Permissions`
---
![image](https://user-images.githubusercontent.com/40828825/136237304-6cb0cb90-92dc-424a-aede-3a8111ef4a84.png)
#### 14. Choose EC2Actions policy just created
#### 15. Click on `Next: Tags`
---
![image](https://user-images.githubusercontent.com/40828825/136237433-44fdbbc8-3f27-4f67-94ba-133c68debaea.png)
#### 16. Enter tag(s)
#### 17. Click on `Next: Review`
---
![image](https://user-images.githubusercontent.com/40828825/136237573-7fa3d7d5-74fa-4623-beac-87eb25948659.png)
#### 18. Enter role name
#### 19. Enter role description
#### 20. Click on `Create role`
---
![image](https://user-images.githubusercontent.com/40828825/136237743-7ae7ab8f-6e94-42f5-98f7-4bfccceebc5f.png)
#### 21. Click on `Roles` on the left pane
#### 22. Click on the role
---
![image](https://user-images.githubusercontent.com/40828825/136237858-d4d6fcd7-69b8-4852-96ca-f06519152d16.png)
#### 23. Click on `Attach policies`
---
![image](https://user-images.githubusercontent.com/40828825/136237956-b65648e8-acca-498a-82ac-00408a222ff1.png)
#### 24. Choose a new policy
#### 25. Click on `Attach policy`
---
![image](https://user-images.githubusercontent.com/40828825/136238081-c8be6290-c1ce-4698-99ff-c35325e0090c.png)
#### 26. Click on `Roles` on the left pane
#### 27. Click on the role
---
![image](https://user-images.githubusercontent.com/40828825/136238208-d7b5c00c-d252-46a3-a970-6149c5d4e166.png)
#### 28. Click on `Add inline policy`
---
![image](https://user-images.githubusercontent.com/40828825/136238296-423444e3-08db-4bb4-b390-df2f5f8a7cae.png)
#### 29. Type the code as above
#### 30. Click on `Review policy`
---
![image](https://user-images.githubusercontent.com/40828825/136238426-92872489-eb1d-4f71-8263-74eb057e353e.png)
#### 31. Enter name
#### 32. Click on `Create policy`
---
![image](https://user-images.githubusercontent.com/40828825/136238552-72f02dca-c8b1-4781-9170-2580b254ab52.png)
#### 33. See the inline policy created
---
![image](https://user-images.githubusercontent.com/40828825/136238625-5fc92093-f443-4d78-9698-e1f2ee15742b.png)
#### 34. Click on `Users` on the left pane
#### 35. Click on the user that we want to set permission boundary
---
![image](https://user-images.githubusercontent.com/40828825/136238755-f303e2f2-0caf-4d32-b9b8-f29565a4f73d.png)
#### 36. Click on `Permission boundary (not set)`
---
![image](https://user-images.githubusercontent.com/40828825/136238913-48e7a027-00de-4ec7-ac1b-7b28b49e1258.png)
#### 37. Click on `Set boundary`
---
![image](https://user-images.githubusercontent.com/40828825/136239000-7fc8838c-87d8-4283-af58-0359ef3a41b3.png)
#### 38. Choose the policy
#### 39. Click on `Set boundary`
---
![image](https://user-images.githubusercontent.com/40828825/136239121-48db428e-cde3-4699-99fc-161fead0ac5e.png)
#### 40. See the permission boundary created
---
![image](https://user-images.githubusercontent.com/40828825/136239222-2d71369d-98b7-494b-bf0b-1fa77149ac3c.png)
#### 41. Click on `Remove boundary` in the user page
---
![image](https://user-images.githubusercontent.com/40828825/136239325-270e3005-333e-4a61-9a3e-bd52772d0f1d.png)
#### 42. Click on `Remove`
