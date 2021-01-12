# dmulligan/docker-example-tomcat-mysql

A docker compose example project with a MySQL and a Tomcat container linked together.

To run: 

	$ docker-compose up

Containers:
- MySQL: on startup, the container executes a simple database initialisation script `./db/mysql-init.sql`, which
  creates a database containing a single table which is populated with a few records.
- Tomcat: a simple web application, located within `./tomcat/webapps`, is deployed. The application contains some JSPs
  to test the database link between the Tomcat and the MySQL containers.

Docker-sample-nodejs project : notes-service
--------------------------------------------

1.clone the repo 
2.cd notes-service
3.npm install 
4.build the app using docker-compose
docker-compose -f docker-compose.dev.yml up --build

check your application working from the host machine :

curl --request GET --url http://localhost:8080/services/m/notes

must see output as below 

{"code":"success","meta":{"total":0,"count":0},"payload":[]}

reference : https://www.docker.com/blog/how-to-setup-your-local-node-js-development-environment-using-docker-part-2/


To build & run a jenkinsblueocean docker container use the docker compose file : docker-compose_jenkinsblueocean.yml

docker-compose -f docker-compose_jenkinsblueocean.yml up 


To create sonarcube server with postgresql for production environment use docker-compose : docker-compose_sonarcube_postgresql.yml

docker-compose -f docker-compose_sonarcube_postgresql.yml up

To create jenkinsblueocean container with sonarcube + postgresql i a single docker compose file use : docker-compose_sonarcube_jenkins.yml

Note: before running docker compose configure your host as per below commands as root user 

sysctl -w vm.max_map_count=262144
sysctl -w fs.file-max=65536
ulimit -n 65536
ulimit -u 4096

reference : https://hub.docker.com/_/sonarqube/
