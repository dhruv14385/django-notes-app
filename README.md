# Simple Notes App
In this hands-on exercise, I will create a CI/CD pipeline project in Jenkins. A docker image will be created from a dockerfile. It will be pushed on to the Dockerhub. A container with application will be built from the image. I will use GITScm Polling for continuous integration and webhooks for continuous deployment. I have done this hands-on using EC2 Ubuntu instance. Please see following steps for explanation.  

## Get updates  
```
sudo apt update
```

## Clone the repository  
```
git clone https://github.com/dhruv14385/django-notes-app.git
```
Change directory to django-notes-app
```
cd django-notes-app/
```
•	Install Java version 11  
```
sudo apt install openjdk-11-jre
```

•	Open port 8080 to your IP on SG.  
•	Install Jenkins. Enter following commands one after other.   
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
•	Confirm that Jenkins is running with following command.  
```
service jenkins status
```

## Create a new pipeline project in Jenkins

Install Docker
Install Docker compose
Create credentials for Docker hub 
Give permission to Jenkins user for Docker

## Create credentials for Dockerhub
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/7fdbe137-daf8-4c13-b24d-044b61ac14c9)

## Create Jenkins pipeline project with following configurations
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/841788c4-4c45-42a2-98f2-c8178fa89fca)
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/98ca5838-c1c3-4204-8805-a58d90867836)
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/2bebe167-0aed-4081-a308-6f7a86bdb4ee)
![image](https://github.com/dhruv14385/django-notes-app/assets/83332524/91520d39-7127-4fea-abae-aa8caca4f694)






## Installation
1. Clone the repository
```
git clone https://github.com/LondheShubham153/django-notes-app.git
```

2. Build the app
```
docker build -t notes-app .
```

3. Run the app
```
docker run -d -p 8000:8000 notes-app:latest
```

## Nginx

Install Nginx reverse proxy to make this application available

`sudo apt-get update`
`sudo apt install nginx`
