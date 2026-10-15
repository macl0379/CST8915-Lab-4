# CST8915-Lab-4

**Student Name**: Collin MacLeod
**Student ID**: macl0379
**Course**: CST8915 Full-stack Cloud-native Development
**Semester**: Fall 2026

---

## Introduction

In this lab, we will be exploring Docker and its capabilities in creating, managing, and deploying containerized applications. We will learn how to build Docker images, run containers, and utilize Docker Compose for orchestrating multi-container applications. This lab will provide hands-on experience with Docker's layered architecture and the benefits of containerization in a cloud-native development environment.

---

## Demo Video

🎥 [Watch Demo Video](https://youtu.be/fb891VG9Mss)

---

## Questions

### What are the main differences between a Docker image and a Docker container?

Images are a read only template that is used as a template to create Docker containers. This template includes everything (dependancies, code, libraries) that is required to run an application and can be used to create multiple containers. This template remains unchanged by the actions in any container. Containers are individual instances of an image whose environment is independent of the image it is derived from and other containers based on the same image. They contain a writable layer that allows for execution of the application.

### Explain how Docker's layered architecture improves efficiency.

Docker's layers and how they are shared between images can speed up development and improve scalability. By sharing layers, each container pulls a majority of what it needs to run without using up any additional space by storing complete individual filesystems. With these shared layers, builds can happen quickly only having the run through layers that have changed pulling on cached layers for everything else. The writable layer to each container allows for multiple instances to be running that won't affect each other. This enables a good CI/CD workflow for testing and development with containers effectively acting as active branches with each instance being able to run testing on code changes in an exact environment that is easily replicable.

### Why does each container get its own writable layer?

To allow each container to run independently of each other and allow for testing and development. Without a writeable layer, these containers wouldn't be usable for development and testing. These containers will not affect other instances when operating and any changes can be made to the instance file system while maintaining the integrity of the shared layers. 

### What are the benefits of using Docker Compose over running containers individually?

Docker Compose allows for easy management and monitoring of multiple containers using fewer files and less commands meaning less time for deployment, maintenance. You can spin up all containers at the same time as was done here when firing up the python and redis containers, and also scale containers through the command line. These deployments stay consistent as they are pulling from the same YAML file. Docker Compose also initiates networking automatically meaning you don't have to update the environment for each container and allows for centralization of application logs and data.

## References

Docker, How Compose works
https://docs.docker.com/compose/intro/compose-application-model/

Docker, Networking in Compose
https://docs.docker.com/compose/how-tos/networking/

Docker, Why use Compose?
https://docs.docker.com/compose/intro/features-uses/

## Acknowledgment

In this lab I used ChatGPT to find additional readings and giving me starting points for answering any questions I had. Copilot provided a simple introduction summary to the lab.

