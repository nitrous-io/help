---
layout: post
title: "Change / Reset Password"
category: troubleshooting
blurb: Setup a free custom domain and configure DNS settings.
slug: change-reset-password
navorder: 4
---

### Change Password

You can change your password easily from the PubStorm CLI. Open up a terminal, and navigate into one of your project directories.

Follow the instructions at the prompt.

```bash
mycomputer:~$ storm password change
[Info] Changing password will log you out from all other active sessions.
Enter Existing Password: *******
Enter New Password: **********
```

### Reset Password

You can also reset your password from the PubStorm CLI. In the terminal type:

```bash
mycomputer:~$ storm password reset
Enter Email:
```

You will be sent an email with a token to reset your password.

