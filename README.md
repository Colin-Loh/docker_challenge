# docker_challenge
Building and running a container

## Step 1:
```
.
└── docker_challenge
    ├── hello.sh
    ├── Dockerfile
```

| **Items** 	| **Description**                                                                                                                                                                                                                                                                   |
|----------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| hello.sh  | hello.sh is                                             |
| funcapp-build-pipeline.yml | The YAML file contains steps necessary to run **Terraform Plan / Apply**. The pipeline extends from a template.yaml within **mgl-platform** project. The template holds all stages required to apply appsetting changes                                              |

This folder contains a bash script that echoes out an environment variable called “HELLO” to standard out. 

## Step 2: 
Create a simple docker file based on alpine linux that copies the bash script into the container

This folder also has an alpine linux image that we are using to run it as a container. 
We would need to use the following command to run docker: 

`docker run --name repo alpine/git clone https://github.com/docker/getting-started.git`

A docker image is a private file system just for the container. It provides all the file and code that the container needs. 

Start a container based on the image we built, Running a container launches the application with private resources, securely isolated from the rest of your machine. 

In order to use this script, we would need to make the script executable by running the following command: 

```
chmod +x hello.sh
```

This will allow us to run the script by typing `./hello.sh` in the terminal / command prompt. 
