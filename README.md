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
 s.send("Acknowledgement Recived".encode())

```
  

### OUTPUT:
## Client output:
![Screenshot 2024-02-29 210206](https://github.com/kaviya546/2a_Stop_and_Wait_Protocol/assets/150368823/01d308a3-67b0-4f46-a7d2-27209b3781fb)

## Server output:
![Screenshot 2024-02-29 210153](https://github.com/kaviya546/2a_Stop_and_Wait_Protocol/assets/150368823/977864da-997b-49ee-adcc-0674b6372d27)
![Screenshot 2024-02-29 210129](https://github.com/kaviya546/2a_Stop_and_Wait_Protocol/assets/150368823/53b09664-4a98-4f69-a9a1-84fc69260b42)


### RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
