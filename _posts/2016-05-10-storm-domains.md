---
layout: cli-reference
title: storm domains
category: command-reference
blurb: List all domains for the current PubStorm project
navorder: 4
---

### Name

storm domains - List all domains for the current PubStorm project

### Synopsis

<pre><code>storm domains</code></pre>

### Description

`storm domains` displays the domains that the current PubStorm project supports.
This includes the default `.pubstorm.site` subdomain provided to you for free,
as well as any custom domains you might have added (using
[`storm domains add`]({% post_url 2016-05-10-storm-domains-add %})).

``` bash
$ storm domains
List of Domains for "blog"
- blog.pubstorm.site
- yourdomain.com
```

#### Default domain

The **default domain** provided to you is `<project-name>.pubstorm.site`. For
example, if your **Project Name** is `blog`, its default domain is
`blog.pubstorm.site`.

The default domain is automatically enabled for your project and allows you to
easily show your work to other people. If you want to, you can disable the
default domain using
[`storm domains rm default`]({% post_url 2016-05-10-storm-domains-rm %}).

#### Custom domains

You can use your own custom domain instead of `.pubstorm.site` - use
[`storm domains add`]({% post_url 2016-05-10-storm-domains-add %}) to add any
number of custom domains to your project.

### See Also

[`storm domains add`]({% post_url 2016-05-10-storm-domains-add %}),
[`storm domains rm`]({% post_url 2016-05-10-storm-domains-rm %})
