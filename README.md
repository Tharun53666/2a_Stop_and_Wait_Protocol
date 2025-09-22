# 2a_Stop_and_Wait_Protocol
# REGISTER NO:212224240170
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
client:
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
server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
   print(s.recv(1024).decode())
   s.send("Acknowledgement Recieved".encode())
```
## OUTPUT
client output:

<img width="395" height="277" alt="Screenshot 2025-09-22 151611" src="https://github.com/user-attachments/assets/25391a93-cdef-4538-8468-df29d7d37442" />

server output:

<img width="412" height="163" alt="Screenshot 2025-09-22 151604" src="https://github.com/user-attachments/assets/6b0e43a8-a0fc-48af-b05b-0e9800ac1312" />





## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
