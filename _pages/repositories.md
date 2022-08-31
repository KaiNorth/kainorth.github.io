---
layout: page
permalink: /Repositories/
title: Repositories
description: Edit the `_data/Repositories.yml` and change the `github_users` and `github_repos` lists to include your own GitHub profile and Repositories.
nav: true
nav_order: 3
---

## GitHub users

{% if site.data.Repositories.github_users %}
<div class="Repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.Repositories.github_users %}
    {% include repository/repo_user.html username=user %}
  {% endfor %}
</div>
{% endif %}

---

## GitHub Repositories

{% if site.data.Repositories.github_repos %}
<div class="Repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.Repositories.github_repos %}
    {% include repository/repo.html repository=repo %}
  {% endfor %}
</div>
{% endif %}
