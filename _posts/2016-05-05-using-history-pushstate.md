---
layout: post
title: "Using history.pushState"
category: documentation
blurb: Use history.pushState in your web app with 200.html
slug: using-history-pushstate
navorder: 6
---

If you are building a single-page JavaScript application, you may want
to take advantage of `history.pushState` and the HTML5 History API to
get cleaner URLs without the ugly `#`.

To make sure routes defined in your application are accessible, add a
`200.html` file to the root of your project. Once `200.html` page is
added, when a request comes in for a URL where you do not have an HTML
page, PubStorm will serve the `200.html` instead, to let your
client-side router handle the route.

You should load your client-side web application and the router in the
`200.html` page as you would in the normal entry point of the
application. The client-side router should then recognize the URL and
route to an appropriate page.

```html
<!-- 200.html -->
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>My App</title>
</head>
<body>
  <script src="/js/app.js></script> <!-- load javascript application -->
</body>
</html>
```

### Enabling pushState support in Ember.js

To enable pushState support in Ember.js, simply set the location
attribute of the `App.Router` to be `"history"`.

```javascript
App.Router.reopen({
  location: "history"
});
```

### Enabling pushState support in React with React Router

You can enable pushState support in React apps that use React Router
library by setting the history property of the main `<Router>` component
to be `browserHistory` that can be imported from `react-router` package.

```javascript
import { browserHistory } from 'react-router'; // ES6

// ...

render((
  <Router history={browserHistory} routes={routes} />,
), document.getElementById("app"));
```

### Enabling pushState support in Angular

To enable pushState support in Angular, enable html5 mode in
`locationProvider`.

```javascript
angular.module('myapp', []).config(function($routeProvider,
$locationProvider) {
  $locationProvider.html5Mode(true);
});
```
