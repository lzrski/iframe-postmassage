# IAI Shop - Embeded app communication model

This is a proof of concept for communicating between IAI Shop and a designer app. IAI Shop will be in a parent window and a designer app in an iFrame, possibly hosted on another domain (cross origin).

The communication is based on [postMessage API][]. For simplicity, jQuery is used on both ends, however it is not really required.

On load, overlay URL is passed from parent app to the app embeded in an iframe below (child app):

```json
{
  "name"  : "overlay",
  "value" : "URL to overlay PNG image"
}
```

When designer app is ready to save, it passes a data to be stored as an attachment to parent app.

```json
{
  "name"  : "save",
  "value" : {
    "preview" : "URL Encoded binary data",
    "fabric"  : "Lots of JSON encoded data, including URL encoded binary data",
    "overlay" : "window.overlay"
  }
}
```

It is displayed in an alert window.

Please review the sources.

[postMessage API]: https://developer.mozilla.org/en-US/docs/Web/API/Window.postMessage
