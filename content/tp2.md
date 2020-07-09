+++
type   = "page"
title  = ""
+++

Remote Method Invocation (RMI)
==============================

The *remote procedure call* (**RPC**) approach extends the common programming abstraction of the procedure call to distributed environments, allowing a calling process to call a procedure in a remote node as if it is local.

*Remote method invocation* (**RMI**) is similar to RPC but for distributed objects, with added benefits in terms of using object-oriented programming concepts in distributed systems. It also extends the concept of an object reference to the global distributed environments, and allows the use of object references as parameters in remote invocations.

In this exercise you will experiment with RMI by developing an object oriented chat application using Java RMI.

### Requirements

-   [Java SDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html)
-   [Chat Application](/files/RMI.zip)

Objectives
----------

-   Experiment with the development of RMI.
-   Compare Socket and RMI development.

Chat Application
----------------

The chat application is composed of the following files:

-   `IChatServer.java` --- lists the (remote) operations exposed by the Chat Server.
-   `ChatServer.java` --- implements the Chat Server.
-   `IChatClient.java` --- lists the (remote) operations exposed by the Chat Client.
-   `ChatClient.java` --- implements the Chat Client.
-   `Run.java` --- isolate the code initializing the chat' client and server parts.
-   `security.policy` --- authorizes remote communication (in/out) in the JVM.
-   `StartServer.sh` and `StartClient.sh` --- shell scripts for launching the Chat server and client.

The figure below illustrates the operations exposed by the client and server:

![RMI](/img/RMI.png)

-   **Server**
    -   `addClient(client)` --- subscribes a new client into the chat server.
    -   `send(msg)` --- receives the message that will be broadcasted to all the clients connected (subscribed) to the server
-   **Client**
    -   `Notify(msg)` --- receives a server notification (e.g., the string representing the message sent by a user)

The following code snippets show the **Server and Client interfaces**:

```
public interface IChatServer extends Remote {
       public void send(String msg) throws RemoteException;
       public void addClient(IChatClient client) throws RemoteException;
}

public interface IChatClient extends Remote {
       public void notify(String msg) throws RemoteException;
}
```

Note that the figure also illustrates the process of a client subscription:

1.  A client instance contact call the *addClient* server operation and subscribe itself into the server.
2.  The server uses its *send* operation for *notifying* all connected clients about the connection of a new client.

You can start the chat' server and client parts by issuing the following commands:

```
java -Djava.security.policy=file:security.policy   # Run server 
java -Djava.security.policy=file:security.policy   # Run client
```

Remark that these commands are abstracted in the scripts `StartServer.sh` and `StartClient.sh`. 


To Do
-----

Hand in a short report explaining what you did and what you learned and a zip with your application. In particular describe the differences between developing a chat application using WebSockets and RMI and argue about the pertinence of using these tools for given applications.

1.  Broadcast a message to connected users when someone connects or disconnects.
2.  Add support for nicknames.
3.  Show who is online.
4.  Add private messaging.