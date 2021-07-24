https://drive.google.com/file/d/1-u_Q-qh5t38e7imxDg97kUb0T4fX9FV4/view?usp=sharing
## REFER DOCKER IMAGE:-  docker pull harshal769/guieditor <br>
# GUI-in-Docker
GUi in docker running (Graphical User Interface) in Docker 

## Step Should be followed
 1) Check docker installed or not systemctl status docker in (Linux base OS) and in windows Run docker version

 2) To check images :- docker images 

 3) If you dont have any images, pull image from hub.docker.com <br>
   To download/pull image:-  docker pull centos:latest

 4) To create a container :  docker run -it --name "CONTAINER_NAME" centos:latest<br><br>
 Step inside the Docker 
 - step 1:- rpm -q gedit
 - step 2:- yum install gedit -y 
 - step 3:- gedit (But it fails, and throws an warning - no display) 
 - exit 
 
 5) To make new directory:-  mkdir guidock/
 
 ## Create Dockerfile
 
 6) vim Dockerfile
 
 FROM centos:latest
 
 RUN yum install gedit -y

 CMD gedit
 
 7) docker build -t guieditor:v1 . ("This will create a image of guieditor with version v1")
 
 8) docker images ("you will see guieditor:v1 image")
 
 9) docker container run -it --name gui --env="DISPLAY" --net=host guieditor:v1 <br>
 
## <b> EXPLAINATION  </b> <br>
- --env="DISPLAY" : It provides the display environment to the container.
- --net=host : It will provide the x-server host of the base OS 

This helps in running/launching the GUI containers.

