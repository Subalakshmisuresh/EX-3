# EX-3 IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

DATE :

AIM:

To write a python program to perform sliding window protocol

ALGORITHM:

1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it
will send NACKsignal to client.
6. Stop the program

PROGRAM:

CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
 st+=s
 c.send(str(l[i:st]).encode())
 ack=c.recv(1024).decode()
 if ack:
 print(ack)
 i+=s
 ```
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
REG NO:
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
 ```
OUTPUT:

CLIENT:

![cn-3c](https://github.com/Subalakshmisuresh/EX-3/assets/121957896/f5a3c27c-b44f-4907-af7d-3efa0d883457)

SERVER:

![cn-3s](https://github.com/Subalakshmisuresh/EX-3/assets/121957896/2b3fb2ee-f161-43d6-a3f2-691e00a1c5ec)


RESULT:

Thus, python program to perform stop and wait protocol was successfully executed
