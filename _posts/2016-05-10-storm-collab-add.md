---
layout: cli-reference
title: storm collab add
category: command-reference
blurb: Add a collaborator to the current project
navorder: 14
---

### Name

storm collab add - Add a collaborator to the current project

### Synopsis

<pre><code>storm collab add [COLLAB_EMAIL]</code></pre>

### Arguments

**COLLAB_EMAIL**: Email address of user to add as collaborator. _Optional._

### Description

Use `storm collab add` to add another PubStorm user as a **collaborator** of the
current PubStorm project.

<div class="alert warning">
  <strong>Note:</strong> Only the owner of a project can add collaborators.
</div>

<div class="alert warning">
  <strong>Note:</strong> The collaborator must be an existing PubStorm user. Ask
  them to signup using <code>storm signup</code> if they aren't a PubStorm user.
</div>

```bash
$ storm collab add
Enter Email of Collaborator to Add: ceo@acme.io
[Info] Successfully added "ceo@acme.io" as a collaborator of "blog"
```

Collaborators are allowed to do everything the project owner can (e.g. publish
the project, rollback, add custom domains) _except_ deleting the project and
adding/removing other collaborators.

You can remove a collaborator from your project with
[`storm collab rm`]({% post_url 2016-05-10-storm-collab-rm %}).

### See Also

[`storm collab`]({% post_url 2016-05-10-storm-collab %}),
[`storm collab rm`]({% post_url 2016-05-10-storm-collab-rm %})
