## CS-6650-Project-2

#### i: How to build your server and client nodes? 
ServantInterface: Include methods needed for the three instructions. (GET, PUT, DELETE). 
Servant: Implement methods decleared in the servantInterface. Library I use: java.rmi.RemoteException, java.rmi.server.UnicastRemoteObject, java.util.concurrent.ConcurrentHashMap;
Client: RMI client. Recursively receive calls from user's input and bind the user's input info. to the server side. Java library use: java.net.MalformedURLException; java.rmi.Naming; java.rmi.NotBoundException; java.rmi.Remote; java.rmi.RemoteException; java.util.Scanner;
Server: RMI server. Java library use: java.rmi.RemoteException; java.rmi.registry.LocateRegistry; java.rmi.registry.Registry; java.rmi.server.UnicastRemoteObject;


#### ii: How to run your server and client programs?
First go to the server class, click run. Then go to the Client class, run the main method. Since I use a while loop to recursively receive instructions from the client, the first thing you’d see is “Want continue? Y/N”, you need to type in Y or N(capitalize sensitive). If you type N, the client would be closed. If you click Y, you’ll see “What you want to do next?”. Then, you should type in either “PUT”, “GET” or “DELETE”. If you input is "PUT", you'll see "Please input the key and value you want to insert into the Hashmap (E.g. A APPLE):", to ensure the valid input, the next thing you should do is put key, value into the concurrentHashmap. DELETE and GET option is the similar story, you should be able to follow instructions to do it. 


#### iii: Your executive summary
##### Assignment Overview:
In the last project, we focus on writing code on setting up communication between client and server, simply by creating the socket and sending the socket from client to the server. We also learned the difference between UDP and TCP protocol, UDP is the one that can transfer the data faster but is less reliable. TCP is the opposite. In this project, we focus on enabling clients and servers to communicate using Remote Procedure Call(RPC) instead of sockets. Many frameworks can be used to set up RPC, the one I choose to use in the project is called Java RMI. There're many reasons why I choose RMI to communicate, it's easy to set up. Also, it set up the multithread work automatically when there are many clients' requests from the server. After doing this project, I have a deeper understanding of how middleware works and how we can apply it. 

##### Technical Impression: 
The procedure I write this project is quite similar to the previous one. First to set up the server and then build the client. I met some issues while building the server since I didn't understand how the create/getRegistry work correctly. To enable the communicate between client server, the client side should call rmi::localhost:1/... The localhost stands for your own laptop and 1 is stands for the port number. If it can find a correnespond instruction and port number, then the client can receive the act result send from the server. To store the key and value, the first data structure that pops out of my mind to use is HashMap. However, HashMap is not thread safe. Similar to the HashMap, ConcurrentMap can solve the threadsafe problem. ConcurrentMap in Java is a class that implement AbstraceMap It's basically work the same thing as the HashMap. The problem of using Hashmap is, when there're many client requests concurrently to the server, the hash code may "collide". If that happened, the <key, value> we stored my not accurate. There's three instructions that should be performed in this project, GET, DELETE and PUT. To follow to OOD principle, I write methods name in the servantInterface and they implement all of those methods in the Servent class. 
