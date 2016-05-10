---
layout: cli-reference
title: storm collab rm
category: command-reference
blurb: Remove a collaborator from the current project
navorder: 11
---

### Name

storm collab rm - Remove a collaborator from the current project

### Synopsis

<pre><code>storm collab rm [COLLAB_EMAIL]</code></pre>

### Arguments

**COLLAB_EMAIL**: Email address of user to remove as collaborator. _Optional._

### Description

Use `storm collab rm` to remove a **collaborator** from the current PubStorm
project.

<div class="alert warning">
  <strong>Note:</strong> Only the owner of a project can remove collaborators.
</div>

```bash
$ storm collab rm
Enter Email of Collaborator to Remove: janitor@acme.io
[Info] Successfully removed "janitor@acme.io" as a collaborator of "blog"
```

### See Also

[`storm collab`]({% post_url 2016-05-10-storm-collab %}),
[`storm collab add`]({% post_url 2016-05-10-storm-collab-add %})
