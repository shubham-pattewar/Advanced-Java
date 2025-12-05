<img width="373" height="427" alt="image" src="https://github.com/user-attachments/assets/0446595a-835f-4bf3-8f4b-dee0d396781a" />

chat the name of folder in websocket
```
//index.jsp
<!DOCTYPE html>
<html>
<body>

<h2>Welcome to Chat Application</h2>

<p><a href="chat.jsp">Go to Chat Room</a></p>

</body>
</html>
```


```
//chat.jsp
<!DOCTYPE html>
<html>
<head>
<title>WebSocket Chat</title>
</head>
<body>

<h2>Real-Time Chat App</h2>

<div id="messages" style="border:1px solid #000; width:300px; height:200px; padding:10px; overflow:auto;"></div>

<br>
<input type="text" id="msgInput" placeholder="Type message...">
<button onclick="sendMsg()">Send</button>

<script>
    let ws = new WebSocket("ws://localhost:8080/10ChatApplication/ChatServer");

    ws.onmessage = function(event) {
        let box = document.getElementById("messages");
        box.innerHTML += event.data + "<br>";
    };

    function sendMsg() {
        let msg = document.getElementById("msgInput").value;
        ws.send(msg);
        document.getElementById("msgInput").value = "";
    }
</script>
```


```
//ChatServer.java
package com.websocket;

import jakarta.websocket.*;
import jakarta.websocket.server.ServerEndpoint;
import java.io.IOException;
import java.util.*;

@ServerEndpoint("/ChatServer")
public class ChatServer {

    private static Set<Session> users = Collections.synchronizedSet(new HashSet<>());

    @OnOpen
    public void onOpen(Session session) {
        users.add(session);
        System.out.println("New user connected: " + session.getId());
    }

    @OnMessage
    public void onMessage(String message, Session sender) throws IOException {
        synchronized (users) {
            for (Session session : users) {
                session.getBasicRemote().sendText(message);
            }
        }
    }

    @OnClose
    public void onClose(Session session) {
        users.remove(session);
        System.out.println("User disconnected: " + session.getId());
    }
}
```
</body>
</html>
