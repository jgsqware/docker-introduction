class: middle,center
# Docker
## Introduction to containers

.center[![:scale 20%](images/wemanity.png)]

---
.logo[![:scale 7%](images/wemanity-logo.png)]

# Who am I?

</br>
.profile_title[Julien Garcia Gonzalez]

.profile_t[![:logo 30px, 10px](images/wemanity-logo.png)Devops facilitator]

.profile_t[![:logo 30px, 10px](images/twitter-logo.png)[@jgsqware](https://twitter.com/jgsqware)]
.profile_t[![:logo 30px, 10px](images/github-logo.png)[github.com/jgsqware](http://www.github.com/jgsqware)]

.profile[![:scale 40%](images/profile.jpg)]

</br></br>
.center[![:logo 100px, 30px](images/docker-logo.png)![:logo 50px, 30px](images/golang-logo.png)![:logo 50px, 30px](images/jenkins-logo.png)![:logo 70px, 30px](images/ansible-logo.png)![:logo 70px, 30px](images/chef-logo.png)]
---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# One step in the IT world

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar One step in the IT world - Dark ages]

.center[# One application on One physical server]

.center[![](images/docker/one_app_one_physical.png)]

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar One step in the IT world - Dark ages]

.center[# One application on One physical server]

- Huge cost
- Wasted resources
- Difficult to scale/migrate

.center[![](images/docker/one_app_one_physical.png)]

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar One step in the IT world - Lighter ages]

.center[# Hypervisor-based VMs]

.center[![](images/docker/hypervisor.png)]

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar One step in the IT world - Lighter ages]

.center[# Hypervisor-based VMs - Pros]

- Multiple VMs on One host
- Better scaling
- Pay as you go model

.center[![:scale 60%](images/docker/hypervisor.png)]

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar One step in the IT world - Lighter ages]

.center[# Hypervisor-based VMs - Cons]

- Dedicated CPU, Ram, Storage
- Entire OS => Wasted resources
- More VMs == More resources
- Application portability note guaranteed
.center[![:scale 60%](images/docker/hypervisor.png)]

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# One step further

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# One step further
.big[The Deployment nightmare]

---
class: center
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar One step further - The Deployment nightmare]
</br>
![:scale 100%](images/docker/matrix.png)

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar One step further - The Deployment nightmare]

</br></br>
![:scale 110%](images/docker/deployment-nightmare.png)

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# How to fix it?
.big[Back in time ...]

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How to fix it? - Back in time ...]

</br></br>
![:scale 110%](images/docker/transport-analogy.png)

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How to fix it? - Back in time ...]

</br></br>
![:scale 110%](images/docker/transport-analogy-container.png)

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# And Now? For IT?

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# Docker 

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar Docker]

</br></br>
![:scale 110%](images/docker/deployment-dream.png)

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar Docker]

</br></br>
![:scale 110%](images/docker/matrix-filled.png)

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# What is Docker ?

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# Containers vs VMs

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar Containers vs VMs]

</br></br>
![:scale 110%](images/docker/vms.png)

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar Containers vs VMs]

- Separation of concerns
    - Developers focus on building their apps
    - System admins focus on deployment
- Fast development cycle
- Application portability
- Build in one environment, ship to another
- Scalability
    - Easily spin up new containers if needed
- Run more apps on one host machine

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# How is it done?

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How is it done?]

# From Kernel

Usage of **CGroup** + **Namespace**

- Resource management: CPU, Memory
- Isolation
- Security

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How is it done?]

# From Filesystem

Containers are made from **Layers**

    - Copy-on-write Filesystem
    - Shared between containers
    - Can be cached

![:scale 110%](images/docker/layers.png)

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How is it done?]

# Networking

- **Private Network** between container
- **Overlay network** if multiple nodes

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How is it done?]

# Persistence

- Usage of volume
    - external Filesystem
- Shared between container
- Local or remote (AWS, NFS,...)

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# How can I build it?

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How can I build it?]

Dockerfile

```
FROM open-jdk:8

```
- Example
- Each entry is a Layers
- Caching System
- FROM -> show docker hub

---

Front-End, Back-end, DB? How to manage them?

---

Docker-compose

- Example
- v2
    - services
    - volumes
    - networks

---

How can I share my images?

---

Docker Hub & Docker Registry

---

Production environment, how can I orchestrate it?

---

Docker Swarm

- Cluster of docker nodes
- orchestration
- scheduler
- swarm-cluster image

---

---

Is it ready for Production?

---

- Company using it
- Provider
- Security matrix

Demo

- Show docker commands (image, run, ps, rm, rmi)
- Show voting app Dockerfile
- Build voting app
- Show docker-compose for voting app
- Deploy voting app
- Make a change
- rebuild and redeploy

- Deploy swarm cluster
- Deploy voting app on it