## CS-6650-Project-3


#### i: How to run your server and client programs?
First go to the server class, click run. Then go to the Client class, run the main method. Since I use a while loop to recursively receive instructions from the client, the first thing you should see is "Want continue? Y/N", you need to type in Y or N(capitalize sensitive). If you type N, the client would be closed. If you click Y, you will see "What you want to do next?". Then, you should type in either "PUT", "GET" or "DELETE". If you input is "PUT", you'll see "Please input the key and value you want to insert into the Hashmap (E.g. A APPLE):", to ensure the valid input, the next thing you should do is put key, value into the concurrentHashmap. DELETE and GET option is the similar story, you should be able to follow instructions to do it. 
