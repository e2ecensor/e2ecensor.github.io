---
layout: page
title: knowledge base
permalink: /knowledge-base/
description: a collection of technical background of Internet censorship.
nav: true
nav_order: 6
horizontal: false
---
### Technical Background of Internet Censorship

Internet censorship controls what can be viewed by a certain group of Internet users. Such information control, typically placed by authority entities such as governments, ISPs, or organizations, can be achieved by various techniques like IP-layer censorship (e.g., blocking IP addresses) and application-layer censorship (e.g., domain names based blocking in DNS, HTTP, and HTTPS), and its severity varies from country to country. This proposed research will focus on application-layer censorship, as it typically enables the censors to accurately block their undesired Internet services while avoiding collateral damage caused by prevalent IP sharing in Cloud or CDN platforms. 

##### Application-Layer Censorship

##### On-path and In-path Censors
In order to examine network traffic, censorship devices can be deployed in two different ways. An on-path censor is a device attached to a router and can obtain a copy of all the packets passing through the router. Since it cannot operate on the original packets, it is unable to prevent the packets from reaching their destinations. Correspondingly, it needs to inject packets to interfere or terminate a connection. An in-path censor acts as a Man-In-The-Middle (MITM) to examine the actual packets. Therefore, it can directly manipulate or drop the packets associated with the prohibited services. The in-path device is usually hard to be identified; however, due to the capacity of operating on the actual packets, it can be efficiently detected in our proposed approach.

### State-of-the-art and Significant Research

##### OONI: Open Observatory of Network Interference
[OONI](https://ooni.org/) 

##### Iris: Global Measurement of DNS Manipulation
*Paul Pearce, Ben Jones, Frank Li, Roya Ensafi, Nick Feamster, Nick Weaver, Vern Paxson. in USENIX Security Symposium, 2017.*

##### ICLab: A Global, Longitudinal Internet Censorship Measurement Platform

*Arian Akhavan Niaki, Shinyoung Cho, Zachary Weinberg, Nguyen Phong Hoang, Abbas Razaghpanah, Nicolas Christin, Phillipa Gill. in IEEE Symposium on Security and Privacy (S&P), 2020.*

##### Quack: Scalable Remote Measurement of Application-Layer Censorship

*Benjamin VanderSloot, Allison McDonald, Will Scott, J. Alex Halderman, and Roya Ensafi. in the Proceedings of the 27th USENIX Security Symposium, 2018.*

##### FilterMap: Measuring the Development of Network Censorship Filters at Global Scale
*Ram Sundara Raman, Adrian Stoll, Jakub Daleky, Reethika Ramesh, Will Scottz, Roya Ensafi. in Network and Distributed Systems Security (NDSS) Symposium, 2020.*

### Disguiser and Comparison
