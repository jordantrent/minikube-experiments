# Setting up the Kubernetes Cluster with Minikube

## My Thoughts

- Minikube is a great way to get started with Kubernetes, I can just focus on gaining an understanding of the basics.
- The CLI is powerful, and makes it very easy to get going. I'm not sure if I'll ever need to use the GUI, but it's nice to have it available.
- The docs are great, and providing you have a basic understanding of the terminal, you can get started quickly.
- The dashboard is a great way to get a feel for the cluster, I'm really excited to see what it can do.
- I'm on Windows, using Windows Terminal, you've got to make sure Docker Desktop is running for the docker driver to work.

## Prerequisites
- Install Minikube: [Minikube Installation Guide](https://minikube.sigs.k8s.io/docs/start/)
- Install `kubectl`: [Kubectl Installation Guide](https://kubernetes.io/docs/tasks/tools/)
- Install Docker: [Docker Installation Guide](https://docs.docker.com/get-docker/)

## Steps

### 1. Start Minikube
```bash
minikube start --driver=docker
```
![](./screenshots/start-minikube.png)

### 2. Verify Cluster Status
```bash
kubectl cluster-info
```
![](./screenshots/cluster-status.png)

### 3. Enable Minikube Addons
Enable useful addons like the dashboard:
```bash
minikube addons enable dashboard
```

![](./screenshots/dashboard-enable.png)

### 4. Access the Dashboard
Start the dashboard:
```bash
minikube dashboard
```

