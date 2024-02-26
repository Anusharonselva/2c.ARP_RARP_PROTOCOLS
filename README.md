# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode())
```
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode()
```
## OUPUT - ARP
CLIENT
![Screenshot (395) 1](https://github.com/Anusharonselva/2c.ARP_RARP_PROTOCOLS/assets/119405600/47a86e6f-4784-4591-9878-3d27ae3d7502)
SERVER
![Screenshot (395)](https://github.com/Anusharonselva/2c.ARP_RARP_PROTOCOLS/assets/119405600/6eb8414e-c053-4608-aa7c-b595a063be83)

## PROGRAM - RARP
CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
 ip=c.recv(1024).decode()
 try:
   c.send(address[ip].encode())
 except KeyError:
   c.send("Not Found".encode())
```
SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
 ip=input("Enter MAC Address : ")
 s.send(ip.encode())
 print("Logical Address",s.recv(1024).decode())
```

## OUPUT -RARP
CLIENT
![Screenshot (396) 1](https://github.com/Anusharonselva/2c.ARP_RARP_PROTOCOLS/assets/119405600/45bd35f1-b993-499f-aea2-a84eb6562480)

SERVER

![Screenshot (396) 2](https://github.com/Anusharonselva/2c.ARP_RARP_PROTOCOLS/assets/119405600/2f5eeb9b-f901-4837-bd2e-bc7b28f33079)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
