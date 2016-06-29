---
layout: cli-reference
title: storm password reset
category: command-reference
blurb: Reset your PubStorm password
navorder: 21
---

### Name

storm password reset - Reset your PubStorm password

### Synopsis

<pre><code>storm password reset</code></pre>

### Options

**\-\-continue**: Specify this flag if you already have a password reset token

### Description

Use `storm password reset` to reset your password if you've forgotten it and are
unable to [login]({% post_url 2016-05-10-storm-login %}).

You will be sent an email with a **password reset token** that can be used to
reset your password.

After entering the **password reset token** and your new password, you'll need
to [login]({% post_url 2016-05-10-storm-login %}).

### See Also

[`storm login`]({% post_url 2016-05-10-storm-login %})
