# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

## DATE : 09-03-2023

## AIM :
To write a python program to perform client server model.

##ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program



## CLIENT PROGRAM:
## Developed By : MALARVIZHI G
## Reg No : 212222040096
import socket

s=socket.socket()

s.bind(('localhost',8080))

s.listen(5) 

c,addr=s.accept()

while True:

	i=input("ENter a data:")
  
	c.send(i.encode())
  
	ack=c.recv(1024).decode()
  
	if ack:
  
		print(ack)
    
		continue
    
	else:
  
		c.close()
    
		break

## SERVER PROGRAME:

import socket

s=socket.socket()

s.connect(('localhost',8080))

while True:

	print(s.recv(1024).decode())
  
	s.send("Recieved".encode())


## CLIENT OUTPUT:

![ex 1 client](https://github.com/22008650/19CS406-EX-1/assets/122548204/f1d8fc20-443e-4259-9957-94e64886ad4a)
## SERVER OUTPUT:
![ex 1 server](https://github.com/22008650/19CS406-EX-1/assets/122548204/6931056d-618d-497b-a01f-c0213340d240)




## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
