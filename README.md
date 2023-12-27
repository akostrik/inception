**Docker** a set of platform as a service (PaaS) products that use OS-level virtualization to deliver software in packages called **containers**.   
* Automates the deployment of applications in containers => applications can work efficiently in different environments in isolation.  
* Implements a high-level API to provide lightweight containers that run processes.
* Packages an application and its dependencies in a virtual container that can run on Linux / Windows / macOS => the application ca be run in a variety of locations (on-premises, in public clouds such as decentralized computing, distributed computing, cloud computing, in private cloud).  

* The containers are isolated from one another.  
* A container bundles its own software, libraries and configuration files.  
* Containers can communicate with each other through well-defined channels.  
* **Docker Engine** the software that hosts the containers.  
* A typical Docker use case runs 8 containers per host.

# Efficency
* Containers are lightweight => a single server or virtual machine can run several containers simultaneously.  
* Containers share the services of a single operating system kernel => use fewer resources than virtual machines.  
* Linux: Docker uses the resource isolation features of the Linux kernel (cgroups, kernel namespaces) and a union-capable file system (OverlayFS) to allow containers to run within a single Linux instance, avoiding the overhead of starting and maintaining virtual machines.  
* MacOS: Docker uses a Linux virtual machine to run the containers.  
The Linux kernel's support for namespaces mostly isolates an application's view of the operating environment, including process trees, network, user IDs and mounted file systems, while the kernel's cgroups provide resource limiting for memory and CPU.  
Since version 0.9, Docker includes its own component (called **libcontainer**) to use virtualization facilities provided directly by the Linux kernel, in addition to using abstracted virtualization interfaces via libvirt, LXC and systemd-nspawn.

# Components
The Docker software as a service offering consists of three components:
* Software: The Docker daemon (**dockerd**) = a persistent process that manages Docker containers and handles container objects. listens for requests sent via the **Docker Engine API**.
  The Docker client program (**docker**) provides a command-line interface (CLI) that allows users to interact with Docker daemons.
* **Docker objects** = various entities used to assemble an application in Docker:
    + A **Docker container** = a standardized, encapsulated environment that runs applications. is managed using the Docker API or CLI. It is a process created from an image.
    + A **Docker image** = a read-only template used to build containers. Is used to store and ship applications. It is a process image.
    + A **Docker service** allows containers to be scaled (?) across multiple Docker daemons. The result is known as a **swarm**, a set of cooperating daemons that communicate through the Docker API (?).
* A **Docker registry** = a repository for Docker images. Docker clients connect to registries to pullimages for use or push images that they have built. Allows the creation of notifications based on events. **Docker Hub** = the main public registry. 
