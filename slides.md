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
.profile_t[![:logo 30px, 10px](images/github-logo.png)[CoreOS Clair](https://github.com/coreos/clair)] maintainer


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
- Application portability not guaranteed
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

</br>
![:scale 100%](images/docker/transport-analogy.png)

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How to fix it? - Back in time ...]

</br>
![:scale 100%](images/docker/transport-analogy-container.png)

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# And Now? For IT?

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

![:scale 100%](images/docker/docker-logo.png)

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

</br>
.center[![:scale 65%](images/docker/vms.png)]

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

.img-right[![:scale 100%](images/docker/layers.png)]
---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How is it done?]

# Networking

- **Private Network** between container
- **Overlay network** if multiple nodes

.center[![:scale 60%](images/docker/networking.gif)]

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

# Dockerfile

```
FROM alpine
MAINTAINER Julien Garcia Gonzalez <jgonzalez@wemanity.com>

COPY ./hugo_0.14_linux_amd64 /bin/hugo
ENV HUGO_THEME hyde
RUN mkdir /hugo
WORKDIR "/hugo"
ENTRYPOINT exec hugo server -b http://"hugo-server" -p "59000" /hugo

EXPOSE 1313
```
---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How can I build it? Dockerfile]

# Dockerfile

```
FROM alpine
MAINTAINER Julien Garcia Gonzalez <jgonzalez@wemanity.com>

COPY ./hugo_0.14_linux_amd64 /bin/hugo
ENV HUGO_THEME hyde
RUN mkdir /hugo
WORKDIR "/hugo"
ENTRYPOINT exec hugo server -b http://"hugo-server" -p "59000" /hugo

EXPOSE 1313
```

- Each entry is a Layers
- Intermediate layers are cached to speed up the next build
- `FROM` <- Image coming from repository

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# Application = Front-End, Back-end, DB,...
.big[How to manage them?]

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar Applications. How to manage them?]
.img-right[![:scale 100%](images/docker/docker-compose-logo.png)]
# Docker-compose

```
version: "2"

services:
  vote:
    build: ./vote
    command: python app.py
    volumes:
     - ./vote:/app
    ports:
      - "5000:80"

  redis:
    image: redis:alpine
    ports: ["6379"]

  worker:
    build: ./worker

  db:
    image: postgres:9.4
```

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# How can I share my images?

---
class: center 
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How can I share my images?]

# Docker Hub
# Docker Store
# Docker Registry  

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How can I share my images? Docker Hub]

# Docker Hub

- Image Repositories
- Automated Builds
- Webhooks
- Organizations
- GitHub and Bitbucket Integration

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How can I share my images? Docker Hub]

![:scale 100%](images/docker/hub.png)

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How can I share my images? Docker Store]

# Docker Store

- Same features as Docker Hub
- Trusted commercial and free software distributed as Docker Images.

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How can I share my images? Docker Store]

![:scale 100%](images/docker/store.png)

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How can I share my images? Docker Registry]

# Docker Registry

- Stateless
- Highly scalable
- On-Premise
- Your own distribution pipeline

.center[.note[**No GUI integrated**]]

.img-right-b[![:scale 70%](images/docker/docker-registry.png)]

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar How can I share my images? Docker Registry]

Registry UI from Community:

### Commercial
- [Docker Trusted Registry](https://docs.docker.com/docker-trusted-registry/)

### Free
- [Portus](http://port.us.org/)
- [Hyper - Registry UI](https://github.com/mkuchin/docker-registry-web)
- [jgsqware - Registry UI](https://github.com/jgsqware/registry-ui)

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# Production environment
.big[How can I orchestrate it?]

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar Production environment, how can I orchestrate it?]

# Docker Swarm mode

- Cluster management integrated with Docker Engine
- Decentralized design image.
- Declarative service model
- Scaling
- Desired state reconciliation
- Multi-host networking
- Service discovery
- Load balancing
- Secure by default
- Rolling updates

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar Production environment, how can I orchestrate it? Docker Swarm mode]

![:scale 100%](/images/docker/swarm-cluster.png)

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# Enterprise version?

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar Enterprise version?]

# Docker Datacenter

- Out of the box Container-As-A-Service
- Build Workflow
- Build, manage and deploy
- On-premise

.img-right[![:scale 70%](images/docker/docker-datacenter-logo.png)]

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar Enterprise version?]

![:scale 100%](/images/docker/data-center.1.png) 

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar Enterprise version?]

![:scale 100%](/images/docker/data-center.2.png) 


---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# OK! But is it really used?

---
.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar OK! But is it really used?]

# Customers

.center[![:logo 100px, 30px](images/docker/paypal-logo.png)![:logo 100px, 30px](images/docker/spotify-logo.png)![:logo 100px, 30px](images/docker/ebay-logo.png)![:logo 100px, 30px](images/docker/ge-logo.png)![:logo 100px, 30px](images/docker/ing-logo.png)![:logo 100px, 30px](images/docker/swisscom-logo.png)]

---

.logo[![:scale 7%](images/wemanity-logo.png)]
![:title_bar OK! But is it really used?]

# Providers

.center[![:logo 100px, 30px](images/docker/aws-logo.png)![:logo 100px, 30px](images/docker/docker-cloud-logo.png)![:logo 100px, 30px](images/docker/gcp-logo.png)![:logo 100px, 30px](images/docker/digital-ocean-logo.png)![:logo 100px, 30px](images/docker/packet-logo.png)]

---
class: middle, center
.logo[![:scale 7%](images/wemanity-logo.png)]

# Demo

---
- Show docker commands (image, run, ps, rm, rmi)
- Show voting app Dockerfile
- Build voting app
- Show docker-compose for voting app
- Deploy voting app
- Make a change
- rebuild and redeploy

- Deploy swarm cluster
- Deploy voting app on it