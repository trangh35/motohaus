To start up WordPress:

install Docker for Mac: 
https://download.docker.com/mac/stable/Docker.dmg

From inside the repo, run:
```
docker-compose up
```

The docker compose file mounts your local volume to the root of the wordpress container, so all your source files will be there. It also binds port 8000 on your local machine to port 80 on the wordpress container. MySql is available only to the wordpress container, so if ever want to run commands to the database you will need to shell into the container to do so. 

To shell into the container, open a new terminal window and run the following commands:
This will list your docker containers
```
docker ps
```
find the Container ID, e.g. 4981f9cda931, and run:
```
docker exec -it 4981f9cda931 bash
```
This will give you an SSH session inside the docker container, you can access the mysql instance by it's container name, which you can get from docker ps under the NAMES column, e.g. motohaus_db_1

For Wordpress setup:

After your container is up, visit in your browser http://localhost:8000
You should get prompted to install wordpress, etc.



