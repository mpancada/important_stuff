# Commands
- `docker search <image_to_search>`
- `docker pull <image_name>` - downloads image  
- `docker images` - list all images  
- `docker run <image_name>` -  run images or download and run image
    - --rm - to remove the docker instance after it ends
    - --name
    - -d
    - -p `<os_port>:<container_port>`
    - -it - interactive console inside the container
    - -e `<env_name1>=<value1>` - defines env variables
    - --net `<network_name>` - Run inside this network
    - -v `<host_path>:<container_path>` or `<name>:<container_path>` - Create/use a volume to persist data
- `docker ps` - list running instances
    - -a - shows all containers
- `docker build -t <somename:1.0> <Dockerfile_path>`
    - -t - define tag name
    - -f - choose a custom filename
- `docker network ls` - List all networks
- `docker network create` `<network_name>`
- `docker inspect <id_or_name>` - See all configuration info( Root folder, Pid, Timestamps )
- `docker logs <id_or_name>` - Shows container logs
    - -f - String the logs
- `docker exec -it <id_or_bame> /bin/bash` - enter into the docker and display a bash terminal
- `docker rm <id_or_name>` - deletes container
- `docker rmi <id_or_name>` - deletes image

# Dockerfile
- `FROM ubuntu:22-04` - base container
- `COPY somefile.rb /somefolder/` -  copy file
- `COPY somedir /somefolder/` - copy folder
-` WORKDIR /somefolder` - sets this folder to execute the following RUN commands
- `RUN "any linux commands"`
- `RUN "other linux commands"`
- `CMD ["rails", "server","-p","3001"]` - The last command of the container, its an array to exec a linux command

# Docker compose
<table>
    <thead> 
        <tr>
            <th>
              Docker commands
            </th>
            <th>
              Docker compose
            </th>
        </tr> 
    </thead>
    <tbody>
        <tr>
            <td>
<pre lang='bash'>
docker run -d \
    -p 3306:3306 \
    -e ENV_VAR1=somevalue \
    -e ENV_VAR2=somevalue \
    --net some_network \
    --name some_db \
    <image_name>                
</pre>
<pre lang='bash'>
docker run -d \
    -p 8081:8081 \
    -e ENV_VAR3=somevalue \
    -e ENV_VAR4=somevalue \
    --net some_network \
    --name some_name \
    <image_name2>
</pre>
            </td>
            <td>
<pre lang='yaml'>
version:'3'<br>
services:
    some_db:
        image: <image_name> 
        ports: 
         - 3306:3306
        environment:
         - ENV_VAR1=somevalue
         - ENV_VAR2=somevalue
    some_name:
        image: <image_name2>
        ports:
         - 8081:8081
        environment:
         - ENV_VAR3=somevalue
         - ENV_VAR4=somevalue
</pre>
            </td>
        </tr>
    </tbody>
</table>

- `docker-compose -f <filename>.yml up` - Run docker compose file and start all configuration
- `docker-compose -f <filename>.yml down` - Run docker compose file and stop all configured


  

