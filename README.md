# Docker_notes

# See how many images you have?

docker images ls



# See how many docker container ?

docker container ls -a

# Remove a container ?

docker container rm container_id

# Remove multiple container ?
 docker container rm container_id container_id


# Start a container?
docker container start container_id


# Stop a container ?
docker container stop id

# Run a container in background?

docker container run -d ubuntu sleep 30

# Go inside a container?

docker container run -it ubuntu /bin/bash

# Check os realease?
cat /ect/os-release


 # You can also exit from a container without killing it
ctrl p  q

# Remove all container in one command?
docker container rm $(docker container ls -aq)

# How to inspect or get ip address of a container?
 docker container inspect id | less

# Port mapping command ?
 docker container run -d  -p 3600:80 --name my_nginx  nginx


# How to check how many ports running on my machine?

netstat -nltp

# Go inside a container ?

docker container exec -it id /bin/bash

# Rename a container name

 docker container rename id new_name


# Restart a container?

docker container restart id


# Check logs of a container?
docker container logs id

# How to check how many process running on a container?

docker container top id
ps -aux


# How to see all my container using how many ram
docker container stats


# Attach a container inforgrounf?

docker container attach id

# Kill a container?

docker container kill id


# Waiting for exit status of a container?

docker container wait id

# Pause a conatiner ?
docker container pause id


# Unpause a conatainer?

docker container unpause



# Delete all stopped container?

dockar container prune -f



# Check port mapping of container?

docker container port name_of _container


# Docker create command just create a container 
 docker container create ubuntu  sleep 60


# Check file system change of a container ?
 docker container diff id ->(C means created  ,D means deleted,A means add  )

# Set watch command to a cmd

watch 'docker container diff id'

# Copy a file to a particular container

docker container cp test/  id:/tmp/

here test/ host machine path and :/tmp is container path


# Go inside a detach container?
 docker container attatch id

# Export a docker container ?

docker container export id>my_exported.tar

Or docker container export id -o my_exported_container


# How to import exported container?

docker image import my_exported_container my_image


# How to make image from a running container?

docker container commit --author "Kibria" -m "this is test commit id new_name

# How to pull a specific image?

docker pull ubuntu:14.04

# Give a tag to a iamge

docker image tag hub.docker.com/my_id/image_name 
docker login
docker push name_of_image


# Remove image 
docker rm image name

docker image prune(delete unused iamage)

