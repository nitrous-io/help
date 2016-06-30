---
layout: cli-reference
title: storm ssl force
category: command-reference
blurb: Enable/disable redirecting all HTTP traffic to HTTPS for a project
navorder: 8
---

### Name

storm ssl force - Enable/disable redirecting all HTTP traffic to HTTPS for a project

### Synopsis

<pre><code>storm ssl force [VALUE]</code></pre>

### Arguments

**VALUE**: Use `on` to enable, `off` to disable. Defaults to `on`. _Optional._

### Description

After setting up HTTPS on your custom domain (with either
[`storm ssl letsencrypt`]({% post_url 2016-06-29-storm-ssl-letsencrypt %}) or
[`storm ssl set`]({% post_url 2016-05-10-storm-ssl-set %})), you might want to
enforce only HTTPS traffic to your site. This will ensure that all traffic to it
is secure.

Use `storm ssl force` to redirect any non-HTTPS requests to the corresponding
HTTPS URI. For example, requests to `http://www.example.com/` will be redirected
to `https://www.example.com/`.

```bash
$ storm ssl force on
[Info] Forced SSL/HTTPS has been enabled.

$ storm ssl force off
[Info] Forced SSL/HTTPS has been disabled.
```

### See Also

[`storm ssl letsencrypt`]({% post_url 2016-06-29-storm-ssl-letsencrypt %}),
[`storm ssl set`]({% post_url 2016-05-10-storm-ssl-set %})
