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
## Program
```python
Developed By : NARAMALA KUMARTEJA
Reg No: 212223230132
```
## Server
```Python
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())

```
## Client
```python
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
## Output:
### Client:
![image](https://github.com/user-attachments/assets/c3f20019-e0bb-4bc0-a01c-1d9db76eae8a)

### Server:
![image](https://github.com/user-attachments/assets/5a7adcd7-1724-4e52-8cbe-4e6d32000089)

## Result:
Thus, python program to perform stop and wait protocol was successfully executed.
