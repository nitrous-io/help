---
layout: post
title: Starter Templates
category: getting-started
blurb: Try one of our preconfigured websites or blog templates.
navorder: 3
slug: starter-templates
---

This is the starter template article.

TODO: create sample public github repositories under the [https://github.com/pubstorm](https://github.com/pubstorm) org.

<div class="starter-templates">
{% for starter in site.data.starters %}
  <div class="starter-item">
    <div class="avatar vh600">
      <img src="/images/starters/{{ starter.avatar }}" />
    </div>
    <div class="meta">
      <h4>{{ starter.name }}</h4>
      <p class="desc">{{ starter.desc }}</p>
      <div class="actions">
        <a class="btn action" href="{{ starter.github_url }}">Clone</a>
        <a class="btn action" href="{{ starter.demo_url }}">Demo</a>
      </div>
    </div>
  </div>
{% endfor %}
</div>