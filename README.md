# Resources 

- https://www.youtube.com/watch?v=dQMWTULEbS0&list=PLXHMZDvOn5sVXjb88kYXSI7UMx4rhQwOj
- https://kubernetes.io/docs/home/

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
- **Kube-APIserver**: which acts as the frontend to the cluster. All external communication to the cluster is via the APIserver.
- **Kube-Controller-Manager**: which runs a set of controllers for the running cluster. It implements governance across the cluster.  
- **Etcd**: the cluster state database
- **Kube Scheduler**: which schedules activities to the worker nodes based on events occurring on the etcd. It also holds the nodes resources plan
  to determine the proper action for the triggered event. For ex, the scheduler would figure out which worker node will host a newly scheduled Pod.

In order to have high availability (HA), replication failover, etc., we need to have these Master Nodes.  
The Master Nodes sit within our K8s cluster, and their role is to manage the whole container orchestration deployments.  

The Master nodes should always be available and we should have more than one for failover.  

## Labels & Selectors

Labels are key/value pairs that are attached to objects such as Pods.  
Labels are intended to be used to specify identifying attributes of objects that are meaningful and relevant to users, but do not directly 
imply semantics to the core system.  

Labels can be used to organize and to select subsets of objects.  
They can be attached to objects at creation time, or subsequently added and modified at any time.  

Each object can have a set of key/value labels defined. Each key must be unique for a given object.  
Labels allow for efficient queries and watches, and are ideal for use in UIs and CLIs. 

Non-identifying information should be recorded using **annotations**.  

You can assign labels to different nodes within your cluster that basically instruct K8s what you want them to be used for.  




@13/20
