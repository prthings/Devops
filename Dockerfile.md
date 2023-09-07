## Docker Install in Ec2 Instance using Amazon Linux 2 

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


## Docker Commands

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


## Management Commands:
  builder     Manage builds
  buildx*     Docker Buildx (Docker Inc., v0.10.4)
  compose*    Docker Compose (Docker Inc., v2.17.2)
  config      Manage Docker configs
  container   Manage containers
  context     Manage contexts
  image       Manage images
  manifest    Manage Docker image manifests and manifest lists
  network     Manage networks
  node        Manage Swarm nodes
  plugin      Manage plugins
  secret      Manage Docker secrets
  service     Manage services
  stack       Manage Docker stacks
  swarm       Manage Swarm
  system      Manage Docker
  trust       Manage trust on Docker images
  volume      Manage volumes

  ## Commands:
  attach      Attach local standard input, output, and error streams to a running container
  build       Build an image from a Dockerfile
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  events      Get real time events from the server
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  history     Show the history of an image
  images      List images
  import      Import the contents from a tarball to create a filesystem image
  info        Display system-wide information
  inspect     Return low-level information on Docker objects
  kill        Kill one or more running containers
  load        Load an image from a tar archive or STDIN
  login       Log in to a Docker registry
  logout      Log out from a Docker registry
  logs        Fetch the logs of a container
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  ps          List containers
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  rmi         Remove one or more images
  run         Run a command in a new container
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  search      Search the Docker Hub for images
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  version     Show the Docker version information
  wait        Block until one or more containers stop, then print their exit codes
