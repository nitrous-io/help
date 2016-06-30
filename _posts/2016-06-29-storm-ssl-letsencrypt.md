---
layout: cli-reference
title: storm ssl letsencrypt
category: command-reference
blurb: Setup HTTPS on a domain with a free SSL certificate from Let's Encrypt
navorder: 7
---

### Name

storm ssl letsencrypt - Setup HTTPS on a domain with a free SSL certificate from [Let's Encrypt](https://letsencrypt.org/)

### Synopsis

<pre><code>storm ssl letsencrypt [DOMAIN]</code></pre>

### Arguments

**DOMAIN**: Custom domain to secure with HTTPS. _Optional._

### Description

`storm ssl letsencrypt` sets up HTTPS on your custom domain. It takes about 5
seconds and costs nothing (which is _amazing_, if you've ever setup HTTPS the
traditional way before).

The SSL certificate will be obtained from [Let's Encrypt](https://letsencrypt.org/),
an awesome nonprofit [Certificate Authority](https://en.wikipedia.org/wiki/Certificate_authority)
(CA) that provides certificates at zero cost.

The example below is the output from setting up HTTPS on [this very site](https://help.pubstorm.com/)
(which [runs on PubStorm](https://en.wikipedia.org/wiki/Eating_your_own_dog_food)):

```bash
$ storm ssl letsencrypt
Enter Domain Name: help.pubstorm.com
Requesting a certificate from Let's Encrypt for help.pubstorm.com...
[Info] Successfully installed a Let's Encrypt certificate for https://help.pubstorm.com/.
```

### The Nitty Gritty

Some technical details for the so inclined.

* **Certificate Expiry**: You don't have to worry about your certificate expiring
  (Let's Encrypt certificates are short-lived and expire every 3 months).
  PubStorm will automatically renew your certificate when it's about to expire
  (approximately 1 month from its expiry date). This renewal incurs zero downtime.
* **How it works**: PubStorm makes automated requests to Let's Encrypt for a
  certificate on your behalf, in that single `storm ssl letsencrypt` command:
  1. PubStorm creates an account on Let's Encrypt for your custom domain.
  2. A cryptographic transaction between PubStorm and Let's Encrypt then takes
     place to prove that PubStorm controls the domain.
  3. Once Let's Encrypt verifies that PubStorm does actually control the domain,
     PubStorm generates a private key and a Certificate Signing Request (CSR),
     and sends the CSR to Let's Encrypt.
  4. Let's Encrypt responds with a certificate for the domain, which PubStorm
     saves and installs on your PubStorm site.
* **Leaving PubStorm**: Should you decide to move your site off PubStorm in
  future, the beauty of Let's Encrypt is that you can simply request a new
  certificate. It doesn't matter that PubStorm has previously requested a
  certificate. All you need to do is to [prove that you control the domain](https://letsencrypt.org/how-it-works/).

### See Also

[`storm ssl info`]({% post_url 2016-05-10-storm-ssl-info %}),
[`storm ssl force`]({% post_url 2016-06-29-storm-ssl-force %})
