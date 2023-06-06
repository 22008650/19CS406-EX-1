# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

## DATE : 09-03-2023

## AIM :
To write a python program to perform client server model.

## ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program



## CLIENT PROGRAM:
## Developed By : MALARVIZHI G
## Reg No : 212222040096
```import socket
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
```

## SERVER PROGRAME:

```
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())  
	s.send("Recieved".encode())
```


## CLIENT OUTPUT:
![ex01 client output](https://github.com/22008650/19CS406-EX-1/assets/122548204/149ef68d-b811-4dd6-95c3-699209b11c71)
## SERVER OUTPUT:
![ex01 server output](https://github.com/22008650/19CS406-EX-1/assets/122548204/5f74b1c7-b48f-4b6a-a6bb-0f6e7e1fe78a)


## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.
