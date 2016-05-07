---
layout: post
title: "SSL for Custom Domains"
category: documentation
blurb: Add SSL certs and enable HTTPS for custom domains.
slug: ssl-for-custom-domains
navorder: 6
---

TLS, which is more commonly and somewhat not entirely accurately
referred to as SSL, is a cryptographic protocol that lets you secure
communications between your customers and your site by providing an
end-to-end encryption of the data transmitted. For the rest of the
article we will refer to the protocol as SSL (which is actually a
predecessor of TLS) since that is how it is almost universally called.

Sites that are served with SSL encryption use the HTTPS (HTTP Secure)
protocol and their URLs begin with `https://` instead of `http://`.

### SSL for pubstorm.site domains

All sites that are served at the default `.pubstorm.site` URLs have
HTTPS enabled by default. Simply visit the URLs with the `https://`
instead of the `http://` protocol.

By default both `http://` and `https://` URLs are enabled. In order to
enable HTTPS-only mode and redirect users hitting the `http://` to the
more secure `https://` URL, run the following command:

```
storm ssl force true
```

To disable HTTPS-only mode, you can run `storm ssl force false`.

### SSL for custom domains

In order to enable SSL for custom domains, you need to acquire an SSL
certificate. Browsers require certificates issued by certificate
authorities (CAs). This is to ensure that the certificate is genuine and
not forged by a malicious party. This post will guide you through
obtaining an SSL certificate and uploading the certificate to PubStorm
to enable SSL for your custom domains.

1. Install OpenSSL
2. Generate a Certificate Signing Request (CSR)

#### Install OpenSSL

To have the CA issue you a certificate, you need to create a Certificate
Signing Request (CSR). In order to create one, you need to use OpenSSL
command line tool.

Open your command line (command prompt, terminal, bash etc.) and enter
the following command to check if you have OpenSSL.

```
openssl version
```

If it shows an OpenSSL version information, such as `OpenSSL 1.0.2`, you
are good to go.

If you are using OS X on a Mac, OpenSSL should already be installed.

On Windows, install latest
[Git for Windows](https://git-scm.com/download/win), which includes
OpenSSL and other useful command line tools. After installing Git for
Windows, run Git Bash to open a command line that gives you access to
OpenSSL.

Different flavors of Linux have different ways of installing OpenSSL,
but on Ubuntu, run the following command.

```
sudo apt-get install openssl
```

Once OpenSSL is installed, you can proceed to the next step.

#### Generate a Certificate Signing Request (CSR)


