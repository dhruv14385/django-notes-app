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
