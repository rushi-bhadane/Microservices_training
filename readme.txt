For setting mongodb path : mongod --dbpath="D:\MongoDB" It's a server process

in kycprocess/target : java jar

push the project(jar file to cloudfoundary): cf push kycprocess2019-cf -p jar filename
In kycprocess,
src/main/resources/application.properties:

spring.profiles.active = prod

application-dev.properties:

spring.data.mongodb.host=localhost
spring.data.mongodb.port=27017
spring.data.mongodb.database=boadb
spring.data.mongodb.url=mongodb://localhost:27017/boadb

kycprocess/pom.xml":

55 :

Docker:

> docker logs

-Dserver.port=6061

To create container:
> docker run --name demo-mysql -e MYSQL_ROOT_PASSWORD=password -e MYSQL_DATABASE=demo -e MYSQL_USER=demo_user -e MYSQL_PASSWORD=demo_pass -d mysql

To start mysql:
> docker exec -it demo-mysql mysql -u demo-user -p
demo-mysql is container, demo-user is userid

To remove container:
>remove rm containerid

stop the container:
>docker stop containerid

restart the container:
>docker restart conmtainerid

for containerid:
>docker container ls -a

for docker image build:(run from cmd in project folder)
>docker build -f dockerfile -t kycmumbai-app .

For compose, deploying the docker file:
>docker-compose up


Openshift:

Move spring project to openshift and run on 

copy url
paste in cmd
> openshift-->copylogincommmand-->token

To detect resources:
>oc get pods


>oc new-app -e MYSQL_USER=demo_user -e MYSQL_PASSWORD=demo_pass -e MYSQL_DATABASE=demo -e MYSQL_ROOT?_PASSWORD=password mysql --name=demo-app


Zipkins:

>docker run -d -p 9411:9411 openzipkin/zipkin

https://zipkin.io/pages/quickstart , on this website download java zipkin.jar file

> java -jar zipkin.jar

>http://192.168.99.100:9411/zipkin/

in ecommerce app, applicaion properties file, 
2. spring.zipkin.base-url=http://localhost:9411/

For this to run, eurekaserver should be connected

Hystrix:

Project 1: Hystrix Dashboard, 8081
Project 2: Hystrix Callback, 8090
Project 3: Kycprocess, 7076
