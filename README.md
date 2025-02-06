# python-computer-network
Computer Networks Project from University.

This project simulates a TCP communication between a client and a server. The two python files, MessageBoardClient.py acts as the client side and MessageBoardServer.py acts the server file. This project was developed in Windows 11 64 bit, on VSCode. The following will include steps on how to simulate client and server communication. 

Steps:
1. Open both MessageBoardClient.py and MessageBoardServer.py alongside their own individual terminals.
2. Run MessageBoardServer.py first, it should show "Listening...."
3. Once you have successfully run the server side, run the MessageBoardClient.py
4. If successful, it will ask for the IP Address of the server, which would be your device's IP address, for Windows, you can check your device's IP Address by going into command prompt and typing "ipconfig", find the IPV4 address and paste into the terminal, for MAC/Linux, open terminal and type "ifconfig", you should see the IPV4 address.
5. Next, the client side will ask for the port, which will be "16111".
6. If you have successfully provided the correct inputs for IP Address, and Port, it will attempt to build connection and test with the server, if successful, a successful message will be shown and you can start providing commands, if not, the client will continuously ask for IP Address and port until connection with server has been established.


The list of commands are:
1. POST -> Able to input and save messages. Each POST command ends when user inputs "#" into the terminal. Client will then send "#" to server which will record all messages sent up to "#" as one message and provide it with a specific message ID
2. GET ->  Sends a get request to the server which then returns all recorded POST messages that was sent previously by client. Will return message id, the time that the message was received, followed by the message sent by the user through the client
3. DELETE -> Able to delete a specific message by inputting the message ID of that wanted deleted message. Can delete multiple messages at once, which delete command can be terminated by inputting "#". If any of the inputted message ID is invalid, ie. message ID doesn't exist or was never recorded, the server will return an error message and users have to input all the message ID again, despite the previous one was valid.
4 QUIT -> If a QUIT command is entered, client will terminate connection with server, and stop all operation at once.

Notes:
Multiple error checking cases have been implemented, such as KeyboardInterrupt, ValueError, TimeoutError, and failed connection. It is important to note that despite a client quitting, if the server is still listening and the client reconnects, all previous data will be stored.

