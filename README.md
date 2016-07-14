CubeSpawn Control Framework 

Tests and examples to get the general process together - then we'll buildout shell docker and docker-compose files to assemble the control and simulation nodes

***Updated 07/14/2016***

As implemented via Docker microservices architecture

Assumptions: all the examples were created either directly on a 14.04 LTS Ubuntu install, or via SSH to same.

Status:

Instructions for the ROS talker/listerner tutorial run on a conventional Ubuntu install -tested, working

Instructions for the ROS talker/listener tutorial run as 3 docker instances off one image using the Docker network -tested, working

Intructions for the ROS talker/listener tutorial running from a docker-compose file works - completed 7/14/2016

Next steps:

A roscore/Rviz environment will be built, and the first machine model will be added, leading towards a software based model for virtual design.

A web centric application server for both x86 and ARM architecture.

Modules for Machinekit, Octoprint, ROS on arm controllers with an added MTConnect Agent

