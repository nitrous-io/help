---
layout: post
title: Collaborating on a Project
category: documentation
blurb: Working on a Project with teammates
slug: collaborating-on-a-project
navorder: 7
---

When building websites, you'll often be working with a team. You can work
collaboratively with your team by adding them as **collaborators** to your PubStorm
project.

### Adding a Collaborator

Use `storm collab add` to add another PubStorm user as a collaborator to your
project:

```bash
mycomputer:~/microsite$ storm collab add
Enter Email of Collaborator to Add: kale-lover@acme.com
[Info] Successfully added "kale-lover@acme.com" as a collaborator of "microsite"
```

Collaborators are allowed to do everything the project owner can (e.g. publish
the project, rollback, add custom domains) _except_ deleting the project and
adding other collaborators.

<div class="alert warning">
  <strong>Note:</strong> Only the owner of a project can add collaborators.
</div>

<div class="alert warning">
  <strong>Note:</strong> The collaborator must be an existing PubStorm user. Ask
  them to signup using <code>storm signup</code> if they aren't a PubStorm user.
</div>

### Viewing the Collaborators of your Project

Use `storm collab` to find out who the collaborators of your PubStorm project
are:

```bash
mycomputer:~/microsite$ storm collab
Collaborators of "microsite"
- kale-lover@acme.com
```

### Removing a Collaborator from your Project

Use `storm collab rm` to remove a collaborator from your PubStorm project:

```bash
mycomputer:~/microsite$ storm collab rm
Enter Email of Collaborator to Remove: kale-lover@acme.com
[Info] Successfully removed "kale-lover@acme.com" as a collaborator of "microsite"
```

Once a collaborator has been removed, they will no longer have access to your
project.
