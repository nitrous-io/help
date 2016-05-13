---
layout: cli-reference
title: storm ssl info
category: command-reference
blurb: Show certificate information for a domain of the current PubStorm project
navorder: 8
---

### Name

storm ssl info - Show certificate information for a domain of the current
PubStorm project

### Synopsis

<pre><code>storm ssl info [DOMAIN]</code></pre>

### Arguments

**DOMAIN**: Domain to show certificate info of. _Optional._

### Description

Use `storm ssl info` to display the details of the certificate of a custom
domain of the current PubStorm project.

```bash
$ storm ssl info
Enter Domain Name: help.pubstorm.com
Certificate details for domain "help.pubstorm.com":
Common Name: help.pubstorm.com
Issuer: /C=US/O=Let's Encrypt/CN=Let's Encrypt Authority X3
Subject: /CN=help.pubstorm.com
Starts At: 2016-05-09 04:20:00 +0000 UTC
Expires At: 2016-08-07 04:20:00 +0000 UTC
```

If the domain does not have a certificate registered with PubStorm, you can
upload one using [`storm ssl set`]({% post_url 2016-05-10-storm-ssl-set %}).

```bash
$ storm ssl info
Enter Domain Name: help.pubstorm.com
[Info] No certificate for "help.pubstorm.com"
```

### See Also

[`storm ssl set`]({% post_url 2016-05-10-storm-ssl-set %}),
[`storm domains`]({% post_url 2016-05-10-storm-domains %})
