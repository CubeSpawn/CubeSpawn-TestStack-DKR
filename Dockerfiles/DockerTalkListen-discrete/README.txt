This performs the same talker listener setup using docker images

There are many ways to install docker, but this is the quickest I've found

wget -qO- https://get.docker.com/ | sh

If you do not want to type "sudo" before every docker command
add your user to the docker group

sudo usermod -aG docker <your-user>

you must log out and back in for this to take effect

to test your installation 

docker run hello-world

next, we'll use the files found in ~/CubeSpawn-Docker/rostutorials

cd CubeSpawn-Docker/rostutorials

docker run -t ros:ros-tutorials .

create a docker network

docker network create testnet

run the roscore container 
docker run -it -–rm --name master -–net=testnet ros:ros-tutorials roscore

open a new terminal
run the talker container

docker run -it --rm --name talker --net=testnet --env ROS_HOSTNAME=talker --env ROS_MASTER_URI=http://master:11311 ros:ros-tutorials  rosrun roscpp_tutorials talker

one more terminal

docker run -it --rm --name listener --net=testnet --env ROS_HOSTNAME=listener --env ROS_MASTER_URI=http://master:11311 ros:ros-tutorials  rosrun roscpp_tutorials listener

 





