### Docker Install in Ec2 Instance using Amazon Linux 2 

Write docker-install.sh


`sudo yum update -y
sudo yum search docker
sudo yum info docker
sudo yum install -y docker
sudo systemctl enable docker.service
sudo systemctl start docker.service
sudo systemctl status docker.service
docker --version
sudo yum install git -y
sudo curl -L https://github.com/docker/compose/releases/download/1.22.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose`


### Docker Commands

    1  vi docker.sh
    2  cat docker.sh
    3  sh docker.sh
    4  docker --version
    5  docker images
    6  docker ps
    7  docker pull httpd
    8  docker images
    9  docker ps
   10  docker run -it -d httpd
   11  docker ps
   12  docker rm 54e573d87a13
   13  docker stop 54e573d87a13
   14  docker ps
   15  docker ps -a
   16  docker start 54e573d87a13
   17  docker ps
   18  docker rm 54e573d87a13
   19  docker stop 54e573d87a13
   20  docker rm 54e573d87a13
   21  docker ps -a
   22  docker images
   23  docker rm 76e5ad98b58e
   24  docker rmi 76e5ad98b58e
   25  history
   26  docker images
   27  docker pull httpd
   28  docker images
   29  docker run -it -d httpd
   30  docker ps
   31  docker commit 617d9b255a40 youraccout/ignite
   32  docker images
   33  docker push youraccout/ignite
   34  docker login
   35  docker push youraccout/ignite