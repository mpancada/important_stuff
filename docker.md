# Commands
- `docker search <image_to_search>`
- `docker pull <image_name>` - downloads image  
- `docker images` - list all images  
- `docker run <image_name>` -  run images or download and run image
    - --name
    - -d
    - -p `<os_port>:<container_port>`
    - -it - interactive console inside the container
    - -e `<env_name1>=<value1>` - defines env variables
    - --net `<network_name>` - Run inside this network
- `docker ps` - list running instances
    - -a - shows all containers
-` docker build -t <somename:1.0> <Dockerfile_path>`
    - -t - define tag name
- `docker network ls` - List all networks
- `docker network create` `<network_name>`
- `docker inspect <id_or_name>` - See all configuration info( Root folder, Pid, Timestamps )
- `docker logs <id_or_name>` - Shows container logs
    - -f - String the logs

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
    <tr>
        <td>
          lool<br>
          asdad
        </td>
        <td>
          aaaaa
        </td>
      </tr> 
</table>


  

