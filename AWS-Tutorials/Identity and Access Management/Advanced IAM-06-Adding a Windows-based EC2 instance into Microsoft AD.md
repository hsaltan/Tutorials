## Adding a Windows-based EC2 instance into Microsoft AD  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/136662822-9a5c9bbe-6a5b-4245-b78e-284e4b59597d.png)  
#### 1. Launch a Windows-based EC2 instance in AWS Managed Microsoft AD as described in the above lab  
---
![image](https://user-images.githubusercontent.com/40828825/136662999-142d0256-147e-4bc8-819e-a8ee3fd8aac3.png)  
#### 2. Click on `Windows Explorer`  
---
![image](https://user-images.githubusercontent.com/40828825/136663008-931e0166-4d07-4931-8849-bbac0e7346d9.png)  
#### 3. Right click on `This PC`  
#### 4. Click on `Properties`
---
![image](https://user-images.githubusercontent.com/40828825/136663016-ce06c2a0-3121-4d15-89d4-f5bb8734bab7.png)  
#### 5. Check if our EC2 instance is in the AD domain  
---
![image](https://user-images.githubusercontent.com/40828825/136663026-d3cf8260-5070-4443-a95a-07a0ecfffa50.png)  
#### 6. Launch a Windows-based EC2 instance as described in the above lab  
---
![image](https://user-images.githubusercontent.com/40828825/136663054-06d667fe-39ea-4bfb-b613-38cd7747bfcb.png) 
#### 7. RDP into Windows-based EC2 instance as described in the above lab  
---
![image](https://user-images.githubusercontent.com/40828825/136663071-1928e0f0-b06e-42e6-8972-747e4b8ea90a.png) 
#### 8. Click on `Windows Explorer`  
---
![image](https://user-images.githubusercontent.com/40828825/136663098-44f2e9a3-4732-4ce9-9b89-c4b7a7cf74b9.png) 
#### 9. Right click on `This PC`  
#### 10. Click on `Properties`
---
![image](https://user-images.githubusercontent.com/40828825/136663106-c6850d3f-5a1c-44b6-a082-e212cdeea523.png)  
#### 11. Click on `Change settings`  
---
![image](https://user-images.githubusercontent.com/40828825/136663115-28b5532e-2a43-4a7d-933d-596fd1e1956c.png)
#### 12. Click on `Change`  
---
![image](https://user-images.githubusercontent.com/40828825/136663126-e63188ba-515b-4edb-a0bb-106f8974a235.png)  
#### 13. Go back to AWS console  
#### 14. Click on `Directory Service`
---
![image](https://user-images.githubusercontent.com/40828825/136663133-0e0a637a-e5de-4ead-9776-0d4a213d68bb.png)  
#### 15. Copy the directory name (_corp.adexample.com_)  
---
![image](https://user-images.githubusercontent.com/40828825/136663142-d65130ed-3ad9-4b3d-8f80-81053e4a2396.png)  
#### 16. Go back to Windows EC2  
#### 17. Click on `Domain`  
#### 18. Paste the directory name in `Domain`  
#### 19. Click on `OK`  
---
![image](https://user-images.githubusercontent.com/40828825/136663154-77dd943f-29eb-4d6f-9082-4413d2b8cd23.png) 
#### 20. Click on `OK` on the error message  
---
![image](https://user-images.githubusercontent.com/40828825/136663170-b8dd834b-05b2-41a1-9d45-1bd86ae30c6e.png) 
#### 21. Click on `Find` icon at the bottom of desktop  
---
![image](https://user-images.githubusercontent.com/40828825/136663178-9db9d21a-0f11-4a76-9f63-b23c527a3981.png) 
#### 22. Type _ncpa.cpl_ and press `Enter`  
---
![image](https://user-images.githubusercontent.com/40828825/136663190-3c072631-d355-4468-a3f3-6a1c17f2d413.png)  
#### 23. On the opening page, right click on `Ethernet`  
#### 24. Click on `Properties`
---
![image](https://user-images.githubusercontent.com/40828825/136663196-1f8003ad-7958-4f9b-a767-03196af2072a.png)
#### 25. Uncheck and check back again _Internet Protocol Version 4_  
#### 26. Click on `Properties`
---
![image](https://user-images.githubusercontent.com/40828825/136663201-ad581427-68e5-4e72-b40f-9a4955249397.png)  
#### 27. Go back to Directory Service page  
#### 28. Click on the `directory`
---
![image](https://user-images.githubusercontent.com/40828825/136663212-bf11620f-178c-4cd3-b7d0-95449f00784b.png)
#### 29. Copy any one of DNS addresses shown there  
---
![image](https://user-images.githubusercontent.com/40828825/136663221-8dabff03-a735-4229-8c96-e120b1f587d1.png)  
#### 30. Go back to Windows EC2 instance  
#### 31. Click on `Use` the following DNS server addresses
#### 32. Paste the IPv4 address in `Preferred DNS server`
#### 33. Click on `OK`
---
![image](https://user-images.githubusercontent.com/40828825/136663229-e9541b9f-9b3f-4af0-8afc-38f2f3819110.png) 
#### 34. Click on `OK`  
---
![image](https://user-images.githubusercontent.com/40828825/136663242-7cdf7a3a-7982-4d6e-99b2-120b9451ba49.png) 
#### 35. Enter name (_Admin_)
#### 36. Enter directory password (_ADexample1_)
#### 37. Click on `OK`
---
![image](https://user-images.githubusercontent.com/40828825/136663246-ea224b59-79a1-4273-b42e-0bb5cceb4f43.png) 
#### 38. Click on `OK`  
---
![image](https://user-images.githubusercontent.com/40828825/136663262-84869c8a-407e-4a86-8b5d-ce455b4fd11c.png)  
#### 39. Click on `Restart Now`  
---
![image](https://user-images.githubusercontent.com/40828825/136663271-393d7dec-4a9a-4fa6-acbb-8d45a16fbff6.png)
#### 40. Log into the Windows EC2 instance  
#### 41. Enter username
#### 42. Enter password
#### 43. Click on `Continue`
---
![image](https://user-images.githubusercontent.com/40828825/136663281-fabf0450-f76c-4f8f-a80e-288339568cb6.png)  
#### 44. Click on `Server Manager`  
---
![image](https://user-images.githubusercontent.com/40828825/136663285-2f4ebf44-b789-421f-98da-503b71e364c2.png)  
#### 45. Click on `Add` roles and features  
---
![image](https://user-images.githubusercontent.com/40828825/136663292-f4a13ce2-84c6-46e9-a0bf-6ddf6ec0f1eb.png)  
#### 46. Click on `Next`  
---
![image](https://user-images.githubusercontent.com/40828825/136663301-4a867fc6-b294-4fb2-a71a-8819e22f1aff.png) 
#### 47. Choose `Role-based` or `feature-based installation`  
#### 48. Click on `Next`
---
![image](https://user-images.githubusercontent.com/40828825/136663305-35dee063-4c6d-4309-94c4-01c1d091f5cb.png) 
#### 49. Click on `Next`  
---
![image](https://user-images.githubusercontent.com/40828825/136663310-a379443f-d4ca-4a17-a295-699284b40872.png) 
#### 50. Click on `Next`  
---
![image](https://user-images.githubusercontent.com/40828825/136663313-93fdd0b8-1f82-4cef-b04a-8779cb344929.png)  
#### 51. Choose `Role Administration Tools`  
#### 52. Choose `Active Directory Certificate Services Tools`  
#### 53. Choose `Active Directory Rights Management Services Tools`  
#### 54. Click on `Next`  
---
![image](https://user-images.githubusercontent.com/40828825/136663321-96d2446f-0519-492f-9b2a-569aab13c259.png)
#### 55. Click on `Install`  
---
![image](https://user-images.githubusercontent.com/40828825/136663324-2c4219b3-bd9e-489b-9301-b5a8d314202b.png)  
#### 56. Click on `Close`  
---
![image](https://user-images.githubusercontent.com/40828825/136663332-1a0d001b-f473-430d-9338-31733e7f03b2.png)  
#### 57. Click on `Windows` icon  
#### 58. Click on `Restart`
---
![image](https://user-images.githubusercontent.com/40828825/136663340-065d9e45-7bd8-4985-b058-164e9bc1dd86.png)  
#### 59. Log back into Windows EC2 instance  
#### 60. Click on `Windows Administrative`  
---
![image](https://user-images.githubusercontent.com/40828825/136663345-6d46b93e-8b5e-4c00-814b-a16e8757437c.png) 
#### 61. On the opening page, double click on `Active Directory Users and Computers`  
---
![image](https://user-images.githubusercontent.com/40828825/136663351-80d05b3a-169d-4f33-94c2-d52faaf0486f.png) 
#### 62. Click on `Users`  
#### 63. Click on `New`
#### 64. Click on `User`
---
![image](https://user-images.githubusercontent.com/40828825/136663361-1f2feb6d-7e78-4fd8-a19a-c312a8a01356.png) 
#### 65. Enter first name
#### 66. Enter last name
#### 67. Enter user logon name
#### 68. Click on `Next`
---
![image](https://user-images.githubusercontent.com/40828825/136663401-48285020-fc54-4198-a741-f29c9e58b05a.png)  
#### 69. Choose `Password never expires` for this example
#### 70. Enter password
#### 71. Confirm password
#### 72. Click on `Next`
---
![image](https://user-images.githubusercontent.com/40828825/136663409-d88662b2-4349-43fc-846f-b6068d265781.png)  
#### 73. Click on `Finish`  
---
![image](https://user-images.githubusercontent.com/40828825/136663418-60f9f062-3772-4d15-ab47-db7dd38b6232.png)  
#### 74. Click on `Windows` icon
#### 75. Click on `Restart` 
---




