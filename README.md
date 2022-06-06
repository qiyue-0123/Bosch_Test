# Bosch_Test
I use ansible to deploy an app in docker container to a cloud vm(alibaba cloud), you can access http://47.254.147.185:3000/ to see the "Todo" application.(This ip is valid until 2022-06-12 23:59 CST)

This application includes MySQL service, you can use ssh to link to the virtual machine by ip 47.254.147.185(public ip) 
and excute command "docker exec -it efc3e6f7a7fb mysql -p todos", input password:secret, and excute "select * from todo_items;" to see the database table information. 
(efc3e6f7a7fb is the container id of the mysql container)

The three files under Bosch_Test/ansible/ directory is the deployment scripts of ansible. The deploy-docker.yml is roughly divided into these steps：

1. Install docker 
2. Install git && clone the "Todo" app code from github
3. Write Dockerfile and build docker
4. Create a docker network
5. Run a container using the nicolaka/netshoot image. Make sure to connect them to the same network.
6. Install docker-compose and write docker-compose.yml file, then excute "docker-compose up -d".
