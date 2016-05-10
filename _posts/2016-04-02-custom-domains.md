---
layout: post
title: Custom Domains
category: getting-started
blurb: Setup a free custom domain and configure DNS settings.
navorder: 2
---

[PubStorm](https://www.pubstorm.com) allows you to use a custom domain for your projects instead of our subdomain `my-website.pubstorm.site` for free. This article assumes you've already [setup a project](/getting-started/getting_started).

### Add a domain

Open up a terminal, and change directories into the folder for the project where you ran `storm init`. Then type `storm domains add <domain>`

```bash
mycomputer:~$ storm domains add mydomain.com
[Info] Successfully added "www.mydomain.com" to project "my-website".
[Info] Please add the following records to the DNS configuration for the domain "mydomain.com":-
  * CNAME (Alias): www ---> my-website.pubstorm.site
  * A (Host): @ ---> 52.38.113.95
[Info] For more information on DNS configuration, please visit https://help.pubstorm.com/custom-domains
```

### Configure DNS records

As stated in the terminal output above, you will need to add the following records to your DNS configuration:

  * CNAME (Alias): www ---> my-website.pubstorm.site
  * A (Host): @ ---> 52.38.113.95

There are a variety of DNS registrars out there, and the instructions vary by provider. Please find yours in the list below:

<div class="list with-actions">
{% for registrar in site.data.registrars %}
  <div class="fb-li">
    <div class="label">
      <h4>{{ registrar.name }}</h4>
    </div>
    <div class="la">
      <a class="btn action" href="{{ registrar.cname_url }}">Edit CNAME</a>
      <a class="btn action" href="{{ registrar.arec_url }}">Edit A Record</a>
    </div>
  </div>
{% endfor %}
</div>
