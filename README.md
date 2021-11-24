# Create AEM instances in Docker with Docker Compose

## Description
This repository contains Docker files needed for creating AEM Author and AEM Publish instances with Docker Compose.

In order to run the instances 3 Docker images are created: 
- __Base Image__ (aem-base-image)
- __Author Image__ (aem-author)
- __Publish image__ (aem-publish)

Base Image is created out of Ubuntu image and contains the licence file and AEM binary file. Also Java 8 is installed on it. 

Author and Publish Images are created out of Base Image.

## Creating the Docker images
When setting up the instances for the first time, you have to create the Docker images.

1. Copy the __licence file__ (`license.properties`) and __AEM binary file__ (`aem-author-p4502.jar`) in the base_image folder.

2. Create __Base image__.
  - Go to base_image folder and run the following command:
    ```
    $ docker build -t aem-base-image .
    ```
    _You may need to execute it with sudo as root user._

3. Create __Author image__.
  - Go to author folder and run the following command:
    ```
    $ docker build -t aem-author .
    ```
    _You may need to execute it with sudo as root user._

4. Create __Publish image__.
  - Go to publish folder and run the following command:
    ```
    $ docker build -t aem-publish .
    ```
    _You may need to execute it with sudo as root user._

5. You may check if the images were successfully created with:
  ```
  $ sudo docker images
  ```

## Start the instances
If you are setting up the instances for the first time, you have to create the Docker images.

To start the instances run:
```
$ docker-compose up
```
_You may need to execute it with sudo as root user._

It takes __ca. 5 minutes__ to start up both instances.
- The author instance will be available on port 4502. (http://localhost:4502/)
- The publish instance will be available on port 4503. (http://localhost:4503/)

To stop the instances type __Ctrl+C__ in the console.