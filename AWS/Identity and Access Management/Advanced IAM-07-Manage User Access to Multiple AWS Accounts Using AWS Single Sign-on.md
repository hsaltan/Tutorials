## Manage User Access to Multiple AWS Accounts Using AWS Single Sign-on  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/136665208-e46ba968-8684-4b83-97ea-9448c7cf6e30.png)
#### 1. Click on `AWS Single Sign-On under Security, Identity & Compliance` on the AWS console    
---
![image](https://user-images.githubusercontent.com/40828825/136665217-f2c561f2-a970-4943-8e46-2ca6f46ede7d.png)
#### 2. Click on `Enable AWS SSO`  
---
![image](https://user-images.githubusercontent.com/40828825/136665221-0dc82ddf-4e12-4543-ba56-f3719183bf22.png)
#### 3. Click on `Create AWS organization`   
---
![image](https://user-images.githubusercontent.com/40828825/136665225-aeb8b2b2-8717-4aa1-b9e4-e4dd0e38db49.png)
#### 4. Click on `My Organization` under the account name   
---
![image](https://user-images.githubusercontent.com/40828825/136665229-5fd61749-e4f7-49ad-bbac-79f73002e06e.png)
#### 5. Click on `Add account`   
---
![image](https://user-images.githubusercontent.com/40828825/136665241-ac2b0fc7-f30d-413a-829e-38ffe0ea44bc.png)
#### 6. Click on `Invite account`  
---
![image](https://user-images.githubusercontent.com/40828825/136665244-d00f6e7d-a279-4e42-9e6d-66c7f6238f06.png)
#### 7. Enter email of the user that we want to invite (_invitee user_)  
#### 8. Click on `Invite`   
---
![image](https://user-images.githubusercontent.com/40828825/136665247-6d5da7bf-6ca4-4392-8854-ec339eefea3f.png)
#### 9. Go to invite user root account  
#### 10. Click on `My Organization` under the account name   
---
![image](https://user-images.githubusercontent.com/40828825/136665255-f73c41ce-ec67-4e83-8c1a-3ce1c49aec29.png)
#### 11. Click on `Invitations`  
---
![image](https://user-images.githubusercontent.com/40828825/136665260-86f66e13-2139-49b9-86ef-911fa60ef97b.png)
#### 12. Click on `Accept`   
---
![image](https://user-images.githubusercontent.com/40828825/136665264-56c19645-98e9-4e9b-b25d-7aebd75bb092.png)
#### 13. Click on `Confirm`   
---
![image](https://user-images.githubusercontent.com/40828825/136665272-07a3251f-7b15-453f-803f-b568c19099a9.png)
#### 14. Go back to SSO page  
#### 15. Click on `Users` on the left pane  
#### 16. Click on `Add user`   
---
![image](https://user-images.githubusercontent.com/40828825/136665285-3f6401bc-e39f-43f8-ba2e-62beda4c9099.png)
#### 17. Enter username  
#### 18. Choose `Generate a one-time password` that you can share with the user  
#### 19. Enter email  
#### 20. Confirm email  
#### 21. Enter first name  
#### 22. Enter last name  
#### 23. Click on `Next: Groups`  
---
![image](https://user-images.githubusercontent.com/40828825/136665291-a54a0bde-1d22-47b5-aed9-7d8e47ce6f00.png)
#### 24. Click on `Create group`  
---
![image](https://user-images.githubusercontent.com/40828825/136665298-02098bda-51a8-4654-8018-232899252fd8.png)
#### 25. Enter group name  
#### 26. Enter description  
#### 27. Click on `Create`  
---
![image](https://user-images.githubusercontent.com/40828825/136665302-58a21ac9-048c-48f3-a2ed-85809f67d322.png)
#### 28. Choose the group  
#### 29. Click on `Add user`  
---
![image](https://user-images.githubusercontent.com/40828825/136665311-2476a3a9-484f-4bfa-aba5-6a7b081a7ddd.png)
#### 30. Copy the sign-in instructions with the user into the notepad  
#### 31. Click on `Close`   
---
![image](https://user-images.githubusercontent.com/40828825/136665346-8c6797df-e876-44f4-a6ad-848ea66f18a3.png)
#### 32. Go to AWS Organizations page (_of the inviting root user_)  
#### 33. Click on `Organize accounts`  
#### 34. Click on `New organizational unit`   
---
![image](https://user-images.githubusercontent.com/40828825/136665351-2dd11cdb-72ed-432b-a6b1-38e78cf60224.png)
#### 35. Enter organizational unit name  
#### 36. Click on `Create organizational unit`  
#### 37. Do the same to create another organizational unit named as _Development_  
---
![image](https://user-images.githubusercontent.com/40828825/136665354-9aaa2c8e-efe8-4bd8-88d7-62425028af05.png)
#### 38. Select a user  
#### 39. Click on `Move`  
---
![image](https://user-images.githubusercontent.com/40828825/136665376-0216cffc-0b3f-4a45-ad01-e16dac2fd2fb.png)
#### 40. Choose the organizational unit (_Development_) that we want to move the user we selected  
#### 41. Click on `Move`  
#### 42. Move the other user to _Production_   
---
![image](https://user-images.githubusercontent.com/40828825/136665381-ad0f8db3-bf7b-44a5-9eaa-b939ee4f927f.png)
#### 43. Go back to SSO page  
#### 44. Click on `AWS accounts` on the left pane  
#### 45. Click on `Permission sets`  
#### 46. Click on `Create pemission set`  
---
![image](https://user-images.githubusercontent.com/40828825/136665389-c3e542c3-871e-433b-b481-42c459ad9e6e.png)
#### 47. Choose `Create a custom permission set`  
#### 48. Click on `Next: Details`   
---
![image](https://user-images.githubusercontent.com/40828825/136665396-0f532386-55ee-4909-97e9-25c1ded7c068.png)
#### 49. Enter permission name (_EC2AndS3FullAccess_)  
#### 50. Enter description  
#### 51. Enter session duration (_1 hour_)  
#### 52. Scroll down  
---
![image](https://user-images.githubusercontent.com/40828825/136665402-6ff00f09-db4c-4b58-83aa-a42b71235067.png)
#### 53. Choose `Attach AWS managed policies`  
#### 54. Choose the policy `AmazonEC2FullAccess`  
#### 55. Choose the policy `AmazonS3FullAccess`  
#### 56. Click on `Next:Tags`  
---
![image](https://user-images.githubusercontent.com/40828825/136665409-384d0f13-07d4-47cd-9d6f-ffe5e144d03c.png)
#### 57. Enter tag(s)  
#### 58. Click on `Next: Review`   
---
![image](https://user-images.githubusercontent.com/40828825/136665434-ad3066d4-da8a-49c6-8c82-704d66558c41.png)
#### 59. Click on `Create`   
---
![image](https://user-images.githubusercontent.com/40828825/136665439-5883faa1-ec16-4ccf-aa97-8428c3757ef6.png)
#### 60. Go back to SSO page  
#### 61. Click on `AWS accounts` on the left pane  
#### 62. Click on `AWS organization`  
#### 63. Choose the `AWS accounts` that we want to grant permissions to users in  
#### 64. Click on `Assign users`  
---
![image](https://user-images.githubusercontent.com/40828825/136665443-97fedc67-0ecc-4004-872e-bd9ed956fe62.png)
#### 65. Choose `Groups`  
#### 66. Choose the group (_demo_group_)  
#### 67. Click on `Next: Permission sets`  
---
![image](https://user-images.githubusercontent.com/40828825/136665448-bac6f892-5a62-40f5-8bb0-c328471eb46e.png)
#### 68. Choose the permission set (_EC2AndS3FullAccess_)  
#### 69. Click on `Finish`  
---
![image](https://user-images.githubusercontent.com/40828825/136665455-cf27e4d2-8f71-4877-b9bb-087d230907ff.png)
#### 70. Click on `Proceed to AWS accounts`   
---
![image](https://user-images.githubusercontent.com/40828825/136665462-4725b28f-da41-4afb-af09-06ebadbd6897.png)
#### 71. Go to the notepad and copy the above url  
#### 72. Paste it in the URL of the web page  
---
![image](https://user-images.githubusercontent.com/40828825/136665475-501bd038-76a2-4ccc-8bbf-f1abbc38397d.png)
#### 73. Enter the username (_from the notepad_)  
#### 74. Enter the password (_from the notepad_)  
#### 75. Click on `Sign in`   
---
![image](https://user-images.githubusercontent.com/40828825/136665487-0eda3fc0-f863-41ab-a776-0739b09ecebb.png)
#### 76. On the opening page, enter the same password (_current password_)  
#### 77. Enter a new password  
#### 78. Confirm new password  
#### 79. Click on `Update password`  
---
![image](https://user-images.githubusercontent.com/40828825/136665496-d7327107-0643-48af-a02c-0a8cf6c83a6c.png)
#### 80. Click on `AWS Account (2)`  
#### 81. Click on dropdown arrows on the right of each root user account  
#### 82. Click on `Management console`  
#### 83. Try to create EC2 instances and S3 buckets on each root user account  
#### 84. Try to create another entity on the accounts  
---
