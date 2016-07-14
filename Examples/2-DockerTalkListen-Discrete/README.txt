This performs the same talker listener setup given in example 1, but using docker images

There are many ways to install docker, but this is the quickest I've found

wget -qO- https://get.docker.com/ | sh

If you do not want to type "sudo" before every docker command
add your user to the docker group
...
    sudo usermod -aG docker <your-user>
...
you must log out and back in for this to take effect

to test your installation 

docker run hello-world

to run the examples, type or copy: 

cd ~

git clone https://github.com/CubeSpawn/CubeSpawn-TestStack-DKR.git

next, we'll use the files found in ~/CubeSpawn-TestStack-DKR/Examples/2-DockerTalkListen-Discrete/rosmaster

cd ~/CubeSpawn-TestStack-DKR/Examples/2-DockerTalkListen-Discrete/rosmaster

docker build -t ros:ros-tutorials .

cd create a docker network

docker network create testnet

run the roscore container in a new terminal
 
docker run -it -–rm --name master -–net=testnet ros:ros-tutorials roscore

open a new terminal

run the talker container:

docker run -it --rm --name talker --net=testnet --env ROS_HOSTNAME=talker --env ROS_MASTER_URI=http://master:11311 ros:ros-tutorials  rosrun roscpp_tutorials talker

one more terminal

docker run -it --rm --name listener --net=testnet --env ROS_HOSTNAME=listener --env ROS_MASTER_URI=http://master:11311 ros:ros-tutorials  rosrun roscpp_tutorials listener

 





