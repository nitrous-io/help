---
layout: cli-reference
title: storm password change
category: command-reference
blurb: Change your PubStorm password
navorder: 18
---

### Name

storm password change - Change your PubStorm password

### Synopsis

<pre><code>storm password change</code></pre>

### Description

Use `storm password change` to change your PubStorm account's password. You
need to be [logged in]({% post_url 2016-05-10-storm-login %}) to your account
before running this.

You'll be asked for your existing password, and then the new password.

```bash
$ storm password change
[Info] Changing password will log you out from all other active sessions.
Enter Existing Password:
Enter Password:
Confirm Password:
[Info] Your password has been changed.
```

### See Also

[`storm login`]({% post_url 2016-05-10-storm-login %})
