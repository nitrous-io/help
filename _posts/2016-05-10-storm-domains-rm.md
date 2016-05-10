---
layout: cli-reference
title: storm domains rm
category: command-reference
blurb: Remove a custom domain from the current PubStorm Project
navorder: 6
---

### Name

storm domains rm - Remove a custom domain from the current PubStorm Project

### Synopsis

<pre><code>storm domains rm [DOMAIN]</code></pre>

### Arguments

**DOMAIN**: Custom domain to remove. Specify `default` to disable the
default `.pubstorm.site` domain. _Optional._

### Description

Use `storm domains rm` to remove a custom domain from the current PubStorm
project. You can optionally specify the domain to remove by passing it as an
additonal argument, e.g. `storm domains rm example.com`. Otherwise, it'll be
asked for interactively.

```bash
$ storm domains rm
Enter Domain Name to Remove: example.com
[Info] Successfully removed "www.example.com" from project "blog".
```

The string `default` is special - it indicates the
[**default domain**](#default-domain) provided to a project. Use `storm domains
rm default` to disable the default domain.

#### Default domain

The **default domain** provided to you is `<project-name>.pubstorm.site`. For
example, if your **Project Name** is `blog`, its default domain is
`blog.pubstorm.site`.

The default domain is automatically enabled for your project and allows you to
easily show your work to other people. If you want to, you can disable the
default domain using `storm domains rm default`.

### See Also

[`storm domains add`]({% post_url 2016-05-10-storm-domains-add %}),
[`storm domains`]({% post_url 2016-05-10-storm-domains %})
