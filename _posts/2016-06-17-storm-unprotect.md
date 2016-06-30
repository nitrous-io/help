---
layout: cli-reference
title: storm unprotect
category: command-reference
blurb: Disable protection for your PubStorm project
navorder: 24
---

### Name

storm unprotect - Disable HTTP basic authentication for your PubStorm project

### Synopsis

<pre><code>storm unprotect</code></pre>

### Description

Use `storm unprotect` to remove HTTP basic authentication that was previously
setup using [`storm protect`]({% post_url 2016-06-17-storm-protect %}).

### Examples

##### Remove HTTP basic authentication from project

```bash
$ cd /path/to/my/site
$ storm unprotect
[Info] Successfully disabled protection for project "<project-name>".
```

### See Also

[`storm protect`]({% post_url 2016-06-17-storm-protect %})
