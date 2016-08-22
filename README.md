# cordova-plugin-oic

A Cordova plugin to expose the [OIC
specification](https://openconnectivity.org/resources/specifications) to cross
platform applications written in JavaScript.


## Purpose

To provide a plugin which allows using the OIC specification across all mobile
platforms without requiring the user to deal with implementing and compiling
the native code for each operating system.

Current platforms:
 * Android

## Building

As this is a Cordova plugin, you will build it as part of an app. For a demo
app, please see the [cordova-plugin-oic-demo
app](https://github.com/siovene/cordova-plugin-oic-demo).  Build instructions
are located at [its README
file](https://github.com/siovene/cordova-plugin-oic-demo/blob/master/README.md).

## Running tests

This plugin contains a test suite that runs as a Cordova app. Please find it at
the [cordova-plugin-oic-tests project
page](https://github.com/siovene/cordova-plugin-oic-tests).


## Quick start with the API

```javascript
var plugin = cordova.require('cordova/plugin/oic');

plugin.onresourcefound = function(event) {
    var resource = event.resource;
    // Do something with the resource.

    resource.onupdate = function(event) {
        var updates = event.updates;
        // Update your UI when changes have occurred.
    };
};

plugin.setBackend('iotivity').then(function() {
    plugin.findResources();
});
```

More details can be found at the [OIC JS spec for the Soletta
project](https://github.com/zolkis/soletta/blob/master/doc/js-spec/oic.md).
