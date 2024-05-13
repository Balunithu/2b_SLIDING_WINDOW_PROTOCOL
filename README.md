## 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### NAME: NITHYA SHREE B
### REG.NO:212223220071
### Server
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
### Client
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
### Server
![322401700-7bcba08d-715d-417c-b8ab-fe584727e089](https://github.com/Balunithu/2b_SLIDING_WINDOW_PROTOCOL/assets/161273477/28a1c0cd-10b1-4a50-aa6e-4e4cd94a7a79)


### Client

![322401895-d81a1f40-2d87-49c6-b196-e4cdf9c4a792](https://github.com/Balunithu/2b_SLIDING_WINDOW_PROTOCOL/assets/161273477/7161bf73-e3ad-4e76-829b-cf08622bfafa)




## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
