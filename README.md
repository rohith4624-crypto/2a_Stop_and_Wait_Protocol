# 2a_Stop_and_Wait_Protocol
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

## client.py
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
## server.py
```
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
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
## OUTPUT

## client:

<img width="630" height="152" alt="image" src="https://github.com/user-attachments/assets/5240f818-1c45-460e-8604-c511097b0884" />

## server:

<img width="626" height="245" alt="image" src="https://github.com/user-attachments/assets/02ff7bfc-8aaa-4572-a441-28e1e4785d43" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
