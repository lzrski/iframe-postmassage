# IAI Shop - Embeded app communication model

This is a proof of concept for communicating between IAI Shop and a designer app. IAI Shop will be in a parent window and a designer app in an iFrame, possibly hosted on another domain (cross origin).

The communication is based on [postMessage API][]. For simplicity, jQuery is used on both ends, however it is not really required.

On load, overlay URL is passed from this app to the app embeded in iframe below.

When data with name set to save is passed from embeded app, it is displayed in an alert window.

[postMessage API]: https://developer.mozilla.org/en-US/docs/Web/API/Window.postMessage
