# 2a_Stop_and_Wait_Protocol

#### NAME:KAMALESH R
#### REGISTER NUMBER:212223230094

## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

### CLIENT
```
# importing the socket
import socket 
s=socket.socket() 
s.bind(('localhost',8000))
s.listen(5) 
c,addr=s.accept()
# using while loop for the execution
while True:
# taking the input from the user
    i=input("Enter a data: ") 
    c.send(i.encode()) 
    ack=c.recv(1024).decode() 
    if ack:
# if the condition is true, it is printed and continued
        print(ack) 
        continue 
    else:
# if the condition is false, it is closed and break
        c.close() 
        break 
```
### SERVER
```
# importing the socket
import socket 
s=socket.socket() 
s.connect(('localhost',8000))
# using while loop for the execution
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode()) 
```
## OUTPUT

![2A](https://github.com/user-attachments/assets/281e35f6-e394-4229-b0e6-74f5827a7604)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
