---
layout: cli-reference
title: storm repo unlink
category: command-reference
blurb: Unlink the current project from its GitHub repository
navorder: 26
---

### Name

storm repo unlink - Unlink the current project from its GitHub repository

### Synopsis

<pre><code>storm repo unlink</code></pre>

### Description

`storm repo unlink` will stop pushes to a previously configured GitHub
repository from automatically publishing your project.

```bash
$ storm repo unlink
[Info] Unlinked project "ps-blog" from its GitHub repository.
```

You should also delete the webhook from the Settings page of your GitHub
repository.

### See Also

[`storm repo link`]({% post_url 2016-07-20-storm-repo-link %}),
[`storm repo info`]({% post_url 2016-07-20-storm-repo-info %})
