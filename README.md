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
client 
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
server
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
```
## OUTPUT
<img width="934" height="340" alt="Screenshot 2025-09-09 143123" src="https://github.com/user-attachments/assets/9283fa66-893b-4281-a140-0d80df3633a8" />
<img width="929" height="353" alt="Screenshot 2025-09-09 143137" src="https://github.com/user-attachments/assets/3e276642-1baa-4e61-9788-c31273ba8d35" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
