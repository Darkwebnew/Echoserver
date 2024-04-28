# EX-1.Echoserver
## Date:
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

# DESIGN STEPS:

## Step 1:
Design of echo server and client using python socket

## Step 2:
Implementation using Python code

## Step 3:
Testing the server and client 

# PROGRAM:
## SERVER CODE:
### echo-server.py
```
import socket

HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```
## CLIENT CODE:
### Echo-client.py
```
import socket

HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)
print(f"Received {data!r}")
```
# OUTPUT:
## SERVER CODE:
![image](https://github.com/Darkwebnew/Echoserver/assets/143114486/0f4120ff-5fc3-4de8-914e-40e6be0b96e1)
## CLIENT CODE:
![image](https://github.com/Darkwebnew/Echoserver/assets/143114486/cceba549-0717-4960-b2a7-a4f82d8234dc)
# RESULT:
The program is executed successfully
