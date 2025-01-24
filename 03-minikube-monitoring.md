# Some Basic monitoring with Minikube

## My Thoughts
- It's great to be able to just scale up and down the number of pods, and see how they're distributed across the nodes.
- It's also great to be able to see the logs for the pods, and see what's happening.
- Prometheus provides more than enough data out of the box for minikube.
- It's fun to scale them up and down on the CLI, but next I will move onto Chaos Engineering.

## Steps

### 1. Add some nodes

Repeat this a couple of times to add more nodes to the cluster:

```bash
minikube node add
```
![](./screenshots/add-node.png)

### 2. Deploy a sample application

This is an example deployment from the Kubernetes docs:

```bash
kubectl create deployment hello-node --image=registry.k8s.io/e2e-test-images/agnhost:2.39 -- /agnhost netexec --http-port=8080
```

![](./screenshots/get-deployments.png)


### 3. Scale the deployment

Scale the deployment to 5 replicas, spread accross the nodes:

```bash
kubectl scale deployment hello-node --replicas=5
```

### 4. Check the deployment

Check how the pods are distributed across the nodes:

```bash
kubectl get pods -o wide
```
![](./screenshots/scaled-deployment.png)

### 5. Remove the nodes

I've chosen to remove the extra nodes, but you can leave them running if you want to keep them around for other experiments. Kubernetes will automatically reschedule the pods to the remaining node/nodes.

```bash
minikube node delete <node-name>
```






