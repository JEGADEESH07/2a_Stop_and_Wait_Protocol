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
### Client :
```python
import socket
s=socket.socket()
s.bind(('localhost', 8000))
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
### Server :
```python
import socket
s = socket.socket()
s.connect(('localhost', 8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```

## OUTPUT
### Client :
![WhatsApp Image 2024-03-06 at 11 24 51 AM(1)](https://github.com/JEGADEESH07/2a_Stop_and_Wait_Protocol/assets/113497131/3bb39631-6e14-4e44-a1cf-2d8e3dc88aef)
### Server :
![WhatsApp Image 2024-03-06 at 11 24 51 AM](https://github.com/JEGADEESH07/2a_Stop_and_Wait_Protocol/assets/113497131/76ac8942-3c88-4e51-8a6f-a9fc4cbb9767)



## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
