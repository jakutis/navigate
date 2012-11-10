# navigate.js

Description: A router for the browser (client-side JavaScript).

Home page: [jakut.is/git/NAVIGATE/about](https://jakut.is/git/NAVIGATE/about/)

Demo page: [jakut.is/demos/navigate](https://jakut.is/demos/navigate/)

Git repository url: [git://jakut.is/NAVIGATE](git://jakut.is/NAVIGATE)

[npm](https://npmjs.org) package: [navigate](https://npmjs.org/package/navigate)

[jam](http://jamjs.org) package: [navigate](http://jamjs.org/packages/#/details/navigate)

License: [MIT](https://jakut.is/git/NAVIGATE/plain/LICENSE)

Author: [Vytautas Jakutis](https://jakut.is)

# Features

* has no dependencies
* supports Asynchronous Module Loader (AMD, RequireJS), CommonJS (Node.js require) and regular &lt;script&gt; loading
* if HTML5 History API is not available, falls back to hashes
* handles click events on same origin links
* supports browsers:
  - Mozilla Firefox 1.0+
  - Opera 8.00+
  - Google Chrome 1+
  - Microsoft Internet Explorer 6+
  - Apple Safari 3.0+

# API Reference

```
// configure, can be called anytime at all (including never)
navigate({
    // whether same origin a.href clicks are captured
    clickHandlingEnabled : true,
    // URL path prefix
    basePath : ''
});

// initialize
navigate();

// another way to initialize - when the initial page is needed
navigate(function(entryPage) {
    console.log('Entry page to this web app is ' + entryPage);
});

// handle navigations to /user/* pages
navigate('^\\/user\\/(.+)$', function(args, from, to) {
    console.log('Navigated from page ' + from + ' to ' + to);
    console.log('Showing user ' + args[0]);
});

// navigate to user's "tahu" page
navigate('/user/tahu');
```
