---
layout: page
permalink: /data/
title: data
description: experiment data and code repositories.
nav: true
nav_order: 4
---

Disguiser Code & Data 2021 (used in SIGMETRICS'22 paper): <a href="https://drive.google.com/drive/u/1/folders/106F_7gkKO-zRqpdyOokGT_Gr-wonRfnk" target="_blank">Anonymized Data</a>

Pathfinder Code & Data 2022: <a href="https://drive.google.com/drive/folders/1vZ7JuQsWQYIKkT8hxX-_qRldjnSuykQy?usp=share_link" target="_blank">Anonymized Data</a>

Descriptions: TO BE ADDED

---

### GitHub users

{% if site.data.repositories.github_users %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.html username=user %}
  {% endfor %}
</div>
{% endif %}

---

### GitHub repositories

{% if site.data.repositories.github_repos %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.html repository=repo %}
  {% endfor %}
</div>
{% endif %}
