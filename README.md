# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
To write a python program for Implementation of sliding Window Protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
 
## CLIENT: 
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
## SERVER: 
 ```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True:    
    print(s.recv(1024).decode()) 
    s.send("acknowledgement recived from the server".encode())
```
![Screenshot 2024-09-06 135842](https://github.com/user-attachments/assets/4fb0eb32-a760-44d0-b9f5-5a3afdf59ab1)
## OUPUT
![Screenshot 2024-09-06 135809](https://github.com/user-attachments/assets/b95c9629-c8b7-44d8-8683-e66389ce8da8)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
