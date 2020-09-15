# Introduction

Microservices are an architectural approach to building applications. As an architectural framework, microservices are distributed and loosely coupled, so one team’s changes won’t break the entire app. The benefit to using microservices is that development teams are able to rapidly build new components of apps to meet changing business needs.

![](../.gitbook/generic/monolithic-vs-microservices.png)

* You can build polyglot microservices
* Each microservice can be assigned to a team
* Scale each independently
* Can provide resiliency

## The example bank application

The example bank system includes several microservices for handling user authentication and transaction mechanics.

![Example Bank App Architecture](../.gitbook/generic/image%20%281%29.png)

This lab focuses on the java microservices components that is part of the Example Bank app.

* Build and push Java Open Liberty Microservices
* Deploying applications in an OpenShift cluster using container images from Docker Hub
* Exposing and accessing your application in an OpenShift cluster

A live demo of the app: [https://credit-card.ibmdeveloper.net/](https://credit-card.ibmdeveloper.net/)
