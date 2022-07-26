## Example 00
![ex0_whale_Screenshot 2022-07-22 105501](https://user-images.githubusercontent.com/95945800/180466443-190307ad-31e5-4a24-b6ca-df42b9936f2c.jpg)
## Example 01
Running Ubuntu container:
![ex1_container_Screenshot 2022-07-22 105851](https://user-images.githubusercontent.com/95945800/180467206-3902b998-9343-4ee0-bb12-9a4155fc3743.jpg)

Installing & Running Vim:
![ex1_run_vim_Screenshot 2022-07-22 110619](https://user-images.githubusercontent.com/95945800/180468564-9e1ff6c6-bdae-4a79-8969-33606fe7c4b2.jpg)

Installing & Running Cowsay:
![ex1_cowsay_Screenshot 2022-07-22 110856](https://user-images.githubusercontent.com/95945800/180469062-445b794b-ab34-4e72-836f-f506e216e448.jpg)

## Example 02
Running Mongo container:
![ex2_mongo_Screenshot 2022-07-22 111451](https://user-images.githubusercontent.com/95945800/180470336-04e6fcbd-a494-4f3e-82b5-21daa2cac26a.jpg)

Running Rocket.Chat container:
![ex2_rocketchat_Screenshot 2022-07-22 111732](https://user-images.githubusercontent.com/95945800/180470706-6f13cfd6-ac0f-4713-bf9a-e2eb1f8b69cc.jpg)

Rocket.Chat localhost application:
![ex2_rocketchat_localhost_Screenshot 2022-07-22 111914](https://user-images.githubusercontent.com/95945800/180471052-5a494e95-283e-495a-9da4-ce158119b395.jpg)

Testing other docker commands:
![ex2_other_command_Screenshot 2022-07-22 112503](https://user-images.githubusercontent.com/95945800/180472150-703cd7b4-5b3c-4a73-8c9c-5a0b921d5cf3.jpg)
## Example 03
Created Dockerfile:
```
# Comments in Dockerfiles
FROM python:3.5

# Update and install dependencies
RUN apt-get update
RUN pip install Flask

# Add code
ADD . /opt/webapp/

# Set the working directory
WORKDIR /opt/webapp

# Set environment variables
ENV FLASK_APP=hello.py

# Expose the application's port
EXPOSE 5000

# Run the application
CMD ["flask", "run", "--host=0.0.0.0"]

```

Building Dockerfile & Running container:
![ex3_build_Screenshot 2022-07-22 120454](https://user-images.githubusercontent.com/95945800/180479592-5ae846e7-8015-4b38-a80d-7f8ce99fb814.jpg)

Application on localhost:
![ex3_webapp_Screenshot 2022-07-22 120544](https://user-images.githubusercontent.com/95945800/180479609-8bb2d1b7-cccc-462e-92a9-ebd887ff5463.jpg)
## Example 04
Created Dockerfile:
```
# Use node 10.15.3 LTS
FROM node:10.15.3
ENV LAST_UPDATED 20190325T175400

# Copy source code
COPY . /app

# Change working directory
WORKDIR /app

# Install dependencies
RUN npm install

# Fix up some of the issues
RUN npm audit fix

# Expose API port to the outside
EXPOSE 1337

# Launch application
CMD ["node","app.js"]
```
Building Dockerfile:
![Building_docker_160162501-35399953-54be-433d-b218-b46b90131b37](https://user-images.githubusercontent.com/95945800/180809775-7ca97df8-df58-4157-a81d-9654c5b66d9c.png)

Listing all images available:
![ex4_first_images_Screenshot 2022-07-22 123008](https://user-images.githubusercontent.com/95945800/180806428-292df38c-4d68-46a3-aa77-2bf5a1074f39.jpg)

Running `message-app` Dockerfile:
![Running_docker_160162510-8bdddea0-8880-42ee-8195-eaf36fd6a0da](https://user-images.githubusercontent.com/95945800/180809977-892582a6-b195-4cf1-b076-1c17239c16c5.png)

Created YAML file:
```
version: '3'
services:
  mongo:
    image: mongo:4.0.7
    volumes:
      - mongo-data:/data/db
    expose:
      - "27017"
  app:
    build: .
    ports:
            - "1337:1337"
    links:
      - mongo
    depends_on:
      - mongo
    environment:
      - MONGO_URL=mongodb://mongo/messageApp
volumes:
  mongo-data:
```
Building `docker-compose`:
![BUilding_docker_compose_Screenshot 2022-07-25 110639](https://user-images.githubusercontent.com/95945800/180811743-08a5f409-641d-4a7e-9f2c-1fb618e03d2a.jpg)


Running the services:
![Running_servers_160162539-44ef4367-a213-4e5e-902d-add24df4100c](https://user-images.githubusercontent.com/95945800/180810339-e4119b31-b35f-48f7-a546-58464a6c466d.png)

Using app commands:
![Using_app_commands_1_160162564-30bdf8c9-ae4f-430a-b448-bdb291c0ba0f](https://user-images.githubusercontent.com/95945800/180810529-05fabb80-9a8a-4db4-9a7c-f9ead1316cda.png)
![Using_app_commands_2_160162581-47194450-c45f-476a-ada9-9860fb6e91a6](https://user-images.githubusercontent.com/95945800/180810599-f397b47a-ee0c-40c5-845a-ddc22f8bf629.png)


