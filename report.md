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

Listing all images available:

Running `message-app` Dockerfile:

Created YAML file:
```

```
Building `docker-compose`:

Running the services:

Using app commands:



