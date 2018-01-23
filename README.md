Network Broadcast News
A NodeJS broadcast server for the largest media conglomerate in the world

slides

https://slides.com/devleague/events-and-emitters

https://slides.com/devleague/streams-in-node

Goals
server.js

Use the net module to create a new server that listens on a specified address 0.0.0.0 and port 6969 and listens for and accepts socket connections.

Manage which sockets are connected, and maintain your sockets so that it removes any sockets that disconnect from your server.

Each connected socket is a Duplex stream, when it emits a 'data' event, broadcast the data to all sockets.

client.js

Create a new net.Socket and connect to your running socket server.

Once connected, pipe your terminal's standard input stream to write to your connected socket.

Whenever the connected socket (client) emits a 'data' event, then data is being broadcasted from the server, pipe that data out to your terminal's standard output stream.

example
example

Additional Features
add username registration
once connected, the new client will be prompted to enter a username, store the username and then allow them to broadcast messages with all messages prepended with their username.
add admin broadcast
the admin (server.js) can broadcast messages and each message will be prepended with [ADMIN]
prevent users to set their name as [ADMIN] or any other user's name
[bonus] admin can enter a command to kick a client \kick username and kick ip:port will both disconnect the client
[bonus] add a rate limiter that if a client reaches the allowed 'writes per second' limet, automatically kick that user.
[bonus] write a client that floods another server, perhaps with a command \flood "message"
NBN Someone is Always Watching