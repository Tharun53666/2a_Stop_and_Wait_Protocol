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

![Screenshot 2025-04-12 112634](https://github.com/user-attachments/assets/b1e513ab-0045-4fab-a1b0-a1a105e1fdcb)



server output:

![Screenshot 2025-04-12 112658](https://github.com/user-attachments/assets/a8fe4484-8421-46f1-923a-2025cab091ce)




## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
