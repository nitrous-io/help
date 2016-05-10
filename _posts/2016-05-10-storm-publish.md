---
layout: cli-reference
title: storm publish
category: command-reference
blurb: Publish a PubStorm Project to the Web
navorder: 3
---

### Name

storm publish - Publish a PubStorm project

### Synopsis

<pre><code>storm publish</code></pre>

### Description

`storm publish` uploads files in your **Project Path** (see
[`storm init`]({% post_url 2016-05-10-storm-init %})) securely to PubStorm and
makes your website available over the Internet.

```bash
$ storm publish
Scanning "~/company/blog"...
[Info] Bundling 7 files (528 kB)...

Packing bundle "sophias-blog"...
[========================================] 100.0%

Uploading bundle "sophias-blog" to PubStorm Cloud...
[========================================] 100.0%

Launching v1...
[Info] Successfully published "sophias-blog" on PubStorm Cloud.
=> sophias-blog.pubstorm.site
```

After the `publish` command completes, a new version (see
[`storm versions`](#fixme)) of your website will be "live" on a `.pubstorm.site`
domain. For example, if your **Project Name** is `sophias-blog`, it'll be
available at `http://sophias-blog.pubstorm.site`.

<div class="alert info">
  <strong>Note:</strong> you can use a custom domain, in addition to the default
  subdomain, by running <a href="#fixme"><code>storm domains add</code></a>.
</div>

To publish changes to your website, simply make the required changes locally,
then run `storm publish` again.
