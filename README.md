# What is K8s?

- https://www.youtube.com/watch?v=dQMWTULEbS0

K8s (short for Kubernetes) is a bit like running multiple Docker hosts that are all communicating with one another.  
Each `node` is like a single Docker host controlled by a brain which is called a `controlled plane`.  

**Docker Swarm** was the first attempt to be able to bridge and manage multiple Docker hosts, but it was quickly superseded by K8s.  

Each node is typically a VM/physical machine running Docker.  

## K8s Scheduler

In K8s, _scheduling_ refers to making sure that **Pods** are matched to **Nodes** so that `Kubelet` can run them.  
A scheduler watches for newly created Pods 



@4/20
