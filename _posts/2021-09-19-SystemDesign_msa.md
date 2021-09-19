---
layout: post
title: MSA - Micro Service Architecture
description: "System Design MSA"
modified: 2021-08-22
tags: [System Design]
categories: [System Design]
---

## MSA 

- Existing system
    - Install APPlication (program) on top of system (infrastructure)
    - **MONOLIX** : ONE SINGLE APPLICATION / SYSTEM

- **MSA**: Split by function
    - micro
    - Why..? splitting ??
        - What's better...?
        - Communication between splitted systems is possible
        - Increased complexity
        - ex 1) A failure occurred in Netflix: All services were down
            - **Advantages 1** > **Let's prevent the entire site from failing at the same time!**
            - stop some of the services among whole system
        - ex 2) Running multiple services in one application
            - service 1 : inquiry
            - service 2 : payment
            - service 3 : settlement
            - **Advantage 2** > If, among the services, "inquiry" service occupies 90% of API calls among all functions
                - In this case, MSA is introduced from the perspective of **infrastructure efficiency**
                - Introduction of Auto-scale function
            - **Advantage 3** > **When frequent update / distribution is required** 
                - Only some services update / distribute only the function


- **ROI** : Need to consider *Return of Investment*


## Docker
> Each service split in MSA is managed as individual **IMAGE** through Docker  
> In Docker, each service is managed as a separate image, not as a VM  


- Docker: very easy to scale compared to VM  

## DevOps 
> Each service divided in MSA can be divided into tasks such as function development / operation infrastructure management  
> **DevOps: Development + Operations**  


## SRE (Site Reliability Engineering)
> SRE: Technology to operate a stable site  


### Point
> Manage large-capacity services based on Service Docker while taking them to the MSA structure  
> MSA functional unit managed / developed by DevOps team  
> The goal of DevOps is to operate a site with stable / trust considering SRE  