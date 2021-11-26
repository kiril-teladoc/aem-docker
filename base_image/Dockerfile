# Using 'ubuntu' as the base image here
FROM ubuntu:20.04

# setting the working directory
WORKDIR /opt/aem

# Copy the license file
COPY license.properties .

# Copy Quickstart jar file
COPY aem-author-p4502.jar cq-quickstart.jar

# Install Java 8 (Java 8+ is required)
RUN apt-get update && \
    apt-get install -y curl && \
    apt-get install -y software-properties-common && \
    add-apt-repository ppa:openjdk-r/ppa && \
    apt-get update && \
    apt-get install -y openjdk-8-jdk
