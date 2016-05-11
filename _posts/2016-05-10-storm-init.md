---
layout: cli-reference
title: storm init
category: command-reference
blurb: Initializing a PubStorm Project
navorder: 1
---

### Name

storm init - Initialize a PubStorm project

### Synopsis

<pre><code>storm init</code></pre>

### Description

`storm init` sets up the _current working directory_ as a PubStorm project. You
will be asked for your **Project Path** and **Project Name**.

#### Project Path

The **Project Path** is the local path to a directory containing your website's
files (HTML, CSS & Javascript files) - all files in this directory will be
uploaded and published on the Web. `storm init` will create this directory if it
doesn't exist.

The default **Project Path** is `.` (the directory where `storm init` is run).
This is a good choice if you intend to publish everything in the current
directory.

If you are using a static site generator like [Jekyll](https://jekyllrb.com/),
[Middleman](https://middlemanapp.com/) or [Hugo](https://gohugo.io/), you will
want to specify a **Project Path** pointing to the location of the generated
files. See the [Common Project Paths section](#common-project-paths) for
examples.

<div class="alert warning">
  <strong>Note:</strong> Do not store any sensitive information like
  passwords or secret tokens inside your <strong>Project Path</strong>!
</div>

#### Project Name

Pick a memorable name for your project. This will also be used as the subdomain
for your project, so only alphanumeric characters and hyphens are allowed.

Note that project names are globally available to all users of PubStorm, so you
will need to think of something unique if the name you wanted has been taken
(yes, you might have to resort to unglamorous names like `sophias-blog-42`).

### Common Project Paths

##### Regular HTML website

If you're developing a "regular" HTML website, you should use the root directory
where your HTML files are stored as the **Project Path**.

For example, a typical HTML website contains files similar to this:

```bash
$ cd ~/company/blog
$ tree .
.
├── about.html
├── css
│   └── style.css
├── images
│   ├── logo.png
│   └── people-creating-synergies.jpg
├── index.html
└── js
    ├── jquery.js
    └── scripts.js
```

In this case, the **Project Path** will be the `.` (i.e. current directory)
since all the files for the website are contained at the root of the project
directory.

```bash
$ cd ~/company/blog
$ storm init
Set up your PubStorm project
Enter Project Path (path to be deployed): [.] .
```

##### Jekyll

[Jekyll](https://jekyllrb.com/) is a static site generator that works really
well with PubStorm. By default, Jekyll generates your site's files to the
`_site` directory ([by default](https://jekyllrb.com/docs/structure/)).

Use `./_site` as the **Project Path** if you're using Jekyll.

##### Middleman

[Middleman](https://middlemanapp.com/) is yet another static site generator that
works really well with PubStorm. Middleman generates and places your site's
files in the `build/` directory.

Use `./build` as the **Project Path** if you're using Middleman.

##### Hugo

[Hugo](https://gohugo.io/) is, again, yet another static site generator. Hugo
generates and places your site's files in the `public/` directory by default.

Use `./public` as the **Project Path** if you're using Hugo.


### Examples

##### Initialize a Pubstorm project for an existing site

```bash
$ cd /path/to/my/site   # (1)
$ storm init            # (2)
Set up your PubStorm project
Enter Project Path (path to be deployed): [.] .
Enter Project Name: blog
[Info] Successfully created project "blog".
[Info] Saved project settings to "pubstorm.json". This file should not be deleted.
$ storm publish         # (3)
```

1. Navigate to the root of your site's code.
2. Initialize a PubStorm project in `/path/to/my/site`.
3. Publish project to the Web. See [`storm publish`]({% post_url 2016-05-10-storm-publish %}) for more info on publishing your site.
