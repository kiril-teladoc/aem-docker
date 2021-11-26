# Create AEM instances in Docker with Docker Compose

## Overview
This repository contains Docker files needed for creating AEM Author and AEM Publish instances with Docker Compose.

In order to run the instances 3 Docker images are created: 
- __Base Image__ (aem-base-image)
- __Author Image__ (aem-author)
- __Publish image__ (aem-publish)

Base Image is created out of Ubuntu 20.04 image and contains the licence file and AEM binary file. Also Java 8 is installed on it. 

Author and Publish Images are created out of Base Image.

*__Important note:__
To run the AEM instances, you will need minimum 2GB memory and 5GB disk space.* 

## Creating the Docker images
When setting up the instances for the first time, you have to create the Docker images.

1. Copy the __licence file__ (`license.properties`) and __AEM binary file__ (`aem-author-p4502.jar`) in the base_image folder.

2. Run the following command for building the images:
    ```
    $ docker-compose build
    ```
    ___Note:__ You may need to execute all commands with sudo as root user. Instructions on how to manage Docker as a non-root user can be found [here](https://docs.docker.com/engine/install/linux-postinstall/#manage-docker-as-a-non-root-user)._

    If you want to build the images and then start the instances, run the following command:
    ```
    $ docker-compose up --build
    ```

## Start the instances
If you are setting up the instances for the first time, you have to create the Docker images.

- To start __both of the instances__ run:
  ```
  $ docker-compose up
  ```

- To start __author instance__ only, go to `./author` folder and run the following command:
  ```
  $ docker run -p 4502:4502 aem-author
  ```

- To start __publish instance__ only, go to `./publish` folder and run the following command:
  ```
  $ docker run -p 4503:4503 aem-publish
  ```

It may take __up to 5 minutes__ to start the instances for the first time.
- The author instance will be available on port 4502. (http://localhost:4502/)
- The publish instance will be available on port 4503. (http://localhost:4503/)

To stop the instances press __Ctrl+C__ in the console.