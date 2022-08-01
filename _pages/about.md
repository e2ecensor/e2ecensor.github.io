---
layout: about
title: about
permalink: /
subtitle: # <a href='#'>Affiliations</a>. Address. Contacts. Moto. Etc.

profile:
  align: right
  image: disguiser.png
  image_cicular: false # crops the image to make it circular
  # address: >
    #<p>555 your office number</p>
    #<p>123 your address street</p>
    #<p>Your City, State 12345</p>

news: true  # includes a list of news items
selected_papers: true # includes a list of papers marked as "selected={true}"
social: true  # includes social icons at the bottom of the page

---

The detection of Internet censorship usually requires heavy manual inspection due to the lack of ground truth, resulting in the difficulty of identifying false positives (i.e., misclassified censorship) and false negatives (i.e., undetected censorship). The difficulty stems from the fact that without ground truth, in many cases it is unlikely to automatically distinguish the legitimate responses and the responses manipulated by censorship. Existing studies tackled such issues by retrieving and comparing distributed responses, but such an approach usually requires manual inspection, causing the analysis unscalable and inefficient.

The project aims to explore, develop, and deploy a framework that enables end-to-end measurement for accurately and automatically investigating global Internet censorship practices. The key idea is to provide a static payload as ground truth, which can be used to indicate the occurrence of censorship when the static payload has been altered by network devices. Moreover, the deployed end-to-end framework can facilitate extended measurements for investigating more aspects of Internet censorship, for example, pinpointing censor devices’ locations and exploring their policies and deployment.