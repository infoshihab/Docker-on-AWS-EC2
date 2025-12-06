# Docker-on-AWS-EC2
#Use below commands to install Docker on AWS EC2:

sudo apt-get update
sudo apt-get install docker.io -y
sudo systemctl start docker
sudo docker run hello-world
docker ps
sudo chmod 666 /var/run/docker.sock
sudo systemctl enable docker
docker --version


#Normal Docker Command
docker ps -a
docker images
docker rm container_id --> remove the image (Step -1)
docker rmi image_id --> delete the image (Step -2)

TrubleSooting Commands

dcoker logs Container_ID

docker exec -it Container_ID/bin/bash
(^ we use this command for running container , for running additional command we use that )
(^Allow us to access the terminal or shall of our running container)


#Docker network

docker network ls
docker network rm NETWORK_ID (for delete)
docker network create NAME


#Docker Compose

------------***-------------
file name --> mongo.yaml
version: "3.8"

services:
 mongo:
   image: mongo
   ports:
   - 27017:27017
   environment:
   MONGO_INITDB_ROOT_USERNAME:demo_admin
   MONGO_INITDB_ROOT_PASSWORD:password



 mongo-express:
  image: mongo-express
  ports:
  - 8081:8081
  environment:
   ME_CONFIG_MONGODB_ADMINUSERNAME:demo_admin
   ME_CONFIG_MONGODB_ADMINPASSWORD:password
   ME_CONFIG_MONGODB_URL: mongodb://demo_admin:password@mongo:27017/


>>>>>>>>>>>RUN>>>>>>>>>>>>
docker compose -f mongo.yaml up -d
docker compose -f mongo.yaml down 

-------------***------------------



#Dockerize app
file name --> Dockerfile

FROM node

ENV MONGO_DB_USERNAME=demo_admin \
    MONGO_DB_PWD=password123


RUN mkdir -p demo/nodeapp

COPY . /demo/nodeapp

RUN npm install

CMD ["node"."/demo/nodeapp/server.js",]


--------***--------
docker built -t (APP NAME)nodeapp:(VERSION)1.0 .THE_FILE_PATH 


----------------------------*****************-----------------
docker run -it -v /Users/dekstop/data:/test/data ubuntu
ls
cd data
touch index.html


where the key run that terminal
after the terminal run , run the ssh client 3 and the example command




demo_admin
portfolio pass
