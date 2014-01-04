---
layout: post

title: Docker will change everything
permalink: /articles/docker-will-change-everything/

excerpt: "Docker has excited may developers, devops and hosting providers, I share some my views and excitement about the project"

categories:
  - Thoughts

bitcoin: 1EYqFucUiTJPmjrRhFTQxRj84MhRZ9s3Bw
litecoin: LfEo2hMfKHK5HPdm3QoeGxDyNqrbEJL5Dv
namecoin: NEN5AJAagvLEpW8RY6s4fYZYkSBQE9CEXA
dogecoin: DPPjPdajmqoHx3Wq28z5VuchE1PEaAMj9d

author: 
  name: Sathish
  twitter: sathishmanohar
  bio: Co-founder Invoice Jet and Work Life
  image: sathish.png

---

> [Docker] [1] is an open-source engine that automates the deployment of any application as a lightweight, portable, self-sufficient container that will run virtually anywhere.
from: [Docker Learn More] [2]

Yea. But what is docker you ask? Let me try.

Until now, if you need to run any application in production, you need to have the environment setup with great care with all dependencies in place. 

For example, if you have a rails application that runs on ubuntu server with ruby 2.0.0, latest version of rails and mysql for database. you need to have production environment setup with all these dependencies and deploy your application on top of it.

But what happens when there is another rails application that uses the same stack. you need to setup _another instance_ identical to the previous one to run the second application in production.

You might have sensed the problem docker is trying to solve. Docker tries to make it possible to share underlying resources between applications without stepping on each others toes. To put it even simpler docker tries to make production applications run on shared resources like a desktop user runs several programs inside the same operating system.

I think docker project is going to have huge impact on several front. I'll list some of them below.

## Cloud Platforms
Current cloud platforms offers on demand scaling and pay for _only_ what you use model (but not quite).

### Provision and Build times
At present cloud scenario, you need to have a bare minimum instance running all the time to serve any application. Technically as a customer of the cloud provider you are using a less powerful instance even if any of your users are presently not using the app.

This is expected for cloud applications because of attributes related to cloud instances like provision time, build time etc which takes at least few minutes. So you need to have an instance in place just in case.

This is where docker shines a lot, provision time and build time are almost non-existent, even starting a docker container takes less than a second in some cases. This attribute of docker almost eliminates the need for an instance with a dedicated processor, memory and disk space running all the time.

### The instance abstraction
Cloud providers charge for instances which are virtual isolated operating systems. User pays for these instances for the time they use them. These instances are actually isolated and each of its own, hence charging for instance is justified.

In a container scenario, the operating system is shared among containers and since there is no need for those containers to have dedicated processor power or memory all the time, the instance abstraction can go away and pay for what you _actually use_ models can emerge.

Specialized service providers like database hosting, image processing providers can hugely benefit from this decoupling from instances. Instead of choosing services in terms of allocated resources, pluggable services charged based on actual service usage can emerge. Finally underlying machine can be abstracted away in favor of actual service metering.

### Pay by the hour model
Most cloud hosting companies bill customers by the hour (even if you kill the instance after 15 minutes of use), which is lot better compared to old ways of buying physical dedicated hardware in advance. But, its still not pay for what you use. With a shared resources environment like docker, new hosting companies can emerge that charges only for the CPU cycles and memory actually used by the customers.

## Development Ease
Up until now, developers are required to maintain different development and production environments. This inconsistency inevitably leads to issues. Docker promises to eliminate this situation by making it possible to develop on the same container that will be deployed in production, which will make development a lot easier and deployment lot less painful.

[1]: http://www.docker.io/ "Docker Official Website"
[2]: http://www.docker.io/learn_more/ "Docker Learn More"
