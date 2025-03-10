# Resources 

- https://www.youtube.com/watch?v=dQMWTULEbS0&list=PLXHMZDvOn5sVXjb88kYXSI7UMx4rhQwOj
- https://kubernetes.io/docs/home/

# What is K8s?

Kubernetes is a portable, extensible, open source platform for managing containerized workloads and services, that facilitates both declarative configuration and automation.  

The name Kubernetes originates from Greek, meaning helmsman or pilot. K8s as an abbreviation results from counting the eight letters between the "K" and the "s".  

Google open-sourced the Kubernetes project in 2014. Netflix was one of the first companies to have integrated K8s to their stack.  

# Why you need Kubernetes?

Containers are a good way to bundle and run your applications.   
In a production environment, you need to manage the containers that run the applications and ensure that there is no downtime.   
For example, if a container goes down, another container needs to start. Wouldn't it be easier if this behavior was handled by a system?  

That's how Kubernetes comes to the rescue! Kubernetes provides you with a framework to run distributed systems resiliently.  
It takes care of scaling and failover for your application, provides deployment patterns, and more.  

# Setting up our infrastructure

## Use Proxmox Cloud-Init to Deploy Your VMs

Cloud-Init is the de facto multi-distribution package that handles early initialization of a VM instance.  
Using Cloud-Init, configuration of network devices and SSH keys on the hypervisor side is possible.  
When the VM starts for the first time, the Cloud-Init software inside the VM will apply those settings.  

Many Linux distributions provide ready-to-use Cloud-init images, mostly designed for **OpenStack**.  
These images will also work with Proxmox VE.  
While it may seem convenient to get such ready-to-use images, we usually recommend to prepare the images by yourself.  
The advantage is that you'll know exactly what you've installed, and this helps you later to customize images for your needs.  

## Ubuntu Cloud Images

- Head over to https://cloud-images.ubuntu.com/
- 
