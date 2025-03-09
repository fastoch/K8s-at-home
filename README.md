# Resources 

- https://www.youtube.com/watch?v=dQMWTULEbS0
- 

# What is K8s?

Kubernetes was originally developed by Google, and then open-sourced (Cloud Native Computing Foundation).  
Netflix championed it by integrating it into their stack, and deliberately killing pods to test resiliency. 

Using K8s (short for Kubernetes) is a bit like running interconnected Docker hosts that we call nodes.  
- A K8s **node** is typically a VM or a physical machine running Docker.
- All nodes are controlled by a brain which is called a **controlled plane**.  

**Docker Swarm** was the first attempt to bridge and manage multiple Docker hosts, but it was quickly superseded by K8s.  

## K8s Scheduler

In K8s, _scheduling_ refers to making sure that **Pods** are matched to **Nodes** so that **Kubelet** can run them.  

A scheduler watches for newly created Pods that have no Node assigned.  
For every Pod that the scheduler discovers, the scheduler becomes responsible for finding the best Node for that Pod to run on.  

## Horizontal Pod Autoscaling

In K8s, a _HorizontalPodAutoscaler_ automatically updates a workload resource (such as a _Deployment_ or _StatefulSet_), 
with the aim of automatically scaling the workload to match demand.  

Horizontal scaling means that the response to increased load is to deploy more Pods.  
This is different from vertical scaling, which for K8s would mean assigning more resources (CPU, memory) to the Pods that 
are already running for the workload. 

If the load decreases, and the number of Pods is above the configured minimum, the HorizontalPodAutoscaler instructs the 
workload resource to scale back down.

## What is a Master Node?

It's a Node which controls a set of worker nodes (workloads runtime) and resembles a cluster.  
A Master Node has the following components to help manage worker nodes:
- **Kube-APIServer**:
- **Kube-Controller-Manager**:
- **Etcd**:
- **Kube Scheduler**:


@10/20
