# Cloud Enablement Technologies

## Learning Objectives

<li>Understanding Networking Fundamentals
<li>Identify the Enablement Technologies for Cloud-based systems
<li>Understand the differences between and demonstrate how to use virtualization technologies
<li>Understand and demonstrate how to use containers
<li>Understand what an API is used for

## Introduction

Over the past fifteen to twenty years we have shifted from a world driven by hardware purchases, software licensing, expensive IT services, and multi-year IT projects to a world where we can push a button and utilize a new IT service in a matter of minutes.  So, how did we get to this point where new IT services can be delivered immediately?  The answer is that there has been immense development over the past fifteen years or so focused on automation and software-defined services.  Infrastructure has gone from hardware-defined to software-defined, or Infrastructure as Code.  


At the same time, networks have become faster, hardware costs have dropped, virtualization has improved resource utilization, applications have become more complex, and storage options have evolved.  Networking, virtualization, containerization, object storage, software defined networking, and software defined data centers have enabled cloud platforms to experience rapid growth.  This has resulted in IT workloads rapidly shifting to the cloud at a faster pace year after year.

## Compute

### General

Cloud-based platforms utilize virtualization to carve up large pools of physical hardware resources into smaller logical hardware resources.  Virtualization software manages these logical resources, enabling more efficient usage.  

### Virtualization Technologies

Virtualization is a technique that enables multiple operating systems and application to run on a single hardware device.  The technology originated in the 1960s, but the modern version rose in popularity starting in the early 2000s.  The software that enables virtualization to occur is referred to as the hypervisor.  The hypervisor manages the physical hardware resources and allocates these resources to the virtual servers, which are also referred to as virtual machines.  Today there are typically three types of virtualization, two of which are commonly found on Cloud-platforms and the third is found on desktops and laptops.   

#### Types of Virtualization
##### Full Virtualization or Type 1 Hypervisor
In full virtualization, the hypervisor runs directly on the computer's hardware, substituting for the operating system.  Each virtual machine runs its own operating systems and applications.  These virtual machines can run any compatible operating system.  [Linux KVM](https://www.linux-kvm.org/page/Main_Page), [VMWare vSphere](https://www.vmware.com/products/vsphere.html), and [Microsoft Hyper-V](https://www.microsoft.com/en-us/evalcenter/evaluate-hyper-v-server-2019) are all examples of full virtualization.

##### Paravirtualization or Type 2 Hypervisor

