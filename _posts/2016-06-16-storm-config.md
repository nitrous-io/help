---
layout: cli-reference
title: storm config
category: command-reference
blurb: Configure a PubStorm Project
navorder: 21
---

### Name

storm config - Configure a PubStorm project

### Synopsis

<pre><code>storm config</code></pre>

### Description

`storm config` configure a PubStorm project in _current working
directory_.

#### Deploy optimized project?

Your project will be optimized by enabling this option.

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
[Info] Project will be optmized from next deployment.
Successfully updated <project-name> project's configuration.
```
