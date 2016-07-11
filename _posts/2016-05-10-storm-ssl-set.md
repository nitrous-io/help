---
layout: cli-reference
title: storm ssl set
category: command-reference
blurb: Upload an SSL certificate and a private key for a PubStorm project
navorder: 9
---

### Name

storm ssl set - Upload an SSL certificate and a private key for a PubStorm
project

### Synopsis

<pre><code>storm ssl set [DOMAIN] [CERT_FILE] [KEY_FILE]</code></pre>

### Arguments

**DOMAIN**: Domain that certificate is for. Specify `default` to disable the
default `.pubstorm.site` domain. _Optional._<br>
**CERT_FILE**: Path to SSL certificate file. _Optional._<br>
**KEY_FILE**: Path to private key for SSL certificate. _Optional._

### Description

Use `storm ssl set` to register an SSL certificate for a custom domain. This
will allow you to secure traffic to your website when it is accessed via your
custom domain.

To do this, you will first need an SSL certificate and its private key for your
custom domain. If you don't already have an SSL certificate, you can setup one
for free using [`storm ssl letsencrypt`]({% post_url 2016-06-29-storm-ssl-letsencrypt %}).

Place the certificate and its private key in a local path so that the `storm`
command can access them.

```bash
$ storm ssl set
Enter Domain Name: yourdomain.com
Enter Path To Certificate: /path/to/yourdomain.com/cert.pem
Enter Path To Private Key: /path/to/yourdomain.com/privkey.pem
[Info] Successfully set an SSL certificate for https://www.yourdomain.com/

Certificate details for domain "www.yourdomain.com":
Common Name: www.yourdomain.com
Issuer: /C=US/O=Let's Encrypt/CN=Let's Encrypt Authority X3
Subject: /CN=www.yourdomain.com
Starts At: 2016-05-09 04:20:00 +0000 UTC
Expires At: 2016-08-07 04:20:00 +0000 UTC
```

You will then be able to access your website over
[HTTPS](https://en.wikipedia.org/wiki/HTTPS) in a web browser,
e.g. _https://www.yourdomain.com/_.

<figure>
  <img src="/images/cli/storm-cert-set-https-browser.png" alt="Verify that HTTPS is now working in a web browser" />
</figure>
<br />

Note that if you enter "_foobar.com_" in the address bar, it will redirect to "_https://www.foobar.com_" as expected. If however, someone were to type "_https://foobar.com_" without the "www", the page will return 404.

If you need an ssl cert on your root domain, you'll need to set up your own certs using cloudflare or equivalent to setup ssl for your apex (root) domain.

### See Also

[`storm ssl letsencrypt`]({% post_url 2016-06-29-storm-ssl-letsencrypt %}),
[`storm ssl force`]({% post_url 2016-06-29-storm-ssl-force %}),
[`storm ssl info`]({% post_url 2016-05-10-storm-ssl-info %}),
[`storm domains`]({% post_url 2016-05-10-storm-domains %})
