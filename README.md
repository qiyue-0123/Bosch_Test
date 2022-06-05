# Bosch_Test
I use ansible to deploy an app in docker container to cloud vm(alibaba cloud), you can access http://47.254.147.185:3000/ to see the "Todo" application.(This ip is valid until 2022-06-12 23:59)

This application includes MySQl service, you can link to the virtual machine by ip 47.254.147.185(public ip) 
and excute command "docker exec -it e8cfa9ab3503 mysql -p todos", and excute "select * from todo_items;" to see the database table information. 
(e8cfa9ab3503 is the container id of the mysql container)

The three files under Bosch_Test/ansible/ directory is the deployment scripts of ansible. The deploy-docker.yml is roughly divided into these steps：

1. Install docker 
2. Install git && clone the "Todo" app code from github
3. Write Dockerfile and build docker
4. Create a docker network
5. Run a container using the nicolaka/netshoot image. Make sure to connect them to the same network.
6. Install docker-compose and write docker-compose.yml file, then excute "docker-compose up -d".
