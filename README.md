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





demo_admin
portfolio pass
