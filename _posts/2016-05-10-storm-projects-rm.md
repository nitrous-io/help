---
layout: cli-reference
title: storm projects rm
category: command-reference
blurb: Delete a PubStorm project
navorder: 15
---

### Name

storm projects rm - Delete a PubStorm project

### Synopsis

<pre><code>storm projects rm [PROJECT_NAME]</code></pre>

### Arguments

**PROJECT_NAME**: Name of project to remove. Defaults to the current project.
_Optional_.

### Options

**\-\-force, -f**: Use this flag to delete the project without confirmation.

### Description

Use `storm projects rm` to delete a PubStorm project. This will remove its files
from PubStorm's servers, as well as any SSL certificates you have uploaded for
custom domains belonging to this project. Your local files **will not be
deleted**.

<div class="alert warning">
  <strong>Note:</strong> Deleting a project <strong>CANNOT</strong> be undone.
  Your project's files, domains and SSL certificates will be <strong>permanently
  deleted</strong> from PubStorm.
</div>

If ran with no arguments, `storm projects rm` will delete the current project.

```bash
$ cd /path/to/blog
$ storm projects rm
[Warning] This action cannot be undone! This will permanently delete "blog" project. To abort, press Ctrl-C.
Enter "blog" (without quotes) to confirm: blog
[Info] Successfully deleted project "blog".
```

You can specify a specific project to delete as well:

```bash
$ storm projects rm blog
[Warning] This action cannot be undone! This will permanently delete "blog" project. To abort, press Ctrl-C.
Enter "blog" (without quotes) to confirm: blog
[Info] Successfully deleted project "blog".
```

### See Also

[`storm projects`]({% post_url 2016-05-10-storm-projects %}),
[`storm init`]({% post_url 2016-05-10-storm-init %}),
