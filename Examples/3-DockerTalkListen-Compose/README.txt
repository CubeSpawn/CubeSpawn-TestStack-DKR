This Example uses docker-compose to create 3 instances of the ros tutorial image with different run time parameters to create a roscore-talker-listener instance

You must first insure that docker-compose is installed

Instructions are here:
https://docs.docker.com/compose/install

Once docker-compose is installed and tested, do the following:

If you have run the other examples you will have a docker image tagged as ros:ros-tutorials

If you are running this tutorial first, you will need to clone the git folder with the correct Dockerfile:

cd ~

git clone https://github.com/CubeSpawn/CubeSpawn-TestStack-DKR.git

cd ~/CubeSpawn-TestStack-DKR/Examples/DockerTalkListen-discrete/rosmaster

docker build -t ros:ros-tutorials .

once this completes:

cd ~/CubeSpawn-TestStack-DKR/Examples/3-DockerTalkListen-Compose

docker-compose up

to shut down the example 
ctrl-c 

You now have a composite instance of the ros:ros-tutorials image running as all 3 terminals shown in the previous examples.


