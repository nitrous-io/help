---
layout: cli-reference
title: storm domains add
category: command-reference
blurb: Add a custom domain to the current PubStorm Project
navorder: 5
---

### Name

storm domains add - Add a custom domain to the current PubStorm Project

### Synopsis

<pre><code>storm domains add [DOMAIN]</code></pre>

### Arguments

**DOMAIN**: Custom domain to add. Specify `default` to enable the
default `.pubstorm.site` domain. _Optional._

### Description

Use `storm domains add` to add a custom domain to the current PubStorm project.
You can optionally specify the domain to add by passing it as an additonal
argument, e.g. `storm domains add example.com`. Otherwise, it'll be asked for
interactively.

```bash
$ storm domains add
Enter Domain Name to Add: example.com
[Info] Successfully added "www.example.com" to project "blog".

[Info] Please add the following records to the DNS configuration for the domain "example.com":-

  * CNAME (Alias): www ---> blog.pubstorm.site
  * A (Host): @ ---> 52.38.113.95

[Info] For more information on DNS configuration, please visit https://help.pubstorm.com/custom-domains
```

The string `default` is special - it indicates the
[**default domain**](#default-domain) provided to a project. Use `storm domains
add default` to enable the default domain (if it was previously disabled).

#### Default domain

The **default domain** provided to you is `<project-name>.pubstorm.site`. For
example, if your **Project Name** is `blog`, its default domain is
`blog.pubstorm.site`.

The default domain is automatically enabled for your project and allows you to
easily show your work to other people. If you want to, you can disable the
default domain using
[`storm domains rm default`]({% post_url 2016-05-10-storm-domains-rm %}).

### See Also

[`storm domains rm`]({% post_url 2016-05-10-storm-domains-rm %}),
[`storm domains`]({% post_url 2016-05-10-storm-domains %})
