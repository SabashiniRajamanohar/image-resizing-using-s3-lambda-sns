# Automated Image Resizing and Transfer System Using AWS Services

## Project Description:
This project focuses on building an automated system for image processing and management within the AWS ecosystem. The goal is to streamline the handling of images by automatically resizing them and transferring them to a designated storage location while keeping stakeholders informed through notifications. Key AWS services, such as Lambda, S3, and SNS, are used to orchestrate this workflow.

## Key Features:
1. Image processing automation: Automatically resize and optimize images upon upload.
2. Secure storage: Store processed images in a secure and reliable S3 bucket.
3. Real-time notifications: Receive immediate updates about image processing via SNS.
4. Scalable architecture: Design for scalability to handle image processing demands.
5. Cost-efficient solution: Leverage AWS serverless technologies to minimize operational costs.

## Overview :

![a1](https://github.com/itz-mathesh/image-resizing-using-s3-lambda-and-sns/assets/144098846/d806e90a-365e-4f59-a6ac-2606c74b79e3)






## Steps :
### Step 1 :
### Creating Source and Designation s3 Buckets :

1. Navigate to the S3 Console.
2. Follow the Outlined Steps below.
<img width="1433" alt="Screenshot 2025-05-20 at 13 49 05" src="https://github.com/user-attachments/assets/aacda28e-df40-4560-846a-42b6893f5527" />

<img width="1433" alt="Screenshot 2025-05-20 at 13 52 57" src="https://github.com/user-attachments/assets/652a8055-ec9f-4353-b6a4-dc7257cbb8f2" />

<img width="1433" alt="Screenshot 2025-05-20 at 13 51 58" src="https://github.com/user-attachments/assets/f45c395e-8b1b-43d6-b613-13f3cea48389" />

3. Create the destination bucket using the same steps and name it with a unique name.
   
<img width="1433" alt="Screenshot 2025-05-20 at 13 55 03" src="https://github.com/user-attachments/assets/abb5d710-eba3-48b6-a381-f241399d3042" />

4. As you can see above , I created two buckets one is Source bucket and another one is Destination bucket.

### Step 2 :
### Creating the SNS Notification :

1. Navigate to the SNS console.
2. Follow the Outlined Steps below.

<img width="1153" alt="Screenshot 2025-05-20 at 13 56 50" src="https://github.com/user-attachments/assets/74cacc56-97ed-4c65-bc05-7bec56f9c472" />

<img width="1430" alt="Screenshot 2025-05-20 at 13 57 14" src="https://github.com/user-attachments/assets/69a68975-a9dc-47bd-8771-bad73cc9d370" />

<img width="1430" alt="Screenshot 2025-05-20 at 13 57 54" src="https://github.com/user-attachments/assets/fa70062e-ef54-42cd-b019-c11567735360" />

<img width="1430" alt="Screenshot 2025-05-20 at 13 58 23" src="https://github.com/user-attachments/assets/011bfbfe-7b35-453c-8c84-2eda9233be7e" />

<img width="1430" alt="Screenshot 2025-05-20 at 13 59 51" src="https://github.com/user-attachments/assets/d6e4398f-2252-4427-bee8-68f6fbaf2afa" />

3. Scroll down and Click "Create subscription" <br>
4. After this , you will receive some mail for Subscription Confirmation and you have to confirm that.<br>
5. You can use any other protocols also like SQS, HTTP, SMS etc .,<br>

<img width="905" alt="Screenshot 2025-05-20 at 14 00 56" src="https://github.com/user-attachments/assets/fc31224c-caf6-45d8-bf4d-3acc20a9425d" />

<img width="542" alt="Screenshot 2025-05-20 at 14 01 20" src="https://github.com/user-attachments/assets/bf73f034-1b5a-4bec-84b1-a95a132be3d0" />

### Step 3 :
### Creating the Lambda :

1. Navigate to the Lambda Console.
2. Follow the Outlined steps below.
   
<img width="1085" alt="Screenshot 2025-05-20 at 14 02 30" src="https://github.com/user-attachments/assets/ea319cf9-2dc9-4a2e-aa7b-4476e69db822" />

<img width="1171" alt="Screenshot 2025-05-20 at 14 03 36" src="https://github.com/user-attachments/assets/da3f6fc9-5fa5-4aec-a3b9-f907699ac069" />

3. Now replace the default code with the image-resizing-s3.py and deploy the changes , Don't test the code now we have to do some more actions before testing.

<img width="1411" alt="Screenshot 2025-05-20 at 14 04 22" src="https://github.com/user-attachments/assets/97be6047-23a2-4ad6-9674-b37990eccd20" />

<img width="1411" alt="Screenshot 2025-05-20 at 14 05 35" src="https://github.com/user-attachments/assets/45f5da04-937c-4e5f-8dc2-7765a153bb9a" />

<img width="1357" alt="Screenshot 2025-05-20 at 14 07 17" src="https://github.com/user-attachments/assets/fe45cef4-c872-40b7-8003-69fa5e66e6a9" />

<img width="1359" alt="Screenshot 2025-05-20 at 14 25 40" src="https://github.com/user-attachments/assets/6b040cbf-86cf-4dda-860f-dfe4e7c020c8" />

<img width="1417" alt="Screenshot 2025-05-20 at 14 26 23" src="https://github.com/user-attachments/assets/f36db954-52d0-4789-b9af-a4f237802dd8" />

4. After that , We have to give some permission for our Lambda Function to do our process (resizing) , For that navigate to the IAM Console and follow the below steps.

<img width="1170" alt="Screenshot 2025-05-20 at 14 29 18" src="https://github.com/user-attachments/assets/5135c325-33ae-4ee0-8a44-6da8972228b0" />

<img width="1424" alt="Screenshot 2025-05-20 at 14 30 48" src="https://github.com/user-attachments/assets/90dc4d5c-5ce8-4498-9011-24d263cb434b" />

<img width="1366" alt="Screenshot 2025-05-20 at 14 31 26" src="https://github.com/user-attachments/assets/4ade66bb-99ed-4769-8e24-43957d55aebd" />

5. Now navigate to the Lambda Console and follow the steps below.

6. Now we have to trigger the function.

<img width="1185" alt="Screenshot 2025-05-20 at 14 32 16" src="https://github.com/user-attachments/assets/e0592d1b-a1ac-4452-aa20-d54a29f22e53" />

<img width="1170" alt="Screenshot 2025-05-20 at 14 33 39" src="https://github.com/user-attachments/assets/fd321d6c-e84d-42a7-bdd4-5eb059045d09" />

<img width="1177" alt="Screenshot 2025-05-20 at 14 34 28" src="https://github.com/user-attachments/assets/ab5d5d3a-8c85-40a4-8977-9ce7bebed251" />

7. Now we have to go to code section , and scroll down to  layers.<br>
8. We have to add layer .<br>
9. May be you can think , why ?<br>
10. It's because for resize the image we upload in our source S3 bucket , We need a python library called pillow in our code to resize the image . We can manually add Pillow library also, But it's very time consuming and you have to do lot more , Instead of manually adding pillow library we are going to use layers for Some easy action.<br>
11. Follow the outlined Steps below.

<img width="1196" alt="Screenshot 2025-05-20 at 14 36 06" src="https://github.com/user-attachments/assets/1db68abe-516b-480b-897a-750e406fb123" />

<img width="1196" alt="Screenshot 2025-05-20 at 14 52 52" src="https://github.com/user-attachments/assets/d2e4799a-56f8-4ad6-85be-798ee30b5133" />

12. After done all the actions above , now we can test our code.

<img width="701" alt="Screenshot 2025-05-27 at 19 50 25" src="https://github.com/user-attachments/assets/2fc62e0b-7370-4131-80ee-c33f0adc2e4d" />
<img width="757" alt="Screenshot 2025-05-27 at 18 59 20" src="https://github.com/user-attachments/assets/8087c240-e1cc-4c35-a190-c554f596fa52" />

13. It runs successfully but return some error because we still not upload the images in S3 yet.

### Step 4 :
### Results :

1. Navigate to the S3 Console.
2. Upload Some images in  Source Bucket.

<img width="1404" alt="Screenshot 2025-05-20 at 15 09 19" src="https://github.com/user-attachments/assets/0f2dcb31-c424-4379-929b-d9f559d76033" />

<img width="1404" alt="Screenshot 2025-05-20 at 15 10 44" src="https://github.com/user-attachments/assets/cdb440a1-c291-4dc5-89e6-d5fefc83dfdc" />

<img width="1384" alt="Screenshot 2025-05-27 at 19 09 20" src="https://github.com/user-attachments/assets/612a049c-3af1-4e2b-b52e-faa1ff8c52af" />


### It Successfully resized the Image.


