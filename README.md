# Sakai-mysql
Dockerized sakai v20.5 and msql v5.5

# Building Mysql Docker Image for Sakai

docker build -t mysql -f ./Dockerfile.mysql .

# Building Sakai Docker Image

docker build --build-arg release=20.5 -t sakai -f ./Dockerfile.sakai .

# Launching Mysql Container

docker run -d --name mysql -p 3306:3306 mysql

# Launching Sakai Container linked with Mysql container

docker run -d --name sakai -p 8080:8080 --link mysql:mysql sakai
