---
layout: cli-reference
title: storm rollback
category: command-reference
blurb: Rollback to a previous or specific version of the current PubStorm project
navorder: 8
---

### Name

storm rollback - Rollback to a previous or specific version of the current PubStorm project

### Synopsis

<pre><code>storm rollback [VERSION]</code></pre>

### Arguments

**VERSION**: Version of project to rollback to. Leave empty to rollback to the
previous version. _Optional._

### Description

`storm rollback` allows you to quickly revert to a previously published version
of your project.

To rollback to the previously published version, run `storm rollback` without
any arguments:

```bash
$ storm rollback
Launching v2...
[Info] Successfully rolled back "blog" to v2.
```

You're not limited to only the previous version - use `storm rollback VERSION`
to rollback to a particular version:

```bash
$ storm rollback v1
Launching v1...
[Info] Successfully rolled back "blog" to v1.
```

If you run `storm versions` now, you'll see that `v1` has become most recent
published version:

```bash
$ storm versions
Completed deployments for "blog"
Version    Deployed At          State
v1         10 seconds ago       live
v3         7 minutes ago
v2         2 days ago
```


### See Also

[`storm publish`]({% post_url 2016-05-10-storm-publish %}),
[`storm versions`]({% post_url 2016-05-10-storm-versions %})
