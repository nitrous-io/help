---
layout: post
title: JavaScript Environment Variables
category: documentation
blurb: Configure your project's environment
slug: javascript-environment-variables
navorder: 7
---

If you're building a website that uses JavaScript, you can configure your
JavaScript application using PubStorm's JavaScript Environment Variables. This
will allow you to [separate configuration from your code](http://12factor.net/config).

Some examples of configuration variables include:

* Identifiers for tracking services like Google Analytics and Mixpanel.
* Feature flags for your JavaScript framework, e.g. to enable experimental
  features.
* App-specific configuration, e.g. setting `ENV` to `production` or `staging`.

### Setting environment variables

Use `storm env set` to specify environment variables. You can set multiple
variables at once, for example:

```bash
mycomputer:~$ storm env set ENV=production GA_TRACKING_ID=UA-11111-1
Updating env vars for project "help"...

Optimizing...

Launching v46...
[Info] Successfully added env vars
ENV: production
GA_TRACKING_ID: UA-11111-1
```

Setting any new environment variables will re-publish your site with a new
`jsenv.js` file at the root of your PubStorm site, e.g.
http://example.pubstorm.site/jsenv.js

### Using environment variables in your app

Your JavaScript application should include `/jsenv.js` before loading itself,
e.g.:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <script src="/jsenv.js"></script> <!-- load env vars -->
  <script src="/js/app.js"></script> <!-- load your app -->
  <title>My App</title>
</head>
<body>
</body>
</html>
```

The `/jsenv.js` file should look like this:

```javascript
(function(global, env) {
  if (typeof module === "object" && typeof module.exports === "object") {
    module.exports = env;
  } else {
    global.JSENV = env;
  }
}(this, {"ENV":"production", "GA_TRACKING_ID": "UA-11111-1"}));
```

You can consume the environment variables by referring to the global `JSENV`
variable in your JavaScript code:

```javascript
if (JSENV.ENV === 'production') {
  // do stuff that should only be run in production
}
```

This is also useful for setting identifiers like Google Analytics tracking IDs:

```html
<script>
window.ga=window.ga||function(){(ga.q=ga.q||[]).push(arguments)};ga.l=+new Date;
ga('create', JSENV.GA_TRACKING_ID, 'auto');
ga('send', 'pageview');
</script>
<script async src='https://www.google-analytics.com/analytics.js'></script>
```


### Listing environment variables

Use `storm env` to view the environment variables currently set for your
project:

```bash
mycomputer:~$ storm env
Your JS Environment Variables for "example-project"
ENV: production
GA_TRACKING_ID: UA-11111-1
```

### Removing environment variables

Use `storm env rm` to remove any environment variables that you no longer need:

```bash
mycomputer:~$ storm env rm ENV

Optimizing...

Launching v3...
[Info] Successfully deleted ENV
```

Notice that this also publishes a new version of your PubStorm site so that your
previously deployed version is unaffected and uses the old environment
variables that it was deployed with. This is particularly important if you ever
need to [rollback your project]({% post_url 2016-05-10-storm-rollback %}).

To confirm that your environment variables have been successfully removed, use
`storm env`:

```bash
mycomputer:~$ storm env
Your JS Environment Variables for "example-project"
GA_TRACKING_ID: UA-11111-1
```

### Updating environment variables

To update an environment variable that has already been set, simply set it to
its new value using `storm env set`:

``` bash
mycomputer:~$ storm env set GA_TRACKING_ID=UA-22222-2

Optimizing...

Launching v4...
[Info] Successfully added env vars
GA_TRACKING_ID: UA-22222-2
```

To confirm that your environment variables have been successfully updated,
again,use `storm env`:

```bash
mycomputer:~$ storm env
Your JS Environment Variables for "example-project"
GA_TRACKING_ID: UA-22222-2
```
