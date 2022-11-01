---
layout: post
title: design
nav: true
nav_order: 2
permalink: /design/

---

### problem statement

The detection of Internet censorship usually requires heavy manual inspection due to the lack of ground truth, resulting in the difficulty of identifying false positives (i.e., misclassified censorship) and false negatives (i.e., undetected censorship). The difficulty stems from the fact that without ground truth, in many cases it is unlikely to automatically distinguish the legitimate responses and the responses manipulated by censorship. Existing studies tackled such issues by retrieving and comparing distributed responses, but such an approach usually requires manual inspection, causing the analysis unscalable and inefficient.

n general, our key idea is to deploy a control server that replies with a ***static*** payload to provide the ground truth of server responses, so that the manipulation can be identified without manual efforts. We conduct a comprehensive, large-scale measurement on the censorship with fundamental protocols, including DNS, DNS-over-Encryption, HTTP, and HTTPS. Moreover, our framework facilitates extended measurements for investigating more aspects of Internet censorship. We will perform application traceroute to pinpoint censors’ locations and explore their policies and deployment. We leverage the payload conveyed by our control server to examine the keyword-based filtering in both inbound and outbound traffic at a global scale. Moreover, we aim to systematically explore how the diversity of routing paths affects the effectiveness of Internet censorship.

The detail of the framework and a comprehensive measurement study on global censorship can be found in our ACM SIGMETRICS'22 <a href="/assets/pdf/sigmetrics22.pdf">paper</a>.

---

### framework design

The framework of our proposed system design is illustrated in the Figure. The high-level idea is that a client instructs the vantage points to (1) craft DNS/HTTP/HTTPS requests with the test domain names embedded, (2) send the packets to our control server to trigger censorship, and (3) collect the response back for analysis. Our control server replies to arbitrary requests with a static payload for each type of protocol. Note that we do not send any requests to legitimate servers, and the accessed domains in the requests (if being censored) would still trigger the censorship since the censor devices will see the undesired domains but have no knowledge of whether the destination IP address is associated with a legitimate server of the censored domain. In the end, this provides us a baseline by controlling what should be expected at the client side when no censorship is involved so as to accurately recognize the censorship activities.

<img src="/assets/img/disguiser_hz.png" alt="Disguiser Design" style="max-width: 100%"/>

---

### extensive measurements

TO BE UPDATED

---

### other specific research problems

##### Exploring the Censorship of Encrypted DNS
We leverage the framework to explore and evaluate the effectiveness of adopting the emerging encrypted DNS (i.e., DoT and/or DoH) for circumventing censorship. The basic idea is to identify the vantage points (e.g., VPN servers) that suffer manipulation by encrypted DNS, from which perform DNS resolution on the censored domains via DoT/DoH resolvers, and then attempt to visit those domains for assessing the accessibility. We issue the DNS requests from the vantage points via DoT/DoH resolver to our control server that replies arbitrary DNS requests with a static DNS response. If a DNS request triggers an on-path censor, our vantage point will receive a manipulated DNS response that will be different from the static DNS response provided by the control server. In addition, we design and perform a circumvention test with those censored domains to investigate the effectiveness of the use of encrypted DNS. We consider that an encrypted DNS resolver can be used to circumvent censorship if the vantage point can retrieve legitimate web content from the censored domain. The detailed study can be found in our WWW'21 <a href="/assets/pdf/www21.pdf">paper</a>.