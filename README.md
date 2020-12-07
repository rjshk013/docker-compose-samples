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
