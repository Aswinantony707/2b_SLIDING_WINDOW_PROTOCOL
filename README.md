# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
Developed by : ASWIN ANTONY.S

Reg no : 212224220014

Client.py
```
import socket 
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5) 
c,addr=s.accept() 
while True:
    i=input("Enter a data: ") 
    c.send(i.encode()) 
    ack=c.recv(1024).decode() 
    if ack: 
        print(ack) 
        continue 
    else: 
        c.close()
        break
```
Server.py

```

import socket 
s=socket.socket() 
s.connect(('localhost',8080)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode()) 

```
## OUPUT

![Screenshot 2025-04-12 102735](https://github.com/user-attachments/assets/c63c97bd-d86c-4e5b-a79f-78926759ed07)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
