# obs-websocket-js
OBSWebSocket.JS allows Javascript-based connections to [obs-websocket](https://github.com/Palakis/obs-websocket).  
Based heavily on [obs-remote](https://github.com/nodecg/obs-remote-js), which is built for the older, obs-classic compatible plugin.

# [API Documentation](dist/documentation.md)

## Usage

### Plain Javascript
Include the distributable file in the header of your HTML.
```html
<script type='text/javascript' src='dist/obs-websocket.js'></script>
```

Then make use of it.
```html
<script>
  var ws = new OBSWebSocket();

  // Bind some listeners.
  ws.onConnectionOpened = function() {
    console.log('Connection Opened');

    // Send some requests.
    ws.getCurrentScene(function(message) {
      console.log(message);
    });
  };

  // Open the connection and Authenticate if needed. URL defaults to localhost:4444
  ws.connect(); // ws.connect('url', 'password');
</script>
```


### NodeJS
```sh
npm install obs-websocket-js --save
```

Add the library to your application.
```js
var OBSWebSocket = require('obs-websocket-js');
var obsWS = new OBSWebSocket();

obsWS.connect('url', 'password');
```

# Contributing
- Install [node.js](http://nodejs.org).
- Clone the repo.
- Go nuts.
- Generate the concatenated Javascript file and API documentation by running the following...
```sh
npm run build
```

## Formatting Guidelines
- 2 spaces rather than tabs.
