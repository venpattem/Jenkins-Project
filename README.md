# Jenkins-project 🚀
Brief about Jenkins and how to (build end to end pipelines)?
Firstly, we will launch EC2 instance,then install jenkins and use docker as agent, setup CI/CD and deploy application.

# AWS EC2 instance
* Go to AWS console
* Instances (running)
* Launch EC2 instances
![image](https://github.com/pooja-bhavani/Jenkins-project/assets/147735975/e67db38f-a7ac-4a84-8dcc-4f5a06d9e343)

# Install Jenkins.
# Run the below commands to install Java and Jenkins

Install java

````
sudo apt update
sudo apt install openjdk-17-jre
````
Verify weather Java is Installed
```
java --version
```
````
curl -fsSL https://pkg.jenkins.io/debian/jenkins.io-2023.key | sudo tee \
  /usr/share/keyrings/jenkins-keyring.asc > /dev/null
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
````
# Note: By default, Jenkins will not be accessible to the external world due to the inbound traffic restriction by AWS.Open port 8080 in the inbound traffic rules as show below.
* EC2 > Instances > Click on
* In the bottom tabs -> Click on Security
* Security groups
* Add inbound traffic rules (just allow TCP 8080).

![image](https://github.com/pooja-bhavani/Jenkins-project/assets/147735975/cb8ac6b6-bdd6-4432-84b7-49760df846c2)

Login to Jenkins using the URL:
![image](https://github.com/pooja-bhavani/Jenkins-project/assets/147735975/dc3df650-5f8a-4655-83e5-5641eb12c25c)
 Click on Install suggested plugins
 ![image](https://github.com/pooja-bhavani/Jenkins-project/assets/147735975/3b7ca4f1-bb95-4a40-baf7-9d8f0294876c)
 Wait for the Jenkins to Install suggested plugins
![image](https://github.com/pooja-bhavani/Jenkins-project/assets/147735975/c5fb048f-58cc-44dc-8d3b-2ddad7c5520f)
Now, create First Admin User 
![image](https://github.com/pooja-bhavani/Jenkins-project/assets/147735975/8ab3f348-553d-4159-bfa0-a0601f5f397c)
Jenkins Installation is Successful. You can now starting using the Jenkins
![image](https://github.com/pooja-bhavani/Jenkins-project/assets/147735975/d76089a9-d643-4556-a7ae-766d6f684b24)
# Docker Installation
```
sudo apt update
sudo apt install docker.io
```
 # Grant Jenkins user and Ubuntu user permission to docker deamon.
```
sudo su - 
usermod -aG docker jenkins
usermod -aG docker ubuntu
systemctl restart docker
```
![image](https://github.com/pooja-bhavani/Jenkins-project/assets/147735975/f7d1959d-5cc0-4945-8319-ac04b353ccfe)
# Install the Docker Pipeline plugin in Jenkins:
 * Log in to Jenkins.
 * Go to Manage Jenkins -> Manage Plugins.
 * In the Available tab, search for "Docker Pipeline".
 * Select the plugin and click the Install button.
 * Restart Jenkins after the plugin is installed.
![image](https://github.com/pooja-bhavani/Jenkins-project/assets/147735975/5731e405-e670-4e9d-858e-bc26a3357260)

















