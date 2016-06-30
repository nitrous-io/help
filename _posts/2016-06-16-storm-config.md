---
layout: cli-reference
title: storm config
category: command-reference
blurb: Configure a PubStorm Project
navorder: 22
---

### Name

storm config - Configure a PubStorm project

### Synopsis

<pre><code>storm config</code></pre>

### Description

`storm config` configures the current PubStorm project.

Right now, there's only a single setting that you can change: whether to
optimize your project when deploying.

If you choose to optimize your project when deploying, these additional steps
will be performed:

1. JavaScript files will be minified.
2. CSS files will be minified.
3. HTML files(.html, .htm) will be minified.
4. Images(PNG, JPEG, JPG, GIF and SVG) will be optimized.
5. sitemap.xml will be generated and will be accessible at
`<project-name>.pubstorm.site/sitemap.xml`

### Examples

##### Configure a PubStorm project

```bash
$ cd /path/to/my/site
$ storm config
Configure your project: <project-name>
Deploy optimized project? [Y/n]: Y
[Info] Project will be optimized from the next deployment onwards.
Successfully updated <project-name> project configuration.
```
