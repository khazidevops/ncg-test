# ncg-test


bugzilla-testlink-docker-compose

How to install Docker

Visit Docker and get Docker up and running on your system. Optionally you could install Docker Compose to help with setting up a new container.

Remember to create the named volumes before running your services:

$docker volume create bugzilla-db-data

$docker volume create tl-mariadb-data

$docker volume create tl-testlink-data

How to build Bugzilla Docker image

To build a fresh image, just change to the directory containing the checked out files and run the below command:

$ docker-compose build

How to start Bugzilla and TestLink Docker image

To start a new container (or rerun your last container) you simply do:

$ docker-compose up

This will stay in the foreground and you will see the output from supervisord. You can use the -d option to run the container in the background.

To stop, start or remove the container that was created from the last run, you can do:

$ docker-compose stop $ docker-compose start $ docker-compose rm

How to access the Bugzilla and TestLink container

http://localhost/bugzilla

http://localhost:83/login.php?note=logout&viewer=

If you are still in the log screen press Ctrl + C just one time for graceful stop, two times to force stop

To stop all containers created by docker-compose, you need to go to the folder where docker-compose.yml is and run:

docker-compose down To stop just one container:

docker stop my_container Other useful commands

Restarts Docker. Useful in critical situations:

sudo service docker restart Check all containers and its status:

docker container ls Enter in the shell or bash of a particular container:

docker exec -it container_id /bin/bash Stop all containers:

docker stop $(docker ps -a -q) Delete all containers:

docker rm -f $(docker ps -a -q) Delete all volumes:

docker volume rm $(docker volume ls -q) Delete all container images:

docker rmi -f $(sudo docker images -q)
