# 2c.SIMULATING ARP /RARP PROTOCOLS

# Name : Gayathri A
# RegNo : 212221230028
## AIM :
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
## OUPUT - ARP :

![image](https://github.com/Gayathriraj18/2c.ARP_RARP_PROTOCOLS/assets/94154854/fc477097-0737-4c7a-8bcb-989ebac22121)

## PROGRAM - RARP: 
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
```

## OUPUT -RARP :

![image](https://github.com/Gayathriraj18/2c.ARP_RARP_PROTOCOLS/assets/94154854/92e1da57-773d-4412-bc99-a9b293566ac1)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
