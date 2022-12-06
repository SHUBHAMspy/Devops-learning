# Docker Learning

# What is Docker
Docker is a platform or tool for building, running and shipping applications in a consistent manner.

# Problem Solved by Docker
> "It works on my machine, but not on somebody else's machine"
i.e Software inconsistency caused by:
1. One or more files are missing in you deployment
2. Software version mismatch i.e if the target machine might be running some different version of the    software that you application needs.
3. Different configuration settings across different machines.Like environment variables might be different on different machines.

# How Docker solves it
Docker packages all our application along with its dependencies that it needs and now this package can run on any machine that runs docker.

# Virtual Machine
A virtual machine is an abstraction of a machine(physical hardware or host machine).
Virtual machines allow us to run applications in isolation.
We can run several virtual machines on a real physical machine. 
Hypervisors are use to create and manage virtual machines.

# Why Containers & Not Virtual Machines 
1. Each virtual machine needs its own full blown OS
2. They are slow to start because the entire Os needs to be loaded
3. VMs are resource intensive. They take slice of actual physical hardware resources like CPU, memory &disk space.

# Dockerfile
A dockerfile is a plain text file that includes instructions that docker uses to package our application into an image. Dockerfile files are used to build new Docker images. 

# Docker Image
Docker image as a read-only artifact containing the files you need to run a particular application. Unlike most application artifacts, a Docker image contains a complete operating system and all associated system tools required to support the core application being run like a runtime environment(eg node), all application files,third-party libraries,environment variables.

# Container
A container is an isolated environment in the OS where the Docker image is executed. Although Docker doesn't typically provide the same kind of isolation guarantees that virtual machines do, containers do provide a way to easily run trusted code side-by-sidei.e it allows running multiple apps in isolation.
They are lightweight they don't need a full blown OS because all the containers on a machine share the OS of the host and therefore they spun up or start-up very quickly. Also they need a slice of hardware resources on the host i.e no need to allocate memmory and cpu core etc.

So, basically a container is a process started by docker to execute an image or in which docker image is executed.

While Docker images are read-only, Docker containers expose a read/write filesystem allowing any running application to persist changes. The changes are local to the container though, and if the container is destroyed, the changes are lost. Or, if you want to use a different container.

# Docker Volumes
Volumes are persistent storage.
Docker volumes allow containers to persist data outside of the container's lifecycle and share it with different containers. You can think of volumes as network drives you would typically see mounted into your session when logging into an enterprise network 