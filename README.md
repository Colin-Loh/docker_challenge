# docker_challenge
Building and running a container

## Files
```
.
└── docker_challenge
    ├── hello.sh
    ├── Dockerfile
```

| **Items** 	| **Description**                                                                                                                                                                                                                                                                   |
|----------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| hello.sh  | Bash script that echoes out an environment variable called “HELLO” to standard out. |
| Dockerfile | Docker file based on alphine linux that copies the bash script into the container |


## How to build the Dockerfile

1. Create a new file called `Dockerfile` in the project directory 

2. In the first line of the `Dockerfile`, specify the base image. In this case we would use `alpine:latest` as the base image which is a lightweight, latest version of Alpine Linux.

3. We would need to copy our bash script to the container using `COPY` command. The command: `COPY hello.sh ./` copies our bash script to the current directory of our container

4. In order to use this script, we would need to make the script executable by running the following command: `chmod +x hello.sh`. We can use the `RUN` command to do this. 

5. Finally, we can use `CMD` command to specify the command to run when the container is running. `CMD ["sh", "hello.sh"]`, the `sh` executable is being run with the `hello.sh` script as the first parameter. This will run the `hello.sh` script using the `sh` shell.

## How to run the container

1. Before we can run our container, we would need to build our Docker image. We can do this by running the following command: 

```
docker build -t hello .  
```

The `.` indicates that the current working directory is the context of the build.

2. To run the container, we can run the following command:

```
docker run hello  
```

This will automatically start a new container based on the `hello` image and the `hello.sh` script will be executed automatically. 

## How to run the container so it prints out “good morning”

1. To run our container and prints out "good morning" we would need to add or modify our environment variable `HELLO`. 

We can do this by the following command: 

```
docker run -e HELLO=“good morning” hello
```

The will automatically sets the environment variable `HELLO` with the string "good morning"

Alternatively, 

you can add the command `export HELLO=“good morning”` at the start of our bash script. 
