# Docker hands on

We will create an image with a simple python file that will print some messages to see how docker works. 

## Create a Dockerfile
Create a dockerfile with all necessary commands to create the image. First, we will download or call the first image, for example:
```
FROM python:2
```
or 
```
FROM alpine:3.14
```
To check for more available images check the [Docker Hub](https://hub.docker.com/search?q=).

Then, we are entering in the working directory with the command:
```
WORKDIR /usr/src/app
```

To finally copy a requirements file containing the dependencies of the project and install them with pip:
```
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
```

Then, we copy the rest of the files to the working directory:
```
COPY . .
```

To finally run the python file:
```
CMD [ "python", "./your-daemon-or-script.py" ]
```
We would have the ENTRYPOINT command but it is not necessary here as it is already specified on the layer/image and only the arguments need to be specified with *CMD*.

Note: The name *Dockerfile* ALWAYS need the first letter in uppercase.

## Build the image
With the next command we will build an image. If we do ANY change in any of the configuration files of the image, we will need to build it again. By specifying the same name as the previous image, we will reescribe the previous image into the new one. 
With the command:
```
docker build -t <image_name> .
```
We can build the image with the name we want and the dot at the end is the path where the Dockerfile is located.
We will see on the terminal how each of the commands we have specified in the Dockerfile are executed one by one.

## Run the image
First of all, if we want to check if we already have any image, we can execute:
```
docker image ls
```
To run the image, we will execute:
```
docker run <image_name>
```
We will see how the python file is executed and the messages are printed on the terminal.

For any needed help, execute:
```
docker run --help
```

If we want our container to be removed after it is executed, we can add the *--rm* flag:
```
docker run --rm <image_name>
```

With the optional flag *-it* we can run the container in interactive mode:
```
docker run --rm -it <image_name>
```
### Run a service
To expose a port, as for the *docker-test-flask* where we publish a service, we will need to specify which port from the container and our local machine we want to use. For example:
```
docker run --rm -it -p 80:80 <image_name>
```
Where the first 80 is the port from the container and the second one is the port from our local machine.

If we need to execute commands inside the container, we can go to the docker software and click on the container ID which is the one running. Inside it, we will have root privileges to execute any command we want, as *top* to see the processes running.

##  Stop it!
To stop the container and remove everything, we can execute:
```
docker system prune --all
```
