TauNet
=============
##Connecting Pies together since 2015
###Copyright (c) 2015 Rachael Johnson
TauNet is a simple protocol to send and receive encrypted messages over a private network anywhere in the world.

###To Use
Download all files (excluding docs)
In your raspberryPi Terminal, type
>```
>python3 TauNet.py
>```

####Current Settings
- CipherSaber2 <- algorithm to output a stream of random numbers (run key scheduler 20 times after each message received / and transmitted)
- Password (universal for a network) - "password"



####Notes
- Scapy (to send a package)
    - search for python socket example

- Need to use threads to continue receiving while sending a message so no message gets lost

#####Basic Code Outline:
- Need an encrypt / decrypt function.
    - Functions will decrypt a message or encrypt a message using protocol specified by Bart
    
- Listen() function for a specific port - any message sent to that port will be received, decrypted, and then displayed to the user
- Send function (EncryptedStringToSend, AddressToSendTo)
    - Function will send an inputted string to an address 
    - select statement a readable - to check for a closed port
        
- Address Book -should read in a text file and convert to two lists - one with user names, and the other with user addresses
    - Text file should have one line per user / address
    - username should come first, followed by a space, followed by a address

- Main Screen - should be a class, this should handle the threads to ensure a message is never missed
    -Look up asyncio for python - might be what we need

- Log - should be a class also


#####Advance Code Outline:
 - protocol.py 
 - server.py
 - client.py
 - addressBook.py
 - TauNet.py
    - Main handler for everything. This has a while loop that will keep looping until user decides to quit program
    - It contains the main screen. If the user wants view messages, it calls the server class. If the user wants to send a message, it calls the addressBook class, has the user pick a person, then has the user choose
    
   
   
##Bugs
 - Need error handling when a connection has an error (error 111)
 - Need to make sure sockets are being closed after a connection is done