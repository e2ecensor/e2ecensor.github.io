---
layout: post
title: design
nav: true
nav_order: 2
permalink: /design/

---

### problem statement

This proposed research aims to explore, develop, and deploy a framework that enables end-to-end measurement for accurately and comprehensively investigating global Internet censorship practices. The key idea is to deploy a control server that replies with a static payload to provide the ground truth of server responses, so that the manipulation can be identified without manual efforts. We conduct a comprehensive, large-scale measurement on censorship with fundamental protocols, including DNS, DNS-over-Encryption, HTTP, and HTTPS. Moreover, our proposed framework facilitates extended measurements for investigating more aspects of Internet censorship. We will perform an application traceroute to pinpoint censors' location and explore their policies and deployment. Also, we will leverage the payload conveyed by our control server to examine the keyword-based filtering in both inbound and outbound traffic at a global scale.

Internet censorship has been widely witnessed and its severity varies from country to country. Such information control, typically placed by authority entities such as governments, ISPs, or organizations, can be achieved by various techniques such as IP-layer censorship (e.g., blocking IP addresses) and application-layer censorship (e.g., domain names based blocking in DNS, HTTP, and HTTPS). This proposed research will focus on application-layer censorship, as it typically enables the censors to accurately block their undesired Internet services while avoiding collateral damage caused by prevalent IP sharing in Cloud or CDN platforms. To detect censorship activities in a country, the basic idea is to send a request from a vantage point within the country and then compare the corresponding response with a valid response returned by a legitimate server. The dilemma here is that if the request is censored, the vantage point has no ground truth to automatically validate the legitimate response. To tackle this issue, existing studies typically collect and validate the responses from nodes deployed in multiple countries. However, this approach inevitably reduces the detection reliability due to the diversity and flexibility of Internet services. Clients at diverse locations may obtain different but valid IP addresses for the same domain, and websites may intentionally restrict their services on certain locations or offer different content to the clients from different locations. Thus, manual inspection is usually needed, causing the analysis unscalable and inefficient. More importantly, manual analysis can only identify false positives (i.e., misclassified censorship) but false negatives (i.e., undetected censorship) remain uncountable in state-of-the-art studies.

The detail of the framework and a comprehensive measurement study on global censorship can be found in our ACM SIGMETRICS'22 <a href="/assets/pdf/sigmetrics22.pdf">paper</a>.

---

### framework design

The high-level idea of our proposed research is to provide a **static** payload as ground truth, which can be used to indicate the occurrence of censorship when the static payload has been altered by network devices. Typically, in the presence of censorship, the censor devices would first identify the accessed domains (if being censored), and then intercept and terminate the connections to block the censored domains. In the meantime, the censor devices would return a blockpage to the clients, noticing that the accessed content is unavailable. However, automatically and efficiently identifying the blockages remain challenging due to the variations of blockages and lack of ground truth to detect blockages. With the end-to-end design of our framework, we can provide a static payload on the server-side so that the content injected by the censor (i.e., the blockages) can be straightforwardly detected when the client observed a response that is different from our static payload. In other words, this provides us a baseline by controlling what should be expected at the client-side when no censorship is involved so as to accurately recognize the censorship activities.

The framework of our proposed system design is illustrated in the Figure. The high-level idea is that a client instructs the vantage points to (1) craft DNS/HTTP/HTTPS requests with the test domain names embedded, (2) send the packets to our control server to trigger censorship, and (3) collect the response back for analysis. Our control server replies to arbitrary requests with a static payload for each type of protocol. Note that we do not send any requests to legitimate servers, and the accessed domains in the requests (if being censored) would still trigger the censorship since the censor devices will see the undesired domains but have no knowledge of whether the destination IP address is associated with a legitimate server of the censored domain. In the end, this provides us a baseline by controlling what should be expected at the client side when no censorship is involved so as to accurately recognize the censorship activities.

<img src="/assets/img/disguiser_hz.png" alt="Disguiser Design" style="max-width: 100%"/>


##### Challenges

*Impact of Network middlebox on the censorship measurements*. Our proposed framework leverages a control server to provide a ground truth of server responses. Ideally, it does not generate false positives and false negatives. However, a cache proxy placed by ISPs between a vantage point and our control server may intercept the connections and inject responses from its local cache or retrieve responses from legitimate servers rather than our control server, resulting in false positives. To minimize such an impact, we will design and conduct a cache test to exclude those cache-related vantage points in an injecting-and-probing manner. Specifically, we resolve a separate domain operated by us at our control server, which will serve as an incorrect, static DNS response. Meanwhile, an authentic DNS response of this domain is also hosted at its legitimate nameserver. If a DNS cache proxy presents, it will resolve our domain through the normal resolution path and provide us an authentic DNS response. If not, the request will reach our control server and obtain the static response.


---

### extensive measurements

TO BE UPDATED

---

### other specific research problems

##### Exploring the Censorship of Encrypted DNS
We leverage the framework to explore and evaluate the effectiveness of adopting the emerging encrypted DNS (i.e., DoT and/or DoH) for circumventing censorship. The basic idea is to identify the vantage points (e.g., VPN servers) that suffer manipulation by encrypted DNS, from which perform DNS resolution on the censored domains via DoT/DoH resolvers, and then attempt to visit those domains for assessing the accessibility. We issue the DNS requests from the vantage points via DoT/DoH resolver to our control server that replies arbitrary DNS requests with a static DNS response. If a DNS request triggers an on-path censor, our vantage point will receive a manipulated DNS response that will be different from the static DNS response provided by the control server. In addition, we design and perform a circumvention test with those censored domains to investigate the effectiveness of the use of encrypted DNS. We consider that an encrypted DNS resolver can be used to circumvent censorship if the vantage point can retrieve legitimate web content from the censored domain. The detailed study can be found in our WWW'21 <a href="/assets/pdf/www21.pdf">paper</a>.