## Convert a media file to another format  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/137004288-208f57c0-d03f-43b7-b590-ac6321b25973.png)  
#### 1. Go to the AWS console  
#### 2. Click on `Elastic Transcoder` under Media Services
---
![image](https://user-images.githubusercontent.com/40828825/137004326-08cf47df-cb67-4da5-bf7b-ebee710315db.png)  
#### 3. Click on `Create a new Pipeline`  
---
![image](https://user-images.githubusercontent.com/40828825/137004351-a942ce89-f1c1-46f2-b933-499403d5538f.png)  
#### 4. Enter a pipeline name (_pipeline-to-web_)  
#### 5. Choose the input bucket (_demo-input-video_)
#### 6. Choose IAM role
#### 7. Choose the output bucket (_demo-output-video_)
#### 8. Choose the storage class (_Standard_)
#### 9. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137004378-e4136cf8-1ea3-4cfc-9ab5-9f884f959367.png)  
#### 10. Choose the bucket for thumbnails (_demo-thumbnail-video_)  
#### 11. Choose the storage class (_Standard_)
#### 12. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137004396-146fbd45-6a9f-41e8-a742-afd5853e717e.png)  
#### 13. Choose notifications (_No notification_)  
#### 14. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137004419-a21b2abd-76fb-4d15-a437-7fed4bc0c466.png)  
#### 15. Choose AWS KMS Key ARN (_default_)  
#### 16. Click on `Create Pipeline`
---
![image](https://user-images.githubusercontent.com/40828825/137004444-61141eeb-4cae-4507-9c30-80facb1666e9.png)  
#### 17. Click on `Create New Job`  
---
![image](https://user-images.githubusercontent.com/40828825/137004469-0c969239-8116-4c30-988f-4567dac835b2.png)  
#### 18. Choose the pipeline (_pipeline-to-web_)  
#### 19. Enter an output key prefix (_test/_)
#### 20. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137004498-7a2667f8-9e9a-4ce6-8779-f2801081ff8f.png)  
#### 21. Choose the input key  
#### 22. Choose only one input for this example and leave else as default
#### 23. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137004517-200265d5-b792-479d-a2d3-4b006adbaa43.png)  
#### 24. Choose a preset (_System preset: Web_)  
#### 25. Enter an output key with an extension name (_transcoded.mp4_)
#### 26. Create thumbnails (_Yes_)
#### 27. Enter a thumbnail filename pattern (_transcoding-1_)
#### 28. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137004542-3642107d-db32-459d-b33b-9f18ce145445.png)  
#### 29. Leave everything as default  
#### 30. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137004569-a9b59c09-eafa-4ff9-871b-70f251fe36df.png)  
#### 31. Choose only one output for this example  
#### 32. Enter tag(s)
#### 33. Click on `Create New Job`
---
![image](https://user-images.githubusercontent.com/40828825/137004591-0760ff18-2866-443d-92d2-c8c819bff53a.png)  
#### 34. See the output video in S3  
---
![image](https://user-images.githubusercontent.com/40828825/137004618-3c4a7f28-3410-4d88-82d2-d6b85ad7dbd3.png)  
#### 35. See the thumbnail files in S3  
---
