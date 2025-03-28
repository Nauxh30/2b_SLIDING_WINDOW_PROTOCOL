# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## NAME: NAUSHEEN FATHIMA A 
## REGISTER NUMBER : 212224230179.
## AIM
To write a python program to perform sliding window protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
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
while True:    
    print(s.recv(1024).decode()) 
    s.send("acknowledgement recived from the server".encode()) 
```
## OUPUT
CLIENT 
![CN2 1](https://github.com/user-attachments/assets/0ce8f9bd-70df-4567-be83-53ec23b654d0)

SERVER 
![CN2](https://github.com/user-attachments/assets/b6b4a4b7-623b-4f8c-8c31-7abb07a3b0cf)


## RESULT

Thus, python program to perform stop and wait protocol was successfully executed
