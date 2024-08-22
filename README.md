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
## PROGRAM:
Client:
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
Service:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
![Screenshot 2024-08-22 201356](https://github.com/user-attachments/assets/af645ee0-8c29-47f5-a0e7-e6a1c15e6d6e)
![Screenshot 2024-08-22 201411](https://github.com/user-attachments/assets/85ee9b80-dc3b-44ab-9669-633c5cbdfdb9)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
