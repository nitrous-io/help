---
layout: post
title: Publishing and Rollbacks
category: Documentation
blurb: How to update and revert your site to an older version
navorder: 3
---

Publishing your PubStorm project makes the files in your _local_
**Project Path** available on the Web. By making edits to your website locally,
then running `storm publish`, you can make changes to your site rather easily.

### Publishing and versioning

Each time you publish your project with `storm publish`, a new **version** of
your project is created. To see the different versions of your project, run
`storm versions`:

```bash
mycomputer:~$ storm versions
Completed deployments for "my-blog"
Version    Deployed At          State
v3         7 minutes ago        live
v2         2 days ago
v1         1 week ago
```

The example above shows a project that has been published 3 times, with `v3`
being actually "live".

Each version of your project is a _complete_ reproduction of your project _at
the time that it was published_. This is pretty powerful because it means you
can quickly rollback to a previous version of the project - pretty nifty if you
broke something!

### Rollbacks

The rollback feature allows you to quickly revert to a previous version of your
project.

To rollback to the previously published version, run `storm rollback` without
any arguments:

```bash
mycomputer:~$ storm rollback
Launching v2...
[Info] Successfully rolled back "my-blog" to v2.
```

You're not limited to only the previous version - use `storm rollback VERSION`
to rollback to a particular version:

```bash
mycomputer:~$ storm rollback v1
Launching v1...
[Info] Successfully rolled back "my-blog" to v1.
```

If you run `storm versions` now, you'll see that `v1` has become most recent
published version:

```bash
mycomputer:~$ storm versions
Completed deployments for "my-blog"
Version    Deployed At          State
v1         10 seconds ago       live
v3         7 minutes ago
v2         2 days ago
```
