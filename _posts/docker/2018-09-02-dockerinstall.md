---
layout: page
sidebar: right
breadcrumb: true
comments: true
image:
    thumb:  docker-thumb.jpg
title: "Docker!"
teaser: "How to Install Docker on Ubuntu Machine"
categories:
          - docker
tags:
          - Docker
          - frameworks
          - Deployments
---
#### How to install
1. sudo apt-get update
2. apt-get install apt-transport-https ca-certificates curl software-properties-common
3. curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
4. apt-key fingerprint 0EBFCD88
5. add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
6. apt-get update
7. apt-get install docker-ce
8. Docker gets install in /var/lib/docker
9. docker version
