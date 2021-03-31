# Test web app that returns the name of the host/pod/container servicing req
# Linux x64
FROM node:current-alpine

# LABEL to add the metadata
LABEL org.opencontainers.image.title="Hello Docker Learners!" \
      org.opencontainers.image.description="Web server showing host that responded" \
      org.opencontainers.image.authors="@suryamangena"

# Create directory in container image for app code
RUN mkdir -p /usr/src/app

# Copy app code (.) to /usr/src/app in container image
COPY . /usr/src/app

# Set working directory context
WORKDIR /usr/src/app

# Install dependencies from packages.json
RUN npm install

# Command for container to execute-> at the image launches
ENTRYPOINT [ "node", "app.js" ]

# ENV - set the environment variable 
# CMD -> Execte the command 
# ADD -> Add the files from remoteurl rather than the local machine and also unpack tar files
# VOLUME /var/data -> add volume to the container 
# STOPSIGNAL sigint -> system termination signal 
# HEALTHCHECK --interval=5m --timeout=3s CMD curl -f http://localhost/ || exit 1 -> this posts log entry to local file system when it finds problem 
# ARG CODE_VERSION=latest -> Arg instruction pass variables during build time 
#ONBUILD ADD . /app/src -> used to biuld new image based on old existing local image
# ONBUILD RUN 
# SHELL ["powershell", "-command"] -> To use shells other than default ones

