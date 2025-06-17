## 13. **What is the Dockerfile and what are some instructions ?

* A Dockerfile is a script containing a series of instructions on how to build a Docker image. Key instructions include:

    - FROM – Defines the base image (e.g., node, alpine, ubuntu, etc.)

    - WORKDIR – Sets the working directory inside the container

    - COPY – Moves files from your local system into the container

    - RUN – Executes shell commands during build (e.g., installing packages)

    - EXPOSE – Documents the port your app uses (note: does not actually publish it unless you use -p or --network)

    - CMD – Sets the default command to run when the container starts
    
