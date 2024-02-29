### 2a_Stop_and_Wait_Protocol
### AIM:
To write a python program to perform stop and wait protocol
### ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
### PROGRAM:
## Client Output:
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
## Server Output:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recieved".encode())
```
### OUTPUT:
## Client output:
![Client](https://github.com/SUBBIAH1904/2a_Stop_and_Wait_Protocol/assets/147473604/fba00c48-520c-422e-8a5a-6e858be43a6a)
## Server Output:
![Server](https://github.com/SUBBIAH1904/2a_Stop_and_Wait_Protocol/assets/147473604/479f4709-8e07-4961-bd0c-b21dcb9d2521)
![Screenshot 2024-02-29 214411](https://github.com/SUBBIAH1904/2a_Stop_and_Wait_Protocol/assets/147473604/f0fd50ec-ce19-43ae-8ba0-2febbd00c726)
### RESULT:

Thus, python program to perform stop and wait protocol was successfully executed.
