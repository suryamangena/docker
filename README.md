# docker-learning

## Docker Topics
 - Containerizing App
 - Hosting on a Registry
 - Running a Containerized App
 - Managing a Containerized App


## Docker File
    1) Start from exisitng image based on app and os dependencies
    2) Provide metadata information using Label 
    3) Create a directory 
    4) Copy app code
    5) Set working directory 
    6) Install dependencies 
    7) Set the Entrypoint to call the main part/start application

## Docker commands
    ## Buid Image:
        - docker image build -t suryamangena/dockerlearning:first-container .
        - docker image ls
        - docker image rm suryamangena/dockerlearning:first-container 

          Reference: https://docs.docker.com/engine/reference/commandline/image/
    ## Run Command:
        - docker container run -d --name web -p 8000:8080 suryamangena/dockerlearning:first-container -> Here d is detach i.e. mean run in background 
        - docker container ls
        - docker container stop web -> web is name of container 
        - docker container ls -a 
        - docker container rm web
        - Run the container by attaching the terminal -> It means Interactive terminal that allows you access the terminal of container
            docker conatiner run -it --name test alpine sh

            - Exit the terminal 
                exit command -> it will kill the container as well
            - To have soft exit without killing container 
                Ctrl+P+Q



          Reference: https://docs.docker.com/engine/reference/commandline/container_run/

## Virtual Machine vs Docker
    - Virtual Machines virtualize the hardware
    - Container virtualize the Operating System by sharing same OS Kernel and Hardware

## Docker Compose
    Used to define mlti-container apps
    
## Docker Compose Commands:

    - docker-compose up -d 
    - docker-compose down


## Docker Service
    - Docker service is only available in swarn mode
    - docker service create --name web1 -p 8000:8080 --replicas 3 suryamangena/dockerlearning:first-container
    - docker container ls
    - docker service ps web1 -> Multinode docker swarm
    
    ##Scale the docker containers:
        - docker service scale web1=10
        - It will total scale to 10 including existing one. If we stop the few of the containers forcibly, then docker has observe state and desire state, in this case desire state 10 and observe state is 7 as we killed 3 docker containers. So docker service spin up 3 more containers to match the observe and desire state.
    ## Remove the running docker container by using force option
        - docker container rm 9c838b216de4 25c802319fd0 f594ac503234 -f

## Docker Swarm
   - Group of either physical or virtual machines that are running the docker application and that have been configured to join together in a cluster. Clusters are controlled by swarm managers and machines that have joined the cluster are referred to as nodes.

## Docker Swarm Stack
    - Stack on a swarm don't support images on the file 
    - Images needs to be created 
          Reference: 
          - https://docs.docker.com/engine/reference/commandline/container_run/

    - docker stack deploy -c docker-compose.yml conter
    - docker stack ls 
    -  docker stack services conter -> Each Services 
    - docker stack ps counter -> Each container
    - docker stack rm conter

## [Managing Container Images] (docs/managing-container-images.md)#Managing Container Images
        
 ## References
 - https://github.com/nigelpoulton/gsd/tree/master/
 - [docker image](images/docker-image.png)



