## Use Kinesis Data Firehose and Kinesis Data Analytics  
<br><br>   

![image](https://user-images.githubusercontent.com/40828825/137188200-e6c2a813-f495-4623-a5c7-92fbebc9eaa1.png)
#### 1. Go to the AWS console  
#### 2. Click on `Kinesis under Analytics`
---
![image](https://user-images.githubusercontent.com/40828825/137188229-f44f7df7-5b77-42e1-85a7-726975dfa57e.png)
#### 3. Choose _Kinesis Data Firehouse_  
#### 4. Click on `Create delivery stream`
---
![image](https://user-images.githubusercontent.com/40828825/137188253-ee5874e5-26d8-4c7b-856b-16dacf604979.png)
#### 5. Enter a delivery stream name (_captains-kfh_)  
#### 6. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137188278-7161a600-1550-474b-8c96-73574996dae2.png)
#### 7. Choose a source (_Direct PUT or other sources_)  
#### 8. Click on `Next`
---
![image](https://user-images.githubusercontent.com/40828825/137188301-63cf60d9-1571-401c-9518-a7cfdbef1ff4.png)
#### 9. Disable data transformation  
#### 10. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137188322-11cb8ac6-3c51-4d4c-86cd-2ff29404e4dc.png)
#### 11. Disable record format conversion  
#### 12. Click on `Next`
---
![image](https://user-images.githubusercontent.com/40828825/137188342-c3c9363f-e390-4c79-88d0-85c0ce78b643.png)
#### 13. Choose a destination (_Amazon S3_)  
#### 14. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137188362-29110079-d08e-4a01-9df2-f09cdaf31ef5.png)
#### 15. Click on `Create new`  
---
![image](https://user-images.githubusercontent.com/40828825/137188382-504ad52d-bd7b-4f70-b503-59ccb1805bf4.png)
#### 16. Enter a S3 bucket name (_demo-firehose-bucket-s3_)  
#### 17. Choose a region (_Ireland_)
#### 18. Click on `Create S3 bucket`
#### 19. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137188405-aff33fe7-51d4-40ae-81aa-a98974077c1c.png)
#### 20. Click on `Next`  
---
![image](https://user-images.githubusercontent.com/40828825/137188421-098fc681-767c-4472-9412-964a583164bf.png)
#### 21. Enter the buffer size (_1_)  
#### 22. Enter the buffer interval (_60_)
#### 23. [_Once the data stream reaches either of the threshold, it sends the data to the destination store._]
#### 24. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137188458-9937b026-a3ab-455d-a385-b6b5155cf1be.png)
#### 25. _Disable S3 compression_ for this exercise  
#### 26. _Disable S3 encryption_
#### 27. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137188485-dfc00670-be55-4097-a982-8b0b38bd520e.png) 
#### 28. Keep error logging enabled  
#### 29. Click on `Add tag`
#### 30. Enter tag(s)
#### 31. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137188509-19ac2ef7-d348-4c0c-b78c-a99e02701389.png)
#### 32. Select an IAM role (_Create or update IAM role KinesisFirehoseServiceRole-captains--kfh-eu-west-1-****_)  
#### 33. Click on `Next`
---
![image](https://user-images.githubusercontent.com/40828825/137188606-91460b92-d873-44cf-8bb9-a35628018579.png)
#### 34. Click on `Create delivery stream`  
---
![image](https://user-images.githubusercontent.com/40828825/137188655-63ebbba3-4c58-46bf-9c83-9b9b4534a923.png)
#### 35. Launch an EC2 instance as described in the above lab  
#### 36. SSH into the EC2 instance
---
```
[root@ip-172-31-38-89 ec2-user]# yum install python3-pip
[root@ip-172-31-38-89 ec2-user]# pip3 install discord.py
[root@ip-172-31-38-89 ec2-user]# pip3 install boto3
[root@ip-172-31-38-89 ec2-user]# pip3 install faker
[root@ip-172-31-38-89 ec2-user]# pip3 install awscli
```
#### 37. Install python, pip, discord, boto3, faker, and awscli on EC2 instance  
---
```
[root@ip-172-31-38-89 ec2-user]# nano space_captains.py
```
#### 38. Open a new file (space_captains.py) in the nano editor  
---
```
   "Christopher Pike",
    "Creideiki",
    "David Bowman",
    "The Doctor",
    "Exeter",
    "John Robinson",
    "Adama",
    "Khan Noonien Singh"
];

record = {}
while True:

    record['user'] = fake.name();
    if random.randint(1,100) < 5:
        record['favoritecaptain'] = "Dex";
        record['rating'] = random.randint(6000,9000);
    else:
        record['favoritecaptain'] = random.choice(captains);
        record['rating'] = random.randint(1, 1000);
    record['timestamp'] = time.time();
    response = client.put_record(
        DeliveryStreamName=DeliveryStreamName,
        Record={
            'Data': json.dumps(record)
        }
    )
    print('Record: \n' + str(record));
```
#### 39. Copy the above code and paste it in _space_captains.py_, and save and exit  
---
```
[root@ip-172-31-38-89 ec2-user]# aws configure
AWS Access Key ID [None]: ***
AWS Secret Access Key [None]: ***
Default region name [None]: eu-west-1
Default output format [None]: json
```
#### 40. Enter programmatic access credentials  
---
```
[root@ip-172-31-38-89 ec2-user]# python3 space_captains.py
```
#### 41. Run the program for two minutes and then stop it  
---
![image](https://user-images.githubusercontent.com/40828825/137188912-20c01560-6bdc-4e6b-802c-b148965df3a0.png)
#### 42. Go back to the Amazon Kinesis Dashboard  
#### 43. Click on `Data Firehose`
#### 44. Choose the delivery stream (_captains-kfh_)
---
![image](https://user-images.githubusercontent.com/40828825/137188930-6b0aca2e-dae0-4cbc-9454-d5559676ac47.png)
#### 45. Click on `Details` tab  
#### 46. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137188956-9f48a2ea-785e-4219-867e-188ccf749a49.png)
#### 47. Click on the `S3 bucket (demo-firehose-bucket-s3)` to check if the files populate there  
---
```
[root@ip-172-31-38-89 ec2-user]# aws s3 sync s3://demo-firehose-bucket-s3/ .
download: s3://demo-firehose-bucket-s3/2020/10/11/18/captains-kfh-1-2020-10-11-18-09-45-02a4b5af-ab84-4127-a0f4-b50b75d1e1b1 to 2020/10/11/18/captains-kfh-1-2020-10-11-18-09-45-02a4b5af-ab84-4127-a0f4-b50b75d1e1b1
download: s3://demo-firehose-bucket-s3/2020/10/11/18/captains-kfh-1-2020-10-11-18-06-16-c5b038da-7c5e-4f8a-9e0d-3817dcd4b68e to 2020/10/11/18/captains-kfh-1-2020-10-11-18-06-16-c5b038da-7c5e-4f8a-9e0d-3817dcd4b68e
download: s3://demo-firehose-bucket-s3/2020/10/11/18/captains-kfh-1-2020-10-11-18-10-46-dbe923b6-8ae6-4ff6-b119-b7eb2d5fadae to 2020/10/11/18/captains-kfh-1-2020-10-11-18-10-46-dbe923b6-8ae6-4ff6-b119-b7eb2d5fadae
download: s3://demo-firehose-bucket-s3/2020/10/11/18/captains-kfh-1-2020-10-11-18-08-44-3ce6aaf7-8ddc-496a-9392-495950dd3d15 to 2020/10/11/18/captains-kfh-1-2020-10-11-18-08-44-3ce6aaf7-8ddc-496a-9392-495950dd3d15
```
#### 48. Sync the S3 bucket with the local file (_EC2 instance_)  
---
```
[root@ip-172-31-38-89 ec2-user]# tail -1 2020/10/11/18/captains-kfh-1-2020-10-11-18-08-44-3ce6aaf7-8ddc-496a-9392-495950dd3d15
```
#### 49. See the last line of the last file  
---
```
[root@ip-172-31-38-89 ec2-user]# python3 space_captains.py
```
#### 50. Restart the data stream  
---
![image](https://user-images.githubusercontent.com/40828825/137189099-31ada858-6d25-478b-b971-0714e9d1c7db.png)
#### 51. Go back to the Amazon Kinesis Dashboard  
#### 52. Click on `Data Analytics`
#### 53. Click on `Create application`
---
![image](https://user-images.githubusercontent.com/40828825/137189119-e598d175-b5e7-44b6-9124-cb4402263402.png)
#### 54. Enter an application name (_popular-space-captains_)  
#### 55. Enter a description (_popular-space-captains_)
#### 56. Choose the runtime (_SQL_)
#### 57. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137189140-2c86d893-5195-46e9-8675-d9ea54c313de.png)
#### 58. Click on `Add tag`  
#### 59. Enter tag(s)
#### 60. Click on `Create application`
---
![image](https://user-images.githubusercontent.com/40828825/137189157-99977da9-fa43-41c8-a5f8-c099b398a675.png)
#### 61. Click on `Connect streaming data`  
---
![image](https://user-images.githubusercontent.com/40828825/137189182-291e40fe-9b89-410a-938b-b6a10dbcddc9.png) 
#### 62. Select _Choose source_  
#### 63. Select the source (_Kinesis Firehouse delivery stream_)
#### 64. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137189202-7a689991-d8e2-43d2-9bc2-89a940f2923d.png)
#### 65. Select the Kinesis Firehose delivery stream (_captains-kfh_)  
#### 66. Disable record pre-processing
#### 67. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137189224-aaa575bb-7707-49d2-98ac-937543dd5122.png)
#### 68. Choose access permission (_Create/update IAM role_)  
#### 69. Click on `Discover schema`
#### 70. Scroll down
---
![image](https://user-images.githubusercontent.com/40828825/137189246-427b5c52-3ac1-4576-a6cb-b5edfe86d421.png)
#### 71. Click on `Save and continue`  
---
![image](https://user-images.githubusercontent.com/40828825/137189270-b4e4002a-0983-4c1d-8f76-a37170d0e777.png)
#### 72. Click on `Go to SQL editor`  
---
![image](https://user-images.githubusercontent.com/40828825/137189293-89296828-2055-41ed-afb4-56ffd910e2c9.png)
#### 73. Click on `Yes, start application`  
---
```
CREATE OR REPLACE STREAM "DESTINATION_CAPTAINS_SCORES" ("favoritecaptain" VARCHAR(32), average_rating INTEGER, total_rating INTEGER);

CREATE OR REPLACE  PUMP "STREAM_PUMP" AS INSERT INTO "DESTINATION_CAPTAINS_SCORES"

    SELECT STREAM "favoritecaptain", avg("rating") as average_rating, sum("rating") as total_rating
    FROM "SOURCE_SQL_STREAM_001"

    GROUP BY "favoritecaptain", STEP("SOURCE_SQL_STREAM_001".ROWTIME BY INTERVAL '1' MINUTE)
    ORDER BY STEP("SOURCE_SQL_STREAM_001".ROWTIME BY INTERVAL '1' MINUTE), sum("rating") DESC;
```
#### 74. Copy the above SQL code  
---
![image](https://user-images.githubusercontent.com/40828825/137189366-65e29c69-8106-48f2-b732-a896b514c78a.png) 
#### 75. Paste it in the SQL editor  
#### 76. Click on `Save and run SQL`
---
```
CREATE OR REPLACE STREAM "TEMP_STREAM" (
   "favoritecaptain" VARCHAR(16),
   "rating"        INTEGER,
   "ANOMALY_SCORE"  DOUBLE);

CREATE OR REPLACE STREAM "DESTINATION_SQL_STREAM" (
   "favoritecaptain" VARCHAR(16),
   "rating"        INTEGER,
   "ANOMALY_SCORE"  DOUBLE);

CREATE OR REPLACE PUMP "STREAM_PUMP" AS INSERT INTO "TEMP_STREAM"
SELECT STREAM "favoritecaptain", "rating", "ANOMALY_SCORE" FROM
  TABLE(RANDOM_CUT_FOREST(
    CURSOR(SELECT STREAM "favoritecaptain", "rating" FROM "SOURCE_SQL_STREAM_001")
  )
);
-- Sort records by descending anomaly score, insert into output stream
CREATE OR REPLACE PUMP "OUTPUT_PUMP" AS INSERT INTO "DESTINATION_SQL_STREAM"
SELECT STREAM * FROM "TEMP_STREAM"
ORDER BY FLOOR("TEMP_STREAM".ROWTIME TO SECOND), ANOMALY_SCORE DESC;
```
#### 77. Copy the above SQL code  
---
![image](https://user-images.githubusercontent.com/40828825/137189434-f3664561-5926-4841-bea3-1d0de4523de5.png)
#### 78. Paste it in the SQL editor  
#### 79. Click on `Save and run SQL`
---

