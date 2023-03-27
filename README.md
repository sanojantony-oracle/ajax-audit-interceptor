ajax-audit-interceptor
================

This permits to wire some request and response hooks on any Ajax calls.

I find this handy, for exemple, to handle user session expiration and redirect the user to the login page whenever an Ajax call fails with an auth failure.

Install
==============

Install it!
```
npm install ajax-audit-interceptor --save
```

Use it! (with **Browserify**)
```javascript
var AjaxAuditInterceptor = require("ajax-audit-interceptor");
```

API
===============

```javascript
// Setup some callbacks
AjaxInterceptor.addRequestCallback(function(xhr) {
    console.debug("request",xhr);
});
AjaxInterceptor.addResponseCallback(function(xhr) {
    console.debug("response",xhr);
});

// Will proxify XHR to fire the above callbacks
AjaxInterceptor.wire();

// Do some requests
// ................

// Will restore XHR and not fire anymore the callbacks
AjaxInterceptor.unwire();
```

You can add and remove callbacks dynamically while the interceptor is wired.

License
===================

MIT
