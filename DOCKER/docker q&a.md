DOCKER

1) Explain the Architecture of Docker
2) Docker Home directory ?
3) how will you integrate a docker server in jenkins
4) write a dockerfile using a linux and a webserver

    take a linux as base image and install w web server
	
	FROM ubuntu:latest
	MAINTAINER saiprasad
	RUN apt install apache -y
	
5) ENTRYPOINT VS CMD  (difference)

6) where do we used docker to slove specific problem

	IN Recent projects we face inconsistency issues in development and 
	production environment, leading to deployment errors. To solve this
	we adopted docker, and deployed the app using k8s

7) There are multiple stopped containers and unused network taking up 
	spaces, How you will clean up these resources effectively ?
	
	:docker system prune -a
	
8) what is an argument (ARG) and ENV variable
	
	when we will use ARG and ENV 
	
senerio based questions

1) you have a Docker container running a web server, but you need to update the application code inside it.
how would you approach this task?

step1:- stop the running container using "docker stop"

step2:- pull the latest version of ther docker image with updates code using "docker pull"

step3:- Run a new container with the updayes image, ensuring to map volumes and ports using "docker run"

step4:- verify the new container is running correctly


## senerio 2
** you team is deploying a microservices architecture using Docker containers.
how would you orchestrate and manage these containers effectively

## TASK : orchestrating microservices Architecture

i would use docker swarm or kubernetes for container orchestration. Both tools facilitate
management and scaling across multiple hosts.
	
## senerio 3
* you have encountered a problem where a DOCKER container keeps crashing without any clear error message.
how would you troubleshoot and diagnose this issue?
### Task : Troubleshooting container crash
**Answer**:
1. check conatiner logs with `docker logs <container>`.
2. Inspect resource usage and runtime stats using `docker stats <container-name>`
3. review host system logs and metrics
4. if needed, SSh into container using `docker exec -it <container-id> /bin/bash`
5. Review Dockerfile and configuration for misconfiguraton

## senerio 4
* your team needs to share data between multiple Docker containers. how would you accomplish this while maintaining isolation between the containers ?
### Task : Sharing Data Between containers
**Answer**:
i'll use docker volumes and networks, volume offers persistent storage shared among containers, while network enable secure communications. This setup allows containers to access shared data or communicate without impacting each other

## senerio 5
* you need to ensure that your DOCKER containers are secure and compliant with company policies. what security best practies would you implement?
### Task : Implementing Security Best Practices
**Answer**:
1. Regularly update Docker images and containers.
2. Utilize Docker's Security features (user namespaces, seccomp profiles, etc.)
3. Employ least privilege principles for container permissions
4. use docker content trust for image integrity.
5. dcan docker images for vulnerabilities.
6. monitor container activivty for security incidents.
 
