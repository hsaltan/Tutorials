## Build an API gateway  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/137007303-1a23ef19-aff1-4b8d-a13e-631b62e5cf79.png)
#### 1. Go to the AWS console  
#### 2. Click on `Lambda` under Compute 
---
![image](https://user-images.githubusercontent.com/40828825/137007320-3859a1cc-5572-4149-b17d-e200904d903e.png)
#### 3. Click on `Functions` on the left pane  
#### 4. Click on `Create` function 
---
![image](https://user-images.githubusercontent.com/40828825/137007352-1a47a16e-cc2e-4e56-85e2-1d27aab1a179.png)
#### 5. Choose an option (_Author from scratch_)  
#### 6. Scroll down 
---
![image](https://user-images.githubusercontent.com/40828825/137007373-15b3687e-0716-406c-8a95-53f4c7304787.png)
#### 7. Enter a function name (_TransactionProcessor_)  
#### 8. Choose the runtime (_Python 3.8_) 
---
![image](https://user-images.githubusercontent.com/40828825/137007398-b41dbcc0-cb90-4c3e-ba92-5b75f38ae6d1.png) 
#### 9. Choose the execution role (_Create a new role with basic Lambda permissions_)  
#### 10. Click on `Create` function  
---
```
import json

print('Loading function')

def lambda_handler(event, context):
	#1. Parse out query string params
	transactionId = event['queryStringParameters']['transactionId']
	transactionType = event['queryStringParameters']['type']
	transactionAmount = event['queryStringParameters']['amount']

	print('transactionId=' + transactionId)
	print('transactionType=' + transactionType)
	print('transactionAmount=' + transactionAmount)

	#2. Construct the body of the response object
	transactionResponse = {}
	transactionResponse['transactionId'] = transactionId
	transactionResponse['type'] = transactionType
	transactionResponse['amount'] = transactionAmount
	transactionResponse['message'] = 'Hello from Lambda land'

	#3. Construct http response object
	responseObject = {}
	responseObject['statusCode'] = 200
	responseObject['headers'] = {}
	responseObject['headers']['Content-Type'] = 'application/json'
	responseObject['body'] = json.dumps(transactionResponse)

	#4. Return the response object
	return responseObject
```
#### 11. Copy the above code   
---
![image](https://user-images.githubusercontent.com/40828825/137007760-a64a6986-d9af-43dd-ac36-3afffca19c8a.png)
#### 12. Paste the code in the lambda editor  
#### 13. Click on `File` 
#### 14. Click on `Save` 
---
![image](https://user-images.githubusercontent.com/40828825/137007785-127b51be-cabb-49d1-b80d-c07ca17f207b.png)
#### 15. Click on `Deploy`   
---
![image](https://user-images.githubusercontent.com/40828825/137007800-9b54f868-439d-45d8-aec8-34bc2dc3e303.png)
#### 16. Go to the AWS console  
#### 17. Click on `API Gateway` under Networking & Content Delivery  
---
![image](https://user-images.githubusercontent.com/40828825/137007825-d3d35c58-ae34-4a5d-a5dc-59b4ef5a4e3f.png)
#### 18. Click on `Build`   
---
![image](https://user-images.githubusercontent.com/40828825/137007836-6da00b63-904e-462c-ad1c-038bcf317520.png)
#### 19. Choose New API  
#### 20. Enter an API name (_TransactionAPIs_) 
#### 21. Choose the endpoint type (_Regional_) 
#### 22. Click on `Create API` 
---
![image](https://user-images.githubusercontent.com/40828825/137007857-87c9ca26-3731-4f4e-86f7-593f69bb9792.png)
#### 23. Click on `Actions`  
#### 24. Click on `Create Resource`  
---
![image](https://user-images.githubusercontent.com/40828825/137007878-f86993e5-66ba-42b2-970a-b33b8f51aa8c.png)
#### 25. Enter a resource name (_transactions_)  
#### 26. Leave else as default 
#### 27. Click on `Create Resource`  
---
![image](https://user-images.githubusercontent.com/40828825/137007904-1b2b0599-cde0-4240-af15-14eb9f753bfc.png)
#### 28. Choose the resource (_transactions_)  
#### 29. Click on `Actions` 
#### 30. Click on `Create Method`  
---
![image](https://user-images.githubusercontent.com/40828825/137007931-46470f9e-f4a8-4925-ae3c-da03a9d0b70d.png)
#### 31. Choose a method (_GET_)  
#### 32. Click on `OK`  
---
![image](https://user-images.githubusercontent.com/40828825/137007965-94b4b50b-517f-4b29-a858-9c87b2d4059a.png)
#### 33. Choose an integration type (_Lambda Function_)  
#### 34. Enable Use Lambda Proxy integration 
#### 35. Choose Lambda Function (_TransactionProcessor_) 
#### 36. Click on `Save` 
---
![image](https://user-images.githubusercontent.com/40828825/137007985-03ce8049-ecf0-406f-a8e9-e708936fd4d8.png)
#### 37. Click on `OK`  
---
![image](https://user-images.githubusercontent.com/40828825/137007999-5f37c010-17b5-40e0-9120-a8d170e1852c.png)
#### 38. Choose the resource (_transactions_)  
#### 39. Choose the method (_GET_) 
#### 40. Click on `Actions` 
#### 41. Click on `Deploy API` 
---
![image](https://user-images.githubusercontent.com/40828825/137008022-caa03df9-03c3-4133-8101-b6fdb609a6f9.png)
#### 42. Choose the deployment stage (_New Stage_)  
#### 43. Enter a stage name (_test_) 
#### 44. Click on `Deploy` 
---
![image](https://user-images.githubusercontent.com/40828825/137008057-7c9d7f7a-8be3-4942-95ba-778ca917662b.png)
#### 45. Choose the method (_GET_)  
#### 46. Copy the URL and paste it in the notepad  
---
```
https://2pb52cinb5.execute-api.eu-west-1.amazonaws.com/test/transactions?transactionId=5&type=PURCHASE&amount=500
```
#### 47. Add _?transactionId=5&type=PURCHASE&amount=500_ to the end of the URL as above  
#### 48. Click on the URL or copy and paste it in the URL of the web browser 
---
![image](https://user-images.githubusercontent.com/40828825/137008139-f4a66fec-4bae-42e1-9694-ec83639f4947.png)
#### 49. Copy and paste it in the URL of the web browser  
---
![image](https://user-images.githubusercontent.com/40828825/137008164-b9d1adb9-5b0e-4fbb-8415-300efceb7498.png)
#### 50. Go to the AWS console  
#### 51. Click on `CloudWatch` under Management & Governance  
---
![image](https://user-images.githubusercontent.com/40828825/137008185-57ee954a-8b5f-4791-8541-3963a17f4eee.png)
#### 52. Click on `Log groups` on the left pane  
#### 53. Choose the log group (_/aws/lambda/TransactionProcessor_) 
---
![image](https://user-images.githubusercontent.com/40828825/137008196-0ac0850c-48e2-4923-8272-23aebb86730e.png)
#### 54. Choose the log stream (2020/10/07/[$LATEST]ab0a39c4e65c49f394f819413c11a042)  
---
![image](https://user-images.githubusercontent.com/40828825/137008208-25fae390-4a6f-4fed-93b3-2f7c72f36342.png)
#### 55. Check the events   
---
  
