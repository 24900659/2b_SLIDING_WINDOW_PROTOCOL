# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
CLIENT:

 import socket
 
 s=socket.socket()
 
 s.bind(('localhost',8000))
 
 s.listen(5)
 
 c,addr=s.accept()
 
 size=int(input("Enter number of frames to send : "))
 
 l=list(range(size))

 s=int(input("Enter Window Size : "))
 
 st=0


 i=0
 
 while True:
 
 while(i<len(l)):
 
 st+=s
 
 c.send(str(l[i:st]).encode())
 
 ack=c.recv(1024).decode()
 
 if ack:
 
 print(ack)
 
 i+=s
 
 SERVER:
 
 import socket
 
 s=socket.socket()
 
 s.connect(('localhost',8000))
 
 REG NO:
 
 while True:
 
 print(s.recv(1024).decode())
 
 s.send("acknowledgement recived from the server".encode())
## OUPUT
CLIENT:
![Screenshot (43)](https://github.com/user-attachments/assets/1a7d7fde-6605-4912-ab3c-6b8d5b33ff2d)
SERVER:
![Screenshot (44)](https://github.com/user-attachments/assets/6fc17bd8-01e6-4372-a459-452f46508527)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
