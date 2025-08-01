---
layout: page
permalink: /repositories/
title: Repositories
description: 
nav: true
nav_order: 4
---

## Packages

Here you can find a list of my packages and libraries that I have developed or contributed to. You can also find the source code on GitHub.

{% if site.data.repositories.github_repos %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.liquid repository=repo %}
  {% endfor %}
</div>
{% endif %}

## GitHub stats

{% if site.data.repositories.github_users %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.liquid username=user %}
  {% endfor %}
</div>
{% endif %}

{% if site.repo_trophies.enabled and site.data.repositories.github_users %}
  {% for user in site.data.repositories.github_users %}
    {% if site.data.repositories.github_users.size > 1 %}
      <h4>{{ user }}</h4>
    {% endif %}
    <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
      {% include repository/repo_trophies.liquid username=user %}
    </div>
  {% endfor %}
{% endif %}
