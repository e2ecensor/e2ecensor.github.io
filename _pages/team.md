---
layout: page
title: Team
permalink: /team/
description: Faulty and student researchers working on this project
nav: false
display_categories: [faculty, student]
horizontal: false
---

<div class="teams">
	<h2 class="category font-weight-normal">faculty</h2>
    <div class="grid">
		<div class="grid-sizer"></div>
		<div class="grid-item">
			<a href="https://shhaos.github.io/">
			<div class="card hoverable">
				<div class="row no-gutters">
					<div class="col-3">
				        {% include figure.html path="assets/img/profile_hao.jpg" class="img-fluid z-depth-1" %}
					</div>
					<div class="col-9">
						<div class="card-body card-margin">
						<h6 class="card-title">Shuai Hao</h6>
						<p class="card-text">Assistant Professor<br>Dept. of Computer Science<br>Old Dominion University<br>Norfolk, VA</p>
						</div>
					</div>
				</div>
			</div>
			</a>
		</div>
		<div class="grid-item">
			<a href="https://scholar.google.com/citations?user=tmOInzMAAAAJ&hl=en">
			<div class="card hoverable">
				<div class="row no-gutters">
					<div class="col-3">
						{% include figure.html path="assets/img/hnw.jpeg" class="img-fluid z-depth-1" %}
					</div>
					<div class="col-9">
						<div class="card-body card-margin">
						<h6 class="card-title">Haining Wang</h6>
						<p class="card-text">Professor<br>Electrical & Computer Engineering<br>Virginia Tech<br>Arlington, VA</p>
					</div>
					</div>
				</div>
				</div>
			</a>
		</div>
		<div class="grid-item">
			<a href="https://www.ece.udel.edu/people/faculty/ccotton/">
			<div class="card hoverable">
				<div class="row no-gutters">
					<div class="col-3">
				        {% include figure.html path="assets/img/ccotton.png" class="img-fluid z-depth-1" %}
					</div>
					<div class="col-9">
					<div class="card-body card-margin">
						<h6 class="card-title">Chase Cotton</h6>
						<p class="card-text">Professor<br>Electrical & Computer Engineering<br>University of Delaware<br>Newark, DE</p>
					</div>
					</div>
				</div>
				</div>
			</a>
		</div>
	</div>
	
	<h2 class="category font-weight-normal">student</h2>
    <div class="grid">
		<div class="grid-sizer"></div>
		<div class="grid-item">
			<a href="">
			<div class="card hoverable">
				<div class="row no-gutters">
					<div class="col-3">
				        {% include figure.html path="assets/img/user.png" class="img-fluid z-depth-1" %}
					</div>
					<div class="col-9">
						<div class="card-body card-margin">
						</div>
					</div>
				</div>
			</div>
			</a>
		</div>
		<div class="grid-item">
			<a href="">
			<div class="card hoverable">
				<div class="row no-gutters">
					<div class="col-3">
				        {% include figure.html path="assets/img/user.png" class="img-fluid z-depth-1" %}
					</div>
					<div class="col-9">
						<div class="card-body card-margin">
					</div>
					</div>
				</div>
				</div>
			</a>
		</div>
		<div class="grid-item">
			<a href="">
			<div class="card hoverable">
				<div class="row no-gutters">
					<div class="col-3">
				        {% include figure.html path="assets/img/user.png" class="img-fluid z-depth-1" %}
					</div>
					<div class="col-9">
					<div class="card-body card-margin">
					</div>
					</div>
				</div>
				</div>
			</a>
		</div>
	</div>
	
	<h2 class="category font-weight-normal">contact</h2>
    <div class="social">
      <div class="contact-icons">
		  <a href="mailto:{{ site.email | encode_email }}" title="email"><i class="fas fa-envelope"></i></a>
      </div>     
    </div>
<!-- pages/team.md -->
<!--div class="projects">
{%- if site.enable_project_categories and page.display_categories %}

  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}

  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}

  {%- assign sorted_projects = site.projects | sort: "importance" -%}

  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
-->