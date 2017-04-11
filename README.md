# KiloDocker

==================
BUILDING
==================

docker build -t my_flask_app .


==================
RUNNING
==================

docker run -p 80:80 -t my_flask_app

-p connects port 80 of the Docker container to port 80 of your machine, so HTTP can work.
-t again specifies the tag of the container we want to run.


docker run -d --restart=always -p 80:80 -t my_flask_app

-d runs the Docker container as a daemon in the background
--restart=always restarts the container if it crashes, or if the system docker is running on is rebooted.

==================
STOP
==================

docker ps
docker kill whatever_we_called_it


==================
OTHER
==================

+++Using a different environmental variable


You can overwrite many of the commands specified in the Dockerfile, including the environment variables. To change the $MESSAGE var to something else, use the -e flag (for “Environment”):

docker run -p 80:80 -e MESSAGE="something else" -t flask_ascii


+++Daemonize it!

Run it as an auto-restarting daemon:

docker run -d -restart=always -p 80:80 -t flask_app
