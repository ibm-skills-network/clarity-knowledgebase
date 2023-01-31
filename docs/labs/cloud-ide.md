---
sidebar_position: 6
---
# Cloud IDE
Cloud IDE is a browser integrated development environment running in the cloud. It supports many programming languages and tools right out of the box so that the users can start working right away without the hassle of tedious setups.
User interface of Cloud IDE, as shown below, comprises of course instructions on the left side and vscode-like development environment on the right side.

![Cloud IDE Screenshot](/img/labs/cloud-ide-screenshot.png)
## Launch a terminal
Click `Terminal` in the menu of the development environment(on the right side of the screen). Then from the dropdown select `New Terminal` and it should open up a new terminal for you.
## Docker
Docker is an open source platform that is widely used to develop, ship and run applications. Cloud-IDE has built-in support for Docker. You can simply use `docker` cli to run commands. Internally, the docker client(in your IDE) talks to docker daemon, running on a remote host, over a TCP connection. Default user(theia) is configured to run docker commands. Docker commands don't require root privileges. So, don't preface commands with `sudo` or run them with root user. Some examples are:

```
docker version
```
It prints information about the docker client and engine.

```
docker container list
```
It lists the existing containers.

### Volume Mount Points
Volume is mounted to persist data from a docker container. Currently, Cloud-IDE only allows mounting data from `/home/project` directory. For example:
```
docker run -itd --name my-first-container -v /home/project/testDir:/app ubuntu:latest
```
It spins up `my-first-container` using `ubuntu:latest` image and mounts `/home/project/testDir`(if it exists in your environment) to the `/app` directory  inside the container.

See the docker [documentation](https://docs.docker.com/engine/reference/commandline/docker/) for more commands.
## Kubernetes
Kubernetes is an open source container orchestrator which allows to schedule docker containers on large scale compute nodes. It is now a de-facto standard for cloud-native application development and deployment. Cloud-IDE is already configured to support Kubernetes. It has a pre-installed command line tool called `kubectl` that handles communication with remote kubernetes cluster. Here are a few examples:
```
kubectl run my-first-pod --restart=Never --image=ubuntu -- sleep 10s
```
It creates a `my-first-pod` that runs a container using `ubuntu` image with `sleep 10s` command. This container spawns `sleep 10s` process.

```
kubectl get pods
```

It prints existing pods in your namespace.

More commands can be found in the Kubernetes [documentation](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands)

## Embeddable AI

Cloud IDE supports various Embeddable AI services includes Text-To-Speech, Speech-To-Text, and various Watson NLP services (e.g. sentiment, emotion, etc.). Learners have immediate access to all of these services (via HTTP API calls) to learn, test, and embed in their applications. Moreover, Skills Network provides images for all of these services so learners can _deploy_ the services to the provided Code Engine Project, alongisde their applcations.

### Using the provided Services

All of the services are available to all Cloud IDE learners, for all flavours of Cloud IDE. For example the Text-To-Speech can be accessed at: https://sn-watson-tts.labs.skills.network. To help learners both know what services are available and how to use them the Skills Network Toolbox provides a page for each of the Embeddable AI services which shows:
  - Name and brief description
  - Available Models
  - Link to Documentation
  - Example Commands (with button to easily copy or run in terminal)

  <details>
  <summary><b><u>View Screenshot</u></b></summary>
  <img width="422" alt="image" src="https://user-images.githubusercontent.com/276912/215758158-2c8022b5-7d03-454e-a0bf-ed75e0d08d7d.png">
  </details>

Moreover, as an author, within Author IDE, you can add Buttons to your lab's markdown instructions to help learners open these pages with a simple button click.

### Building and Deploying to Code Engine

_Instructions Coming Soon...._
