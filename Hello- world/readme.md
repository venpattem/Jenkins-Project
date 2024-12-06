![image](https://github.com/user-attachments/assets/008db4c5-55c2-43db-920b-81fa27c81030)
# Create a freestyle pipeline to print "Hello World!!"
1. Launch your instance in AWS and set up the Jenkins server on your instance using these commands
![image](https://github.com/user-attachments/assets/04cf3329-869a-4e70-8b79-b55dae231080)
````
$ sudo apt-get update
$ sudo apt-get install jenkins
````

```
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```
![image](https://github.com/user-attachments/assets/c4527d8f-6f7f-4251-a9cc-4e086d14c031)
Allow inbound traffic on port 8080 for Jenkins in the AWS security group.
![image](https://github.com/user-attachments/assets/d0abad91-c7f1-4f25-8b32-c0cc425eed9a)

Open a new tab and enter your AWS IP address followed by ':8080'. It will prompt you for a password to access your Jenkins server. Use this command to retrieve the password.
![image](https://github.com/user-attachments/assets/75948dce-51cb-45d7-b817-6f7dc443fa1b)
![image](https://github.com/user-attachments/assets/b9ffa4d3-91d4-4183-9a48-d329b8a5ae1d)

After pasting your password, click on 'Install Plugins' to initiate the plugin installation. Create your Jenkins account and the Jenkins dashboard will open.
![image](https://github.com/user-attachments/assets/8284e22a-0834-4704-83e4-7c2a2439d5e7)

Follow these steps to create a freestyle pipeline that prints 'Hello World!!'.
Step 1: Click on a new item, and then you will have a page on which you have to give your name to your job and choose ‘freestyle project’ or any other option according to your need and then click ‘ok’.
![image](https://github.com/user-attachments/assets/7c49d201-6f99-4f41-9c68-3c1ac188573d)

Step 2: After this, you will reach a page where you have different options(like build, build triggers, and source code management) that help you manage your job.
Step 3: Now, we will give some description of our job.
![image](https://github.com/user-attachments/assets/292101e0-0ffd-41df-bb04-7db03aba300a)

Step 4: Now, you have to provide which source code management tool you are using since here we are not using anyone so will choose the ‘none’ option.
![image](https://github.com/user-attachments/assets/9d8e606a-d943-4d6d-8383-2b452e793cee)

Step 5: After this, if you want to give some triggers then you can choose accordingly even Jenkins provides us scheduled triggers. And you can choose to build an environment also accordingly. But, here we are making a simple job, so we are not using any triggers and build environment options.
Step 6: In the build section we have an option ‘Execute shell’ by which we can write some command or code.
![image](https://github.com/user-attachments/assets/c7c9bf51-930b-4164-ab53-8b81c28f032b)

```
echo "Hello friends this is my jenkins demo: %date : %time"
```
![image](https://github.com/user-attachments/assets/c4ca369f-16de-4789-9329-d6f68ac53fa2)
Then click apply and save. So, your job is created.

Step 7: Now, we will run it for which click the ‘build now’ option and a building history will be created then click on it.
![image](https://github.com/user-attachments/assets/b83fc37c-101a-4063-b283-a631ec12ca19)
![image](https://github.com/user-attachments/assets/ad28c944-eca9-4985-accd-a86f3059cb2c)






