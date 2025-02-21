# Advanced Features

Welcome to the advanced features guide for Cloud IDE. Whether you're developing applications, managing containers, or deploying AI services, Cloud IDE is flexible enough to provide learners with many of the tools they would need.

In this guide, we will cover:

- **Docker**: Learn how to use Docker within Cloud IDE to develop, ship, and run applications seamlessly.
- **Kubernetes**: Discover how Cloud IDE integrates with Kubernetes for container orchestration and management.
- **Embeddable AI**: Explore the AI capabilities available in Cloud IDE, including Text-To-Speech, Speech-To-Text, and Watson NLP services.
- **Deployment to Code Engine**: Understand how to deploy your applications and AI services to IBM Cloud's Code Engine for a scalable and serverless experience.

Let's dive into each of these features to see how they can enhance your development process.

## Docker (Cloud IDE with Kubernetes, Cloud IDE with Openshift)
Docker is an open source platform that is widely used to develop, ship and run applications. Cloud-IDE has built-in support for Docker. You can simply use `docker` cli to run commands. Internally, the docker client(in your IDE) talks to docker daemon, running on a remote host, over a TCP connection. Default user(theia) is configured to run docker commands. Docker commands don't require root privileges. So, don't preface commands with `sudo` or run them with root user. Some examples are:

```
docker version
```
It prints information about the docker client and engine.

```
docker container list
```
It lists the existing containers.

### Volume Mount Points (Cloud IDE with Kubernetes, Cloud IDE with Openshift)
Volume is mounted to persist data from a docker container. Currently, Cloud-IDE only allows mounting data from `/home/project` directory. For example:
```
docker run -itd --name my-first-container -v /home/project/testDir:/app ubuntu:latest
```
It spins up `my-first-container` using `ubuntu:latest` image and mounts `/home/project/testDir`(if it exists in your environment) to the `/app` directory  inside the container.

See the docker [documentation](https://docs.docker.com/engine/reference/commandline/docker/) for more commands.

## Kubernetes (Cloud IDE with Kubernetes)
Kubernetes is an open source container orchestrator which allows to schedule docker containers on large scale compute nodes. It is now a de-facto standard for cloud-native application development and deployment. Cloud-IDE with Kubernetes is already configured to support Kubernetes. It has a pre-installed command line tool called `kubectl` that handles communication with remote kubernetes cluster. Here are a few examples:
```
kubectl run my-first-pod --restart=Never --image=ubuntu -- sleep 10s
```
It creates a `my-first-pod` that runs a container using `ubuntu` image with `sleep 10s` command. This container spawns `sleep 10s` process.

```
kubectl get pods
```

It prints existing pods in your namespace.

More commands can be found in the Kubernetes [documentation](https://kubernetes.io/docs/reference/generated/kubectl/kubectl-commands)

## Embeddable AI (All Cloud IDE versions)

Cloud IDE supports various Embeddable AI services includes Text-To-Speech, Speech-To-Text, and various Watson NLP services (e.g. sentiment, emotion, etc.). Learners have immediate access to all of these services (via HTTP API calls) to learn, test, and embed in their applications. Moreover, Skills Network provides images for all of these services so learners can _deploy_ the services to the provided Code Engine Project, alongisde their applcations (only availble in Cloud IDE with Kubernetes and Cloud IDE with Openshift).

### Using the provided Services 

All of the services are available to all Cloud IDE learners, for all flavours of Cloud IDE. For example the Text-To-Speech can be accessed at: https://sn-watson-tts.labs.skills.network. To help learners both know what services are available and how to use them the Skills Network Toolbox provides a page for each of the Embeddable AI services which shows:
  - Name and brief description
  - Available Models
  - Link to Documentation
  - Example Commands (with button to easily copy or run in terminal)

<details>
  <summary><b><u>View Screenshot</u></b></summary>
  <img width="422" alt="Skills Network Toolbox interface displaying various AI and NLP tools. Categories include Databases, Big Data, Cloud, and Embeddable AI. Under Embeddable AI, active features include Text-To-Speech and Speech-To-Text. The Watson NLP section lists active features such as Sentiment (BERT, CNN), Categories, Classification, Concepts, Detag, Emotion, Keywords, Language Detection, Noun Phrases, Relations (Transformer), and Syntax. Features labeled 'Coming Soon' include Entity-Mentions (BERT) and Relations (SIRE)." src="https://user-images.githubusercontent.com/276912/215758158-2c8022b5-7d03-454e-a0bf-ed75e0d08d7d.png" />
</details>

Moreover, as an author, within Author IDE, you can add Buttons to your lab's markdown instructions to help learners open these pages with a simple button click. For example, the following markdown creates a button that launches an application running on port 5000:

```
::startApplication{port="5000" display="internal" name="Web Application" route="/"}  
```

The following markdown creates a button that opens the file `test.py` located in the `/home/project` directory:

```
::openFile{path="/home/project/test.py"}
```

### Building and Deploying to Code Engine (Cloud IDE with Kubernetes, Cloud IDE with Openshift)
If you would like to deploy any of the above-mentioned Embeddable AI NLP service and have it be available for anyone to use, you can follow these steps in order to deploy it. The deployment will be to IBM Cloud's Code Engine. IBM Cloud Code Engine is a fully managed, cloud-native service for running containerized workloads on IBM Cloud. It allows developers to deploy and run code in a secure, scalable and serverless environment, without having to worry about the underlying infrastructure.

[... rest of the Code Engine deployment sections ...] 