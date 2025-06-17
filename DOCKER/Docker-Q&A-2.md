## 1. **What is the Dockerfile and what are some instructions ?

* A Dockerfile is a script containing a series of instructions on how to build a Docker image. Key instructions include:

    - FROM – Defines the base image (e.g., node, alpine, ubuntu, etc.)

    - WORKDIR – Sets the working directory inside the container

    - COPY – Moves files from your local system into the container

    - RUN – Executes shell commands during build (e.g., installing packages)

    - EXPOSE – Documents the port your app uses (note: does not actually publish it unless you use -p or --network)

    - CMD – Sets the default command to run when the container starts
    
##WXAMPLE

Use an official Node.js base image
FROM node:18
Set the working directory
WORKDIR /usr/src/app
Copy package.json and install dependencies
COPY package*.json ./
RUN npm install
Copy your app source code
COPY . .
Expose port your app runs on
EXPOSE 3000
Start the app
CMD ["npm", "start"]

## 2. Difference between ENV and ARG in Docker ?

- **ARG**: Defines a variable that uses can pass at build-time
- **ENV**: Sets an environment variable in the container at run-time.

* Example:
```Dockerfile
ARG build_version
ENV APP_VERSION $build_version
```