With paravirtualization, the server runs an operating system such as Windows, macOS, or Linux and then a hypervisor application runs on top of that operating system.  The operating system manages the physical hardware and allocates resources to the hypervisor.  The hypervisor manages these assigned resources and assigns virtual devices to each virtual machine.  Virtual machines then run inside of the hypervisor application.  These virtual machines can run any supported operating system, so you can have an Apple Mac and run Windows, Linux, or macOS, or a Windows PC and run Windows or Linux.  Examples include [VMWare Workstation Pro (Windows)](https://www.vmware.com/products/workstation-pro.html) or [Fusion (Mac)](https://www.vmware.com/products/fusion.html), [VirtualBox Desktop](https://www.virtualbox.org/), and [Parallels](https://www.parallels.com/).

Students can [purchase VMWare products at a discount](https://store-us.vmware.com/vmware-in-education).

For a comparison of full and paravirtualization, review [VMWare's techpaper](https://www.vmware.com/content/dam/digitalmarketing/vmware/en/pdf/techpaper/VMware_paravirtualization.pdf)<br>

###### Advantages of Virtual Machines
* Multiple operating systems on physical hardware
* Easy maintenance
* More efficient use of physical hardware
* Lower total cost of ownership versus physical hardware

###### Disadvantages of Virtual Machines
* Potential resource contention when running multiple virtual machines
* Host OS or Hypervisor OS consume a large amount of the system resources
* Hypervisors are not as efficient as a Host OS
* Not lightweight
* Recovery can be slow
* Complex administration
* Lengthy boot-up times

##### Containerization

In containerization, the operating system is abstracted, rather than the hardware.  The operating system manages all hardware resources.  There are no other operating systems installed, so you only have a single operating system.  Containerization enables you to split workloads up into separate containers, which are just logical partitions that contain application related binary files and libraries, and not an entire operating system.  These containers can be created and launched in a fraction of a second, rather than minutes for virtual machines.  Containers are very lightweight, faster than virtual machines, and offer fast processing and execution.  [Docker](https://www.docker.com/) is the most common container technology in use today, but alternatives such as [LXC](https://linuxcontainers.org/), [Apache Mesos](http://mesos.apache.org/), and [Vagrant](https://www.vagrantup.com/) exist.  Container orchestration systems like [Nomad](https://www.nomadproject.io/), [Kubernetes](https://kubernetes.io/), [Amazon ECS](https://aws.amazon.com/ecs/), [Microsoft AKS](https://azure.microsoft.com/en-us/services/kubernetes-service/), and [Google GKE](https://cloud.google.com/kubernetes-engine) are used to manage these containers.

### Containers
#### Advantages
<li>Lightweight<br>
<li>Efficient<br>
<li>Fast startup<br>

#### Disadvantages
<li>Supports a single OS
<li>Management is complicated
<li>Security can be challenging<br>

<br>

### Supplemental Resources
[<li>Kubernetes in 5 Minutes](https://www.youtube.com/watch?v=PH-2FfFD2PU)<br>

[<li>Docker Tutorial](https://youtu.be/h0NCZbHjIpY)


## Storage

In traditional IT environments, storage is expensive and must be planned out far in advance.  In cloud environments, storage is inexpensive and can be procured as it is needed.

### Types of Storage
#### Block Storage
In traditional IT environments, companies like [Dell|EMC](https://www.dellemc.com/en-us/glossary/san-storage.htm) provide enterprise-class, storage area networks (SANs) that store data at the block level.  In block level storage, files are broken up into blocks and each block is written directly to a disk without a filesystem.  We use special driver software to provide direct access between our application and the underlying storage.

You can use the Lego analogy to represent a block level storage device.  We start with our favorite Lego creation (data), break that down into individual Lego blocks, and then store each Lego block in a drawer for that type of block.  When we are ready to reassemble the creation, we reference the instruction sheet and then retrieve the individual blocks from their individual storage drawers and assemble in the proper order.  This is a very fast way to retrieve our data.

Block storage is very expensive and the equipment is complex, so we typically reserve this for situations where we need high-speed and reliability, such as databases.  The good news is that cloud providers now offer block storage options to customers.  Amazon's block storage is called AWS Elastic Block Storage (EBS).

#### File-based Storage

File-based storage is a common storage method and it is what we have on our desktop and laptop computers.  There is a filesystem, the filesystem is mounted as an OS-accessible drive, and then each file is stored in a filesystem hierarchy consisting of folders, subfolders, and files.  Two common methods of file-based storage used on networks are Network File System (NFS) and Common Internet File System (CIFS).  

#### Object Storage

Object storage is used when data is defined and stored as a unique object in a database.  These objects have metadata and form storage pools that enable unlimited storage capabilities.  Object storage has metadata, which enables classification and analytical capabilities that aren't available with block or file storage.  Object storage is also much faster for your application to retrieve data.  One major benefit of object storage is that you can distribute the data across geographical locations in ways that you cannot do with other storage types.  AWS' S3 and GCP's Cloud Storage are examples of object storage in the public cloud.  Ceph is an example of object storage in an on-premise, colocation, or private cloud environment.  Modern applications often use object storage extensively.


### Ephemeral vs Persistent Storage

Ephemeral storage is short-term storage that could lead to data loss in cloud environments.  This type of storage is attached to a specific compute instance and disappears once that instance is terminated. Persistent storage on the other hand is storage where your data will persist even when compute instances are terminated.  When building cloud-based resources, it is absolutely critical that you understand the difference.  If you store critical data on ephemeral storage, then it will be lost when the compute instance attached to that storage is terminated.

Google has a [comparison of GCP and AWS storage options](https://cloud.google.com/docs/compare/aws/storage) that you may wish to review.


## Application Programming Interfaces \(APIs\)

[Application Programming Interfaces \(APIs\)](https://en.wikipedia.org/wiki/Application\_programming\_interface) are an enabling technology for cloud services as they provide mechanisms for automated application interactions.  APIs provide protocols and tools that enable services to interoperate.  Cloud service providers provide APIs to enable the automatic provisioning and management of services.  We will be utilizing a variety of different APIs in this course as we explore [GCP](https://cloud.google.com/apis/docs/overview), [AWS](https://docs.aws.amazon.com), and other tools. 
