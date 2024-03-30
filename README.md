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
## Install Java
```
sudo apt install default-jre
```
Check Java version
java -version

## Install Jenkins
```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install Jenkins
```

## Create a new pipeline project in Jenkins

Install Docker
Install Docker compose
Create credentials for Docker hub 
Give permission to Jenkins user for Docker

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
