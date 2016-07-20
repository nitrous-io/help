---
layout: cli-reference
title: storm repo link
category: command-reference
blurb: Link the current project to a GitHub repository
navorder: 25
---

### Name

storm repo link - Link the current project to a GitHub repository so that pushes to the repository will publish your project

### Synopsis

<pre><code>storm repo link</code></pre>

### Description

If you use [GitHub](https://github.com/) for your project, you can configure
PubStorm to automatically [publish]({% post_url 2016-05-10-storm-publish %})
your project whenever you push to GitHub.

This uses [GitHub's webhook](https://help.github.com/articles/about-webhooks/)
feature to notify PubStorm when you push to your GitHub repository, and will
require you to add a webhook on GitHub. The command will walk you through the
setup steps:

```bash
$ storm repo link
Enter GitHub repository URL: https://github.com/example/project.git
Enter branch [master]: release
[Info] Successfully linked project to "https://github.com/example/project.git@release"
Setup Instructions:
1. In your GitHub account, go to the https://github.com/example/project.git repository. Click on the Settings tab.
2. Click on Webhooks & services in the left navigation, then click the Add webhook button.
3. Enter https://api.pubstorm.com/hooks/github/2367268dab1908420 as the Payload URL. Ensure that the Content type is application/json.
4. Enter QcmtaNakxaoHd72lAjf= in the Secret field. This will ensure that only GitHub can trigger the publishing of your project.
5. Choose Just the push event (only push events are currently supported). Click the Add webhook button when done
```

You can specify the git branch that you want PubStorm to deploy. We'll use the
`master` branch by default.

Should you need to setup the webhook again, you can run [`storm repo info`]({% post_url 2016-07-20-storm-repo-info %})
to display the setup instructions again.

### See Also

[`storm repo unlink`]({% post_url 2016-07-20-storm-repo-unlink %}),
[`storm repo info`]({% post_url 2016-07-20-storm-repo-info %})
