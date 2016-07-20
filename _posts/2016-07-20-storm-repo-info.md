---
layout: cli-reference
title: storm repo info
category: command-reference
blurb: Displays the linked GitHub repository information and setup instructions
navorder: 27
---

### Name

storm repo info - Displays the linked GitHub repository information and setup instructions

### Synopsis

<pre><code>storm repo info</code></pre>

### Description

`storm repo info` displays the setup instructions to configure a webhook on
GitHub so that your project will be published by PubStorm whenever you push to
your repository.

This only works for public GitHub repositories and requires that you check in the
`pubstorm.json` file to your repository.

```bash
$ storm repo info
[Info] Project "ps-blog" is linked to "https://github.com/PubStorm/help.git@release"
Setup Instructions:
1. In your GitHub account, go to the https://github.com/PubStorm/help.git repository. Click on the Settings tab.
2. Click on Webhooks & services in the left navigation, then click the Add webhook button.
3. Enter https://api.pubstorm.com/hooks/github/2367268dab1908420 as the Payload URL. Ensure that the Content type is application/json.
4. Enter QcmtaNakxaoHd72lAjf= in the Secret field. This will ensure that only GitHub can trigger the publishing of your project.
5. Choose Just the push event (only push events are currently supported). Click the Add webhook button when done.
```


### See Also

[`storm repo link`]({% post_url 2016-07-20-storm-repo-link %}),
[`storm repo unlink`]({% post_url 2016-07-20-storm-repo-unlink %})
