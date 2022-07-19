# hello_world
help world docker file for Jenkins Pipeline

***HOW TO USE*** 

Run the Jenkins image locally, so first clone the repository: 
```
git clone https://github.com/DrKbts1/hello_world
```
Open the folder where Dockerfile for Jenkins is:
```
cd hello_worls/jenkins_setup
```
Build and run the docker image with following commands. Be sure docker is installed and /var/run/docker.sock exists on your host :
```
docker build -t jenkins-local:latest .
docker run -p 8080:8080 -v /var/run/docker.sock:/var/run/docker.sock jenkins-local:latest
```
Open in your browser localhost:8080
Create new item pipeline, select the source from git and put the *https://github.com/DrKbts1/hello_world* link to the source url. 
