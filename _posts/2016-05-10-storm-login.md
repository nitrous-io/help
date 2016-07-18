---
layout: cli-reference
title: storm login
category: command-reference
blurb: Log in to a PubStorm account
navorder: 18
---

<div class="alert alert-warning" id="login-enquiry">
  <span class="glyphicon glyphicon-info-sign" aria-hidden="true"></span>
  PubStorm is a <strong>Command Line Interface</strong>. We do not provide a web-based login or dashboard.
  To login, install the <a href="/getting-started/getting-started/" target="_blank">PubStorm CLI</a> and follow the instructions below.
</div>

### Name

storm login - Log in to a PubStorm account

### Synopsis

<pre><code>storm login</code></pre>

### Description

Use `storm login` to login using your [PubStorm](http://www.pubstorm.com/)
account.

<div class="alert warning">
  <strong>Note:</strong> If you don't have a PubStorm account yet, run
  <a href="{% post_url 2016-05-10-storm-signup %}"><code>storm signup</code></a>
  to sign up for one.
</div>

`storm` will remember your login details, so you won't have to re-enter your
password until you've logged out (with
[`storm logout`]({% post_url 2016-05-10-storm-logout %})).

Use [`storm password reset`]({% post_url 2016-05-10-storm-password-reset %}) if
you've forgotten your PubStorm account password.

### See Also

[`storm password reset`]({% post_url 2016-05-10-storm-password-reset %})
