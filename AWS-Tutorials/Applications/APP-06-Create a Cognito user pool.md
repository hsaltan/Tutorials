## Create a Cognito user pool  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/137171160-77490a15-789f-4c56-8fba-272f4f91f59c.png)  
#### 1. Go to the _https://nodejs.org/en/download/_ page to download the macOS Installer   
---
```
Hasan-iMac:App hsa$ npx create-react-app my-app
Hasan-iMac:App hsa$ cd my-app
```
#### 2. On the Mac terminal, type the above commands to create a react application  
---
![image](https://user-images.githubusercontent.com/40828825/137171262-5c4e8ba1-c88c-40aa-b0c9-a1af0bc276cf.png)  
#### 3. Go to the AWS console  
#### 4. Click on `Cognito` under Security, Identity & Compliance
---
![image](https://user-images.githubusercontent.com/40828825/137171281-b0dfe2ff-c319-4b12-91e1-ad8e8bb54660.png) 
#### 5. Click on `Manage User Pools`  
---
![image](https://user-images.githubusercontent.com/40828825/137171313-4243d610-85e5-4e52-a61b-47ea29fafdc5.png)  
#### 6. Click on `Create a user pool`  
---
![image](https://user-images.githubusercontent.com/40828825/137171347-760873a9-32bf-4fc3-8cb6-6691f1a390cb.png)
#### 7. Enter a pool name (_demo-cognito_)  
#### 8. Click on `Step through settings`
---
![image](https://user-images.githubusercontent.com/40828825/137171369-9da194af-2a83-411b-ba92-ca3a54fff275.png)  
#### 9. Choose Email address or phone number  
#### 10. Choose Allow email addresses
#### 11. Choose _(Recommended) Enable case insensitivity for username input_
#### 12. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137171392-9d4e53a4-acb9-4afd-846d-ec2a855ef782.png)  
#### 13. Leave it as default for this example  
#### 14. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137171420-3b6505d4-4239-44f0-82e3-a86a3996cd24.png)
#### 15. Click on `Next step`  
---
![image](https://user-images.githubusercontent.com/40828825/137171442-fb5adbe9-3dac-40e0-ae3f-88862ef7ead0.png) 
#### 16. Leave it as default for this example  
#### 17. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137171477-97d54b5d-3b73-479e-af69-02086dc1bd35.png)
#### 18. Leave it as default for this example  
#### 19. Click on `Next step`
---
![image](https://user-images.githubusercontent.com/40828825/137171503-4d5ac772-db4b-48ad-923f-757e239dcd2f.png)
#### 20. Leave it as default for this example  
#### 21. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137171527-8480484e-f80e-417a-ba9d-4ff25731e9d3.png)
#### 22. Leave it as default for this example  
#### 23. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137171554-c8d39ac0-93a7-46e0-aff7-4bfbf11f4236.png)
#### 24. Click on `Create role`  
#### 25. Click on `Next step`
---
![image](https://user-images.githubusercontent.com/40828825/137171584-b6b83a16-c503-458d-b846-4c978b0d1a54.png)
#### 26. Leave it as default for this example  
#### 27. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137171602-5b042f74-e689-4d7a-85ea-e92613521d15.png)
#### 28. Leave it as default for this example  
#### 29. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137171633-7ae82f99-a497-47da-a2b7-867fc3b843ae.png)
#### 30. Choose the verification type (_Link_)  
#### 31. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137171659-4d90dab9-335b-47b8-b922-73453f8989b2.png)
#### 32. Leave it as default for this example  
#### 33. Click on `Next step`
---
![image](https://user-images.githubusercontent.com/40828825/137171678-ff104e0a-22ba-49c7-8a83-6f56f7992b07.png)
#### 34. Enter tag(s)  
#### 35. Click on `Next step`
---
![image](https://user-images.githubusercontent.com/40828825/137171704-f14e4557-f3ba-404e-81b1-e344e14be6dc.png)
#### 36. Click on No  
#### 37. Click on `Next step`
---
![image](https://user-images.githubusercontent.com/40828825/137171732-4017e463-5dae-40ec-a7fa-995e725ee312.png)
#### 38. Click on `Add an app client`  
---
![image](https://user-images.githubusercontent.com/40828825/137171754-58561c78-369a-40eb-8527-4f9c762e98eb.png) 
#### 39. Enter an app client name (_web_)  
#### 40. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137171783-fa2c78b9-36f2-4b0c-a05e-af7915b0fac3.png)
#### 41. Uncheck Generate client secret  
#### 42. Click on `Create app client`
#### 43. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137171812-a4006ba4-d602-497b-b71d-b1f188d3fd93.png)
#### 44. Click on `Next step`  
---
![image](https://user-images.githubusercontent.com/40828825/137171846-e1b55064-5326-4de3-b9fe-38746eef61e1.png)
#### 45. Leave it as default for this example  
#### 46. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137171876-40b44cff-a943-4bd1-8557-27b7fc96f3f9.png)
#### 47. Leave it as default for this example  
#### 48. Click on `Next step`
---
![image](https://user-images.githubusercontent.com/40828825/137171907-d44b8ec8-5a4c-4b51-8cff-3c7284cedd81.png)
#### 49. Click on `Create pool`  
---
![image](https://user-images.githubusercontent.com/40828825/137171928-ad0578be-557b-42c7-a6bf-d3b094cc71a7.png)
#### 50. Click on `Domain name` on the left pane  
#### 51. Enter Amazon Cognito domain (_serdar-demo_)
#### 52. Click on `Save changes`
---
![image](https://user-images.githubusercontent.com/40828825/137171974-a66f9c4b-c66d-438d-b515-600f73217cab.png)
#### 53. Open the application file (_App.js_)  
---
```
 const poolData = {
    UserPoolId: "eu-west-1_KPQ8JukXw",
    ClientId: "437r7rmt8rk949nhbhi54bsqlg"
  }

  const userPool = new CognitoUserPool(poolData);

  const onSubmit = event => {
    event.preventDefault();
    console.log("submitted...");
    userPool.signUp(email, password, [], null, (err, data) => {
      if(err) console.error(err);
      console.log(data);
    });
  };

  return (
    <form onSubmit={onSubmit}>
      <input value={email} onChange={event=> setEmail(event.target.value)} type="text" />
      <input value={password} onChange={event=> setPassword(event.target.value)} type="text" />
      <button>Sign Up</button>
    </form>
  );
}

export default App;
```
#### 54. Type the above code in _App.js_ and save it  
---
![image](https://user-images.githubusercontent.com/40828825/137172065-afafc6f3-f3eb-46f6-8dfa-31be6e2c1c70.png)
#### 55. Go to the User Pools Dashboard  
#### 56. Click on `General settings`
#### 57. Copy the _Pool Id_
#### 58. Paste it in _UserPoolId of the App.js_ file
---
![image](https://user-images.githubusercontent.com/40828825/137172090-10f61166-0398-4bd4-b647-6c729c086560.png)
#### 59. Click on `App clients` on the left pane  
#### 60. Copy the _App client id_
#### 61. Paste it in _ClientId of the App.js_ file
---
```
Hasan-iMac:my-app hsa$ cd my-app
```
#### 62. Go back to the Mac terminal  
#### 63. Start the react application by typing the above command
---
![image](https://user-images.githubusercontent.com/40828825/137172163-73b9d30e-1403-4190-85d0-d700db96a904.png)
#### 64. Go to the browser to check the code running correctly  
---
![image](https://user-images.githubusercontent.com/40828825/137172184-63522a58-f96f-4be4-a82f-3632410b70e3.png)
#### 65. Go to the browser  
#### 66. Refresh the page
#### 67. Right click on the page and choose _Inspect_
#### 68. Click on `Sign Up`
---
![image](https://user-images.githubusercontent.com/40828825/137172210-a47c763b-497a-45c0-af54-0b7cb8e4816e.png)
#### 69. See the console and "Submitted…" message  
---
![image](https://user-images.githubusercontent.com/40828825/137172251-d56ffa21-cd3b-4954-81e5-83341c18ac6a.png)
#### 70. Enter an email and password  
#### 71. Click on `Sign Up`
---
![image](https://user-images.githubusercontent.com/40828825/137172275-1d992a7a-6b14-4644-8479-626bb05a087e.png)
#### 72. Go to the console and see the password is not a valid one  
#### 73. [_We have defined the password policy while creating the user pool above._]
---
![image](https://user-images.githubusercontent.com/40828825/137172300-2ea21f37-64b1-4b59-a5f3-28412a2c7b51.png)
#### 74. Enter a valid email and password  
#### 75. Click on `Sign Up`
---
![image](https://user-images.githubusercontent.com/40828825/137172319-e9b5d3df-f375-40a1-ac28-6daa9c24dc3a.png)
#### 76. Go to the console and see the password is a valid one  
---
![image](https://user-images.githubusercontent.com/40828825/137172342-f9be4355-68f0-459c-a428-58aa218e4133.png)
#### 77. Go to the User Pools Dashboard  
#### 78. Click on `Users and groups`
#### 79. Click on refresh on the right top [_The user is not yet confirmed._]
---
![image](https://user-images.githubusercontent.com/40828825/137172369-a48f5830-1cd2-4077-9ffa-fd4e206a1987.png)
#### 80. Check your email inbox  
#### 81. Click on `Verify Email`
---
![image](https://user-images.githubusercontent.com/40828825/137172407-94dce735-942a-4184-b734-c284af1fd57c.png)
#### 82. See the opening page of confirmation and the Amazon Cognito domain in the URL  
---
![image](https://user-images.githubusercontent.com/40828825/137172434-66a9d565-7bae-4fd8-a0ec-066abe1c9ab4.png)
#### 83. Go to the User Pools Dashboard  
#### 84. Click on `Users and groups`
#### 85. Click on refresh on the right top [_The user is now confirmed._]
---
  
