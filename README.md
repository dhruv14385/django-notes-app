# Simple Notes App
In this hands-on exercise, I will create a CI/CD pipeline project in Jenkins. A docker image will be created from a dockerfile. It will be pushed on to the Dockerhub. A container with application will be built from the image. I will use GITScm Polling for continuous integration and webhooks for continuous deployment. I have done this hands-on using EC2 Ubuntu instance. Keep the ports 8000 and 8080 accessible for all the traffic for the purpose of this hands-on. Please see following steps for explanation.  

Get updates  
```
sudo apt update
```

Clone the repository  
```
git clone https://github.com/dhruv14385/django-notes-app.git
```
Change directory to django-notes-app
```
cd django-notes-app/
```
Install Java version 11  
```
sudo apt install openjdk-11-jre
```

Install Jenkins. Enter following commands one after other.   
```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
 https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
```
```
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
/etc/apt/sources.list.d/jenkins.list > /dev/null
```
```
sudo apt-get update
sudo apt-get install jenkins
sudo systemctl enable jenkins
sudo systemctl start jenkins
```
Confirm that Jenkins is running with following command.  
```
service jenkins status
```

Create a new pipeline project in Jenkins.  
Make sure that name of the project does not have any space.

## Create credentials for Dockerhub
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/7fdbe137-daf8-4c13-b24d-044b61ac14c9)

## Create Jenkins pipeline project with following configurations
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/841788c4-4c45-42a2-98f2-c8178fa89fca)  
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/98ca5838-c1c3-4204-8805-a58d90867836)  
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/2bebe167-0aed-4081-a308-6f7a86bdb4ee)  
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/91520d39-7127-4fea-abae-aa8caca4f694)  


## Install Docker
```
sudo apt install docker.io
```
Install docker compose
```
sudo apt-get install docker-compose
```
Build now and it will fail but it's ok. Go to Console output and copy the path of Jenkins workspace as shown below
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/90b309cd-62a8-4a9f-9099-b9a7d8d86fbe)  

Change directory to that one and add user 'jenkins' to docker
```
sudo usermod -a -G docker jenkins
```
Reboot the instance
```
sudo reboot
```
After rebooting, log in to Jenkins again and build again. This time, it should be successful. You can check the app running on port 8000.  
Add Webhook for continuous deployment.  
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/630346b3-548c-4331-9b70-828276f2df1f)  

To check if the webhook is working or not, make any change to index,html located at mynotes/build/index.html in this repository. The build should start as soon as you commit any change.




