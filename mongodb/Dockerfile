# Dockerizing MongoDB: Dockerfile for building MongoDB images
# Based on ubuntu:latest, installs MongoDB following the instructions from:
# http://docs.mongodb.org/manual/tutorial/install-mongodb-on-ubuntu/

# Format: FROM    repository[:version]
FROM       mongo:latest

# Format: MAINTAINER Name <email@addr.ess>
MAINTAINER JaeHwan Oh <ojh102@naver.com>

# Installation:
# Import MongoDB public GPG key AND create a MongoDB list file
#RUN apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv EA312927
#RUN echo "deb http://repo.mongodb.org/apt/ubuntu trusty/mongodb-org/3.2 multiverse" | tee /etc/apt/sources.list.d/mongodb-org-3.2.list

# Update apt-get sources AND install MongoDB
#RUN apt-get update && apt-get install -y mongodb-org

# Create the MongoDB data directory
#RUN mkdir -p /data/db
VOLUME ["/data/db/"]
#WORKDIR /data/
#RUN mkdir -p /data/db

#RUN awk '/bind_ip/{print "bind_ip = 0.0.0.0";next}1' /etc/mongod.conf > /tmp/mongod.conf
# Expose port 27017 from the container to the host
EXPOSE 27017
EXPOSE 27019
EXPOSE 27018
EXPOSE 28017
# Set usr/bin/mongod as the dockerized entry-point application
ENTRYPOINT ["/usr/bin/mongod","--dbpath","/data/db/"]


