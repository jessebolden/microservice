# microservice
----------------------------------------------------------------------------------
Requesting data:
1. Connect to socket
2. Send json request including an action(either "get_leaderboard" or "add_entry").
   Add entry request must include a name, score, and desc.

Example call:
client_socket.sendall([REQUEST GOES HERE].encode('utf-8'))

Example requests:
{"action": "get_leaderboard"}

{"action": "add_entry",
 "data": { "name": "Katie",
           "score": 7025,
           "desc": "Got lost in an Ikea"}

----------------------------------------------------------------------------------
Recieving data:
1. Connect to socket and send request
2. Receive response(will be json data)

Example call:
response = client_socket.recv(1024).decode('utf-8')

Example responses:
{"entries":[LEADERBOARD ENTRIES]}

{"status":"Score added"}

{"status":"Insufficient score"}

![image](https://github.com/user-attachments/assets/fc72b221-f80c-4531-919a-0203ac2ba39f)
