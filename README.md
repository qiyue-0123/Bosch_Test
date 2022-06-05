# Bosch_Test
I use ansible to deploy an app in docker container to cloud vm(alibaba cloud), you can access http://47.254.147.185:3000/ to see the "Todo" application.(This ip is valid until 2022-06-12 23:59)
This application includes MySQl service, you can link to the virtual machine by ip 47.254.147.185(public ip) 
and excute command "docker exec -it e8cfa9ab3503 mysql -p todos", and excute "select * from todo_items;" to see the database table information. 
(e8cfa9ab3503 is the container id of the mysql container)

The three files under Bosch_Test/ansible/ directory is the deployment scripts of ansible.
