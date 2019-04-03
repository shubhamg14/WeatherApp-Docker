# WeatherApp-Docker
Steps to containerize the WeatherApp (https://github.com/shubhamg14/WeatherApp-UI)

The environment used was Ubuntu-18 on AWS

## Installing Docker

Run following commands on unix prompt from the working directory where all code which needs to be dockerize is present.

1. pip install docker (Installs Docker).
2. sudo usermod -aG docker ubuntu (Gives admin previliges to the user after verifying identity)
3. Create a "Dockerfile" --> (Exact name as mentioned) in the working directory and put the following code into it.

       1. FROM alpine:latest
       2. RUN apk add --no-cache python3-dev \
       3. && pip3 install --upgrade pip

       4. RUN pip3 install flask  
       5. RUN pip3 install requests

       6. WORKDIR /DockerApp

       7. COPY . /DockerApp

       8. EXPOSE 80

       9. ENTRYPOINT ["python3"]
       10.CMD ["flaskapp.py"]

Description about Dockerfile:

1. First line in file imports base docker imagei.e Apline Linux which is the most popular lightweight image for docker
2. Second to 4th Line in the above code mentions about the libraries which are required to create an environment for your application.
3. Line 5th in the above code tells docker to create a folder on docker image /Dockerapp in which our whole code for the application would be copied.
4. Line 6th tells Docker to copy code from the present working directory to /DockerApp path in Docker image
5. Line 7th tells docker to expose 80 so that application can be run on port 80
6. Line 9th and 10th tells docker to run following command "python3 flaskapp.py" whenever the docker image is initialized.

Save and exit the Dockerfile

## Creating and Running Docker Image and Container

Before building Docker image add following code in to your flask python code:

       app.run(host='0.0.0.0',port=80)

After Dockerfile is created, run the following commands:

1. docker build -t flaskapp:latest . (Builds a latest(tag) image for flaskapp)
2. docker images (To check if the image has been created or not)
3. docker run -it -d -p 80:80 flaskapp (Daemon mode for running image continuously even after closing the command window)(To run application form docker) (This command tells docker to run its service on port 80 of whichever machine it is running from and map that service to port 80 of our app)
4. docker ps (Can be used to check if container is running or not)

## Pushing the Docker Image to Docker.io

Following command to be used to push image to Docker.io

1. Create an account on Docker.io using your email id.
2. docker login --username=yourhubusername --email=youremail@company.com 
3. docker tag (image_id) (yourhubusername)/(repository_name):(tag)
   Example : docker tag 123456efg12 abc123/weatherapp:ver1
4. docker push (yourhubusername)/(repository created on docker hub)
    Example: docker push abc123/weatherapp

## Pulling and running the DockerImage from Docker.io

To pull image from docker.io use following commands:

1. docker pull (yourhubusername)/weatherapp:var1
2. docker run -d -p 80:80 (youhubusername)/weatherapp:var1
