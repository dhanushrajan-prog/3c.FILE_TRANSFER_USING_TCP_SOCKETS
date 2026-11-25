# 3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
## AIM
To write a python program for creating File Transfer using TCP Sockets Links
## ALGORITHM:
1. Import the necessary python modules.
2. Create a socket connection using socket module.
3. Send the message to write into the file to the client file.
4. Open the file and then send it to the client in byte format.
5. In the client side receive the file from server and then write the content into it.
## PROGRAM
### fileserver.py
```
import socket
server = socket.socket()
server.bind(("127.0.0.1", 5555))
server.listen(1)
print("Server waiting for connection...")
client, addr = server.accept()
print("Connected to:", addr)
filename = input("Enter file name to send: ")
with open(filename, "rb") as file:
 data = file.read()
 client.send(data)
print("File sent successfully")
client.close()
server.close()
```
### fileclient.py
```
import socket
client = socket.socket()
client.connect(("127.0.0.1", 5555))
save_name = input("Enter name to save file: ")
data = client.recv(1000000)
with open(save_name, "wb") as file:
 file.write(data)
print("File received successfully")
client.close()
```
## OUPUT
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/fabe9913-fd51-4f80-8a6d-49981d00aa4d" />
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c979c82b-f63e-4410-9681-47404eaacf18" />

## RESULT
Thus, the python program for creating File Transfer using TCP Sockets Links was 
successfully created and executed.
