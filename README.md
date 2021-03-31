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
    ###### Buid Image:
        - docker image build -t suryamangena/dockerlearning:first-container .
        - docker image ls
        - docker image rm suryamangena/dockerlearning:first-container 

          Reference: https://docs.docker.com/engine/reference/commandline/image/
    ###### Run Command:
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
        
 ## References
 - https://github.com/nigelpoulton/gsd/tree/master/
 - [docker image](images/docker-image.png)



