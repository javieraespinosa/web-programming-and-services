+++
type   = "page"
title  = ""
+++


Interprocess Communication with WebSockets
==========================================

A **socket** is an endpoint of an inter-process communication flow. A socket is bound to a port in a computer and enables communication over a communication protocol (e.g. UDP and TCP). When a socket is bound to the TCP protocol it allows bi-directional communication between two processes.

**WebSocket** is a new technology (HTML5) inspired in classic sockets. WebSocket provides *full-duplex communication* over browser and servers, but it can be used by any client or server application (e.g. mobile applications). In this exercise you will experiment with sockets by developing a chat application using WebSockets.

### Requirements

-   [Chat Application](/files/WebSockets.zip)
-   [NodeJS](http://nodejs.org/)
-   [Express](http://expressjs.com/)
-   [SocketIO](http://socket.io/)

Objectives
----------

Experiment with the development of sockets.

Chat Application
----------------

The chat application is composed of the following files:

-   js --- *contains the chat console client*
-   html --- *contains the chat web client*
-   js --- *contains the code of the server*
-   json --- contains the build dependencies

Application dependencies can be installed by executing the following command in the folder containing the application files:

```
npm install
```

Client and server are executed by issuing the following commands:

```
node Client.js
node Server.js
```

Once the server is running, open a browser and go to [**http://localhost:8080**](http://localhost:8080/).

To Do
-----

Hand in a short report explaining what you did and what you learned and a zip with your application to `javier.espino**@imag.fr`.

1.  Broadcast a message to connected users when someone connects or disconnects.
2.  Add support for nicknames.
3.  Show who's online.
4.  Add private messaging.
5.  Model the application using the object oriented model and describe its architecture.
