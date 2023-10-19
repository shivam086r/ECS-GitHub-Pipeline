# nodejs-deployment-on-dockerhub-via-dockerfile

### docker installation###

sudo apt update

sudo apt upgrade

####Install Required Dependencies####

sudo apt install apt-transport-https ca-certificates curl software-properties-common

###Add Docker Repository###

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

echo "deb [signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

 ####Install Docker ###
 
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io

sudo systemctl enable docker
sudo systemctl start docker

sudo docker --version

### Building and pushing image ####
sudo docker build -t srahangdale/node-docker-app .

sudo docker login

sudo docker push srahangdale/node-docker-app

###Pulling and Running Image###
docker pull image-name

docker run -p 8000:3000 -d srahangdale/node-docker-app

http://localhost:8000


