# A WebSockets Chat Application

### Set up your development environment

Set up your development environment as follows.

First create a `package.json` file to describe your project:

``` bash
$ npm init
```

Choose a project name and answer the questions (you can use the defaults).

Now install the `express` web framework:

``` bash
$ npm install express --save
```


### Create a server

1. Create a server `index.js` file:

``` javascript
let express = require('express');

let port = 4800;
let app = express();
let server = app.listen(port, () => {
  console.log(`Listening on port ${port}`);
});

app.use(express.static('public'));
```

   This sets up the `express` web framework to listen on a specific port for incoming HTTP requests.

   The last line serves files from the `public` folder when accessed via the URL `http://localhost:4800/`.

2. Start the server:

       $ node index.js

   You can also use the `nodemon` tool to start it; `nodemon` offers faster development as it restarts the server whenever you make changes to your source file(s):

       $ nodemon index.js

3. You should now be able to issue an HTTP request from your browser, but of course it will just return an error page:

      ``` http
      Cannot GET /
      ```

So create `public` folder and place an `index.html` in that:

``` html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>WebSockets Chat</title>
  </head>
  <body>
    <h1>Hi</h1>
  </body>
</html>
```


## Part 2 - Connecting to the Server

Now to enable our server for websockets, using the `socket.io` library.

1. First, install the library:

    ```
    $ npm install socket.io --save
    ```

2. Now include the library at the top of `index.js`:

    ``` javascript
    let socket = require('socket.io');
    ```

3. Have the server accept websocket connections: at the end of `index.js`, add:

    ``` javascript
    let io = socket(server);
    ```

4. The `socket.io` library is event-driven. When an event occurs, we will handle it with a callback. <br> <br> At the bottom of `index.js`, create an event handler to handle incoming websocket connection requests:

    ``` javascript
    io.on('connection', socket => {

    });
    ```

5. Now to fill in the body of the event handler. We'll display that a client has connected, and also handle `disconnect` events:

    ``` javascript
      console.log('a socket connected');

      socket.on('disconnect', () => console.log('a socket disconnected'));
    ```

6. Finally, we'll create a client-side script to form the basis of our app.

    1. Create a `public/chat.js` file.
    2. Add into this a `console.log('chat.js running')` so we can check the script is running in the browser.
    3. Also add the line `let socket = io.connect();`

7. Run the server again and connect from your browser. Refreshing the browser page a few times should show some messages in the server console.

## Part 3 - Sending Data

1. Let's first log chat messages received by the server (`index.js`):

``` javascript
socket.on('chat-message', message => console.log(`message:`, message));
```

2. We'll need to enhance our `index.html` to have a 'username' input field, a 'message' input field, and a button to send the message:

![chat-screenshot](images/chat-screenshot.png)

Copy the example from [here](https://gist.github.com/petermunro/596653c20eb1c5a15b2008c68b042cd3).

> If you copy this example and don't have access to "bootstrap", remove this line:

``` html
    <link rel="stylesheet" href="css/bootstrap.min.css">
```



3. Now to modify `chat.js`. Retrieve the DOM elements needed:

``` javascript
// select DOM elements
let usernameField = document.getElementById('username');
let messageField = document.getElementById('message');
let form = document.getElementsByTagName('form')[0];
```

4. Grab the username:

``` javascript
let username = '';
usernameField.addEventListener('change', e => {
  username = e.target.value;
});
```

5. Now handle the message 'Send' button (form submit event), and send our message via websockets to the server:

``` javascript
form.addEventListener('submit', e => {
  socket.emit('chat-message', {
    username,
    message: messageField.value,
  });
  messageField.value = '';
  e.preventDefault();
});
```


## Part 4 - Broadcasting Events to other Users

### Server side

Instead of simply logging an incoming chat message, we'll forward it to all other users. In the server `index.js`, replace this line:

``` javascript
socket.on('chat-message', message => console.log(`message:`, message));
```

with this:

``` javascript
socket.on('chat-message', message => {
  console.log(`message:`, message);
  io.emit('chat-message', message);
});
```

### Client side

On the client, we'll need to show incoming messages in the message box.

1. Near the top of `chat.js`, get the `<div>` that will display the messages:

``` javascript
let messages = document.getElementById('messages');
```

2. Now when a message arrives from the server, add it into your 'messages' `<div>`:

``` javascript
socket.on('chat-message', message => {
  messages.insertAdjacentHTML('beforeEnd', `<p>${message.username}: ${message.message}</p>`);
});
```


---
## Further exercises for the reader

1. If you empty the 'message' input, make "is typing a message..." disappear.
2. Display a list of users
3. Send a private message to just one user
