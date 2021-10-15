## Create a Cognito identity pool  
<br><br>   


![image](https://user-images.githubusercontent.com/40828825/137185150-f3226ea8-11a2-4dd7-9953-ee5e5e48debc.png)
#### 1. Create a user pool as described in the above lab  
---
![image](https://user-images.githubusercontent.com/40828825/137185224-fb98ea68-e281-49b3-ab78-8ef90544851a.png)
#### 2. Create a bucket as described in the above lab  
---
![image](https://user-images.githubusercontent.com/40828825/137185241-96773357-fda9-4a3a-a552-f0daf08d6149.png)
#### 3. Choose the bucket created (demo-cognito-bucket-s3)  
#### 4. Click on `Permissions` 
---
```
<CORSConfiguration>
	<CORSRule>
		<AllowedOrigin>*</AllowedOrigin>
		<AllowedMethod>GET</AllowedMethod>
		<AllowedMethod>PUT</AllowedMethod>
		<AllowedMethod>POST</AllowedMethod>
		<AllowedMethod>HEAD</AllowedMethod>
		<AllowedMethod>DELETE</AllowedMethod>
		<MaxAgeSeconds>3000</MaxAgeSeconds>
		<AllowedHeader>*</AllowedHeader>
	</CORSRule>
</CORSConfiguration>
```
#### 5. Copy the above code   
---
![image](https://user-images.githubusercontent.com/40828825/137185351-42ee31a1-c118-4bbd-b155-e5bc826d1386.png)
#### 6. Click on `CORS configuration` tab  
#### 7. Paste the code in the editor 
#### 8. Click on `Save`  
---
![image](https://user-images.githubusercontent.com/40828825/137185372-e6fa9d42-cbcd-42af-be27-c65be8355215.png)
#### 9. Click on `Block public access` tab  
#### 10. Click on `Edit` 
---
![image](https://user-images.githubusercontent.com/40828825/137185401-c61c4727-e2a6-4f2f-a9b9-75aecc8e97a4.png)
#### 11. Uncheck `Block all public access`  
#### 12. Click on `Save` 
---
![image](https://user-images.githubusercontent.com/40828825/137185422-517117dc-cf4b-4e6e-81c7-7a5241c11979.png)
#### 13. Type "confirm"  
#### 14. Click on `Confirm` 
---
![image](https://user-images.githubusercontent.com/40828825/137185449-56ecdc4e-82f0-44b6-a45c-aec206646def.png)
#### 15. Go to the AWS console  
#### 16. Click on `Cognito` under Security, Identity & Compliance 
---
![image](https://user-images.githubusercontent.com/40828825/137185462-f7129998-7393-4192-a828-4324a6cae46b.png)
#### 17. Click on `Manage Identity Pools`   
---
![image](https://user-images.githubusercontent.com/40828825/137185481-be45308f-4b8c-434d-811c-5afddb016715.png)
#### 18. Enter a pool name (_my app 2_)  
#### 19. Disable `access to unauthenticated identities` 
#### 20. Scroll down  
---
![image](https://user-images.githubusercontent.com/40828825/137185509-2e01202c-5143-4d5c-b9f5-1579feb6736e.png)
#### 21. Go to our user pool (_my-ireland-pool_)  
#### 22. Click on `General settings` 
#### 23. Copy the _pool id_  
---
![image](https://user-images.githubusercontent.com/40828825/137185527-516af170-2d1a-4054-baee-761e4f0a1274.png) 
#### 24. Click on `App clients`  
#### 25. Copy _App client id_  
---
![image](https://user-images.githubusercontent.com/40828825/137185550-5ba66dd8-af70-47ec-8f72-739cbb7533bb.png)
#### 26. Go to the identity pool page  
#### 27. Paste the ids in their respective cells 
#### 28. Click on `Create Pool`  
---
```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "mobileanalytics:PutEvents",
        "cognito-sync:*",
        "cognito-identity:*"
      ],
      "Resource": [
        "*"
      ]
    },
    {
      "Effect": "Allow",
      "Action": [
        "s3:*"
      ],
      "Resource": [
        "arn:aws:s3:::demo-cognito-bucket-s3/private/${cognito-identity.amazonaws.com:sub}/*"
      ]
    }
  ]
}
```
#### 29. Copy the above code  
---
![image](https://user-images.githubusercontent.com/40828825/137185646-1333904c-515e-4853-9225-7e9d0eb81ad1.png)
#### 30. Click on `Edit`  
---
![image](https://user-images.githubusercontent.com/40828825/137185678-b84d70c5-dd5b-4747-bd4f-02c761f9c5be.png)
#### 31. Click on `OK`   
---
![image](https://user-images.githubusercontent.com/40828825/137185699-edb0e7fb-9162-4ebc-b995-bc8e3f5847cc.png)
#### 32. Paste the code in the _Policy Document_  
#### 33. Click on `Allow` 
---
![image](https://user-images.githubusercontent.com/40828825/137185717-465866b6-cf6e-4747-849f-1fa4b46022ed.png) 
#### 34. Take a note of the identity pool ID 
---
  
