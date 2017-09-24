---
layout: post
title: "websocked基础"
author: "ryy"
---

实例

```
<!DOCTYPE html>
<html>
<head>
    <meta charset="utf-8">
    <title>websocket</title>
</head>
<body>
    <h1>Echo Test</h1>
    <input type="text" id="sendTxt">
    <button id="sendBtn">发送</button>
    <div id="recv"></div>
    <script type="text/javascript">
        var websocket= new WebSocket("ws://echo.websocket.org/");
        websocket.onopen=function(){
            console.log('websocket open');
            document.getElementById("recv").innerHTML="Connected";
        }
        websocket.onclose=function(){
            console.log('websocket close')
        }
        websocket.onmessage=function(e){
            console.log(e.data);
            document.getElementById("recv").innerHTML=e.data;
        }
        document.getElementById("sendBtn").onclick=function(){
            var txt=document.getElementById("sendTxt").value;
            websocket.send(txt);
        }
    </script>
</body>
</html>
```

解读

    1、申请一个WebSocket对象
    参数是需要连接的服务器端的地址，同http协议使用http://开头一样，WebSocket协议的URL使用ws://开头，另外安全的WebSocket协议使用wss://开头。
    var wsUri ="ws://echo.websocket.org/";
    websocket = new WebSocket(wsUri);
    2、WebSocket对象一共支持四个消息 onopen, onmessage, onclose和onerror
         我们可以看出所有的操作都是采用消息的方式触发的，这样就不会阻塞UI，使得UI有更快的响应时间，得到更好的用户体验。
    （1）当Browser和WebSocketServer连接成功后，会触发onopen消息;
    websocket.onopen = function(evt) {};
    （2）如果连接失败，发送、接收数据失败或者处理数据出现错误，browser会触发onerror消息;
    websocket.onerror = function(evt) { };
    （3）当Browser接收到WebSocketServer发送过来的数据时，就会触发onmessage消息，参数evt中包含server传输过来的数据;
    websocket.onmessage = function(evt) { };
    （4）当Browser接收到WebSocketServer端发送的关闭连接请求时，就会触发onclose消息。
    websocket.onclose = function(evt) { };