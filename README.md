# Dockerizing Sakai v20.5 and Msql v5.5 With Customed For Our Sakai. 

Firstly, Build Mysql Docker Image:

`docker build -t mysql -f ./Dockerfile.mysql .`

Secondly, Build Sakai Docker Image:

`docker build --build-arg release=20.5 -t sakai -f ./Dockerfile.sakai .`

Then Launch Mysql Container:

`docker run -d --name mysql -p 3306:3306 mysql`

After Launching Mysql Container, Now Launch Sakai Container linked with Mysql container

`docker run -d --name sakai -p 8080:8080 --link mysql:mysql sakai`
