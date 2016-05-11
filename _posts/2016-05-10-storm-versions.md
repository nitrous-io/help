---
layout: cli-reference
title: storm versions
category: command-reference
blurb: List published versions of the current PubStorm project
navorder: 9
---

### Name

storm versions - List published versions of the current PubStorm project

### Synopsis

<pre><code>storm versions</code></pre>

### Description

`storm versions` displays the successfuly published versions of the current
PubStorm project. Each time you publish your project with
[`storm publish`]({% post_url 2016-05-10-storm-publish %}), a new version of
your project is created.

```bash
$ storm versions
Completed deployments for "blog"
Version    Deployed At          State
v3         7 minutes ago        live
v2         2 days ago
v1         1 week ago
```

The example above shows a project that has been published 3 times, with `v3`
being actually "live".

Each version of your project is a _complete_ reproduction of your project _at
the time that it was published_. This is pretty powerful because it means you
can quickly [rollback]({% post_url 2016-05-10-storm-rollback %}) to a previous
version of the project - pretty nifty if you broke something!

### See Also

[`storm publish`]({% post_url 2016-05-10-storm-publish %}),
[`storm rollback`]({% post_url 2016-05-10-storm-rollback %})
