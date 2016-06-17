---
layout: cli-reference
title: storm reinit
category: command-reference
blurb: Re-initializing a PubStorm Project
navorder: 20
---

### Name

storm reinit - Re-initialize a PubStorm project

### Synopsis

<pre><code>storm reinit [PROJECT_NAME]</code></pre>

### Description

`storm reinit` re-initialize a PubStorm project using _current working
directory_. You will be asked for your **Project Path** and **Project Name**.
If you accidentally deleted your `pubstorm.json`, you should use this command
to generate it again.

#### Project Path

The **Project Path** is the local path to a directory containing your website's
files (HTML, CSS & Javascript files) - all files in this directory will be
uploaded and published on the Web. `storm init` will create this directory if it
doesn't exist.

The default **Project Path** is `.` (the directory where `storm init` is run).
This is a good choice if you intend to publish everything in the current
directory.

<div class="alert warning">
  <strong>Note:</strong> Do not store any sensitive information like
  passwords or secret tokens inside your <strong>Project Path</strong>!
</div>

#### Project Name

Project name must be one of your existing project name.

### Examples

##### Re-initialize a Pubstorm project for an existing project

```bash
$ cd /path/to/my/site
$ storm reinit
Enter Project Path (path to be deployed): [.] .
Enter Project Name: blog
[Info] Successfully re-initialized project "blog".
[Info] Saved project settings to "pubstorm.json". This file should not be deleted.
```
