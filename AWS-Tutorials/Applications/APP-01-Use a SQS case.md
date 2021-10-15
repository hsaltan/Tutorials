## Use a SQS case  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/136993732-a3459aa1-2e9b-45f7-8b95-eee2f1e6af50.png) 
#### 1. On the AWS console, click on Simple Queue Service under Application Integration  
---
![image](https://user-images.githubusercontent.com/40828825/136993758-b847008b-6111-4954-b1e4-a357ae160317.png) 
#### 2. Click on `Create queue`  
---
![image](https://user-images.githubusercontent.com/40828825/136993792-2c40450b-5021-4ce2-8e9e-c548ef267d8e.png) 
#### 3. Choose SQS type (_Standard_) 
#### 4. Enter a name (_ireland-dlq_) 
#### 5. Scroll down  
---
![image](https://user-images.githubusercontent.com/40828825/136993814-1cbfffcf-57f5-4137-831d-4b595a40220f.png) 
#### 6. Set the visibility timeout (_30 seconds for which the message will be invisible to others during the proccessing_)  
#### 7. Set the delivery delay (_0 seconds of delay until the start of processing_) 
#### 8. Set the receive message wait time (_20 seconds of polling time - long polling_) 
#### 9. Set the message retention period (_4 days for which the message will be kept in the queue_) 
#### 10. Set the maximum message size (_256 bytes_) 
#### 11. Scroll down 
---
![image](https://user-images.githubusercontent.com/40828825/136993843-99cc111e-6d69-459a-bd6c-9d95ad804d42.png) 
#### 12. Choose the access method (_Basic_)  
#### 13. Define the sender (_only queue owner_) 
#### 14. Define the receiver (_only queue owner_) 
#### 15. Scroll down 
---
![image](https://user-images.githubusercontent.com/40828825/136993870-80f27193-9015-4471-8479-8cfbf04dadf7.png) 
#### 16. Enable or disable server-side encryption  
#### 17. Scroll down 
---
![image](https://user-images.githubusercontent.com/40828825/136993903-fd78643b-bf0b-481f-b303-e54d64212113.png) 
#### 18. Click on `Add new tag`  
#### 19. Enter tag(s) 
#### 20. Click on `Create queue` 
---
![image](https://user-images.githubusercontent.com/40828825/136993940-8ec15f1e-6317-4073-9ff0-6d3dccdc6e9b.png) 
#### 21. Click on `Create queue` to create another queue (_ireland-main_)  
#### 22. Use the same configuration as above with the exceptions shown below 
---
![image](https://user-images.githubusercontent.com/40828825/136993978-5e414310-410a-46ab-aabc-c9886792ea20.png) 
#### 23. Enter a name (_ireland-main_)  
#### 24. Scroll down 
---
![image](https://user-images.githubusercontent.com/40828825/136994008-3ebd697a-3d6a-49f7-9345-2287df9276b1.png) 
#### 25. Enable dead-letter queue  
#### 26. Choose queue (_Choose a dead-letter queue_) 
#### 27. Choose the queue ARN (_ireland-dlq_) 
#### 28. Set maximum receives (_3_) 
#### 29. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/136994030-09228573-725b-4bd2-acab-8fe813c282d5.png) 
#### 30. Click on `Add new tag` 
#### 31. Enter tag(s) 
#### 32. Click on `Create queue` 
---
![image](https://user-images.githubusercontent.com/40828825/136994063-9ed5c604-ada3-4da0-8408-24c12297ed82.png) 
#### 33. Go to the SQS Dashboard  
#### 34. Choose the queue (_ireland-main_) 
#### 35. Click on `Actions` 
#### 36. Click on `Send and receive messages` 
--- 
![image](https://user-images.githubusercontent.com/40828825/136994087-b47851a8-5ff4-45a3-81ba-6d6a0d4560f4.png)
#### 37. Enter a message  
#### 38. Set the delivery delay (_0_) 
#### 39. Click on `Add new attribute` 
#### 40. Enter message attribute 
---
![image](https://user-images.githubusercontent.com/40828825/136994122-39c9b6cf-6119-4637-874e-806b2e3b1017.png) 
#### 41. Click on `Send message`  
#### 42. Send two other messages like this  
---
![image](https://user-images.githubusercontent.com/40828825/136994168-19cdf867-8473-4409-8f98-a6a88144f8e6.png) 
#### 43. Go to the SQS Dashboard  
#### 44. Choose the queue (_ireland-main_) 
#### 45. Click on `Actions` 
#### 46. Click on `Send and receive messages` 
---
![image](https://user-images.githubusercontent.com/40828825/136994193-eced98a2-7fc5-4173-a878-4f337f9472fa.png) 
#### 47. Click on `Edit poll settings`  
---
![image](https://user-images.githubusercontent.com/40828825/136994221-03977f98-6eb6-41c4-aa96-cba1468687c2.png) 
#### 48. Set the polling duration (_20 seconds_)  
#### 49. Set the maximum message count (_3_) 
#### 50. Click on `Save` 
---
![image](https://user-images.githubusercontent.com/40828825/136994251-46fd02ee-818d-4b2e-bf74-59d9f83569d0.png) 
#### 51. Click on `Poll for messages`   
---
![image](https://user-images.githubusercontent.com/40828825/136994283-aaf01e74-6a0c-4852-8632-c7694cc4daf4.png) 
#### 52. Click on `Poll for messages` two more times until you see the messages get removed  
---
![image](https://user-images.githubusercontent.com/40828825/136994310-4590f831-b192-4ab0-97fd-a8c94429452a.png) 
#### 53. Go to the SQS Dashboard  
#### 54. Choose the queue (_ireland-dlq_) 
#### 55. Click on `Send and receive messages` 
---
![image](https://user-images.githubusercontent.com/40828825/136994335-5fea1bf2-ef9a-4659-a31d-427df9107123.png) 
#### 56. Click on `Poll for messages`   
---
![image](https://user-images.githubusercontent.com/40828825/136994356-adca8749-c620-430d-9e71-ba7d5205472d.png) 
#### 57. Choose a message  
#### 58. Click on `Delete` 
---
![image](https://user-images.githubusercontent.com/40828825/136994383-d5b23e1d-4a71-4044-862d-d9fee803d35f.png) 
#### 59. Click on `Delete`  
---
