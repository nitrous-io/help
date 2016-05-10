---
layout: cli-reference
title: storm collab
category: command-reference
blurb: List collaborators of the current project
navorder: 9
---

### Name

storm collab - List collaborators of the current project

### Synopsis

<pre><code>storm collab</code></pre>

### Description

Use `storm collab` to view the **collaborators** of the current PubStorm
project.

```
$ storm collab
Collaborators of "blog"
- kalelover@acme.io
- crossfitcrazy@acme.io
```

Collaborators are allowed to do everything the project owner can (e.g. publish
the project, rollback, add custom domains) _except_ deleting the project and
adding/removing other collaborators.

Add/remove collaborators to your project with
[`storm collab add`]({% post_url 2016-05-10-storm-collab-add %}) /
[`storm collab rm`]({% post_url 2016-05-10-storm-collab-rm %}).

### See Also

[`storm collab add`]({% post_url 2016-05-10-storm-collab-add %}),
[`storm collab rm`]({% post_url 2016-05-10-storm-collab-rm %})
