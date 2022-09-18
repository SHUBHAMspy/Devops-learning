# Docker Learning

Docker image as a read-only artifact containing the files you need to run a particular application. Unlike most application artifacts, a Docker image contains a complete operating system and all associated system tools required to support the core application being run.

A container is an isolated environment in the OS where the Docker image is executed. Although Docker doesn't typically provide the same kind of isolation guarantees that virtual machines do, containers do provide a way to easily run trusted code side-by-side.

While Docker images are read-only, Docker containers expose a read/write filesystem allowing any running application to persist changes. The changes are local to the container though, and if the container is destroyed, the changes are lost. Or, if you want to use a different container.

Docker volumes allow containers to persist data outside of the container's lifecycle and share it with different containers. You can think of volumes as network drives you would typically see mounted into your session when logging into an enterprise network

Dockerfile files are used to build new Docker images. 