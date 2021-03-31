## Managing Container Images

## Docker Image
    1) Speed -> Due to layers are modulared that mean independent each other
    2) Predictability -> Identical envrionments no matter where we host
        a) Reliable environment sharing 
        b) Reduced reliance on documentation 
        c) Reliable deployments

## Docker Search
   - Searches public docker repo
    a) docker search golang

## Pull Alpine linux OS
    - docker pull alpine:latest
    - docker history alpine

## Docker Sizes
    - Less as possible 
    - docker commands in one line with && and operator(less size) makes difference when compare to docker commands in separate lines 
    - Each line in docker file will be a layer in docker image

## Docker Image Storage
    
