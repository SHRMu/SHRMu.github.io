---
layout:     post
title:      Java RMI Exception
subtitle:   exception solved
date:       2019-11-20
author:     SHR
header-img: 
catalog: true
tags:
    - Java RMI
    - Exception
---
# Java RMI Exception

- java.rmi.ConnectException

*Server exception: java.rmi.ConnectException: Connection refused to host: 10.0.75.1; nested exception is: 
	java.net.ConnectException: Connection refused: connect
java.rmi.ConnectException: Connection refused to host: 10.0.75.1; nested exception is: 
	java.net.ConnectException: Connection refused: connect
	at sun.rmi.transport.tcp.TCPEndpoint.newSocket(TCPEndpoint.java:619)
	at sun.rmi.transport.tcp.TCPChannel.createConnection(TCPChannel.java:216)
	at sun.rmi.transport.tcp.TCPChannel.newConnection(TCPChannel.java:202)
	at sun.rmi.server.UnicastRef.newCall(UnicastRef.java:338)
	at sun.rmi.registry.RegistryImpl_Stub.bind(RegistryImpl_Stub.java:60)
	at Server.main(Server.java:31)
Caused by: java.net.ConnectException: Connection refused: connect
	at java.net.DualStackPlainSocketImpl.connect0(Native Method)
	at java.net.DualStackPlainSocketImpl.socketConnect(DualStackPlainSocketImpl.java:79)
	at java.net.AbstractPlainSocketImpl.doConnect(AbstractPlainSocketImpl.java:350)
	at java.net.AbstractPlainSocketImpl.connectToAddress(AbstractPlainSocketImpl.java:206)
	at java.net.AbstractPlainSocketImpl.connect(AbstractPlainSocketImpl.java:188)
	at java.net.PlainSocketImpl.connect(PlainSocketImpl.java:172)
	at java.net.SocksSocketImpl.connect(SocksSocketImpl.java:392)
	at java.net.Socket.connect(Socket.java:589)
	at java.net.Socket.connect(Socket.java:538)
	at java.net.Socket.<init>(Socket.java:434)
	at java.net.Socket.<init>(Socket.java:211)
	at sun.rmi.transport.proxy.RMIDirectSocketFactory.createSocket(RMIDirectSocketFactory.java:40)
	at sun.rmi.transport.proxy.RMIMasterSocketFactory.createSocket(RMIMasterSocketFactory.java:148)
	at sun.rmi.transport.tcp.TCPEndpoint.newSocket(TCPEndpoint.java:613)
	... 5 more*
	
##### pls wait seconds after starting rmiregistry, I prefer this exception means, the rmiregistry is not ready for server to connect


---

- java.rmi.UnmarshalException

*Server exception: java.rmi.ServerException: RemoteException occurred in server thread; nested exception is: 
	java.rmi.UnmarshalException: error unmarshalling arguments; nested exception is: 
	java.lang.ClassNotFoundException: IFlightServer
java.rmi.ServerException: RemoteException occurred in server thread; nested exception is: 
	java.rmi.UnmarshalException: error unmarshalling arguments; nested exception is: 
	java.lang.ClassNotFoundException: IFlightServer
	at sun.rmi.server.UnicastServerRef.dispatch(UnicastServerRef.java:389)
	at sun.rmi.transport.Transport$1.run(Transport.java:200)
	at sun.rmi.transport.Transport$1.run(Transport.java:197)
	at java.security.AccessController.doPrivileged(Native Method)
	at sun.rmi.transport.Transport.serviceCall(Transport.java:196)
	at sun.rmi.transport.tcp.TCPTransport.handleMessages(TCPTransport.java:573)
	at sun.rmi.transport.tcp.TCPTransport$ConnectionHandler.run0(TCPTransport.java:834)
	at sun.rmi.transport.tcp.TCPTransport$ConnectionHandler.lambda$run$0(TCPTransport.java:688)
	at java.security.AccessController.doPrivileged(Native Method)
	at sun.rmi.transport.tcp.TCPTransport$ConnectionHandler.run(TCPTransport.java:687)
	at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1149)
	at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:624)
	at java.lang.Thread.run(Thread.java:748)
	at sun.rmi.transport.StreamRemoteCall.exceptionReceivedFromServer(StreamRemoteCall.java:283)
	at sun.rmi.transport.StreamRemoteCall.executeCall(StreamRemoteCall.java:260)
	at sun.rmi.server.UnicastRef.invoke(UnicastRef.java:375)
	at sun.rmi.registry.RegistryImpl_Stub.bind(RegistryImpl_Stub.java:68)
	at Server.main(Server.java:31)*
	
##### pls remember to start rmiregistry in the exactly same directory, which contains your Server.class, never waste time to do this stupid thing like me :(((