cAdmin-Server
=============

InterSystems Caché Administration Mobile tool - Server side. Bundled with project https://github.com/ShmidtIvan/cAdmin.
  
<b>Installation guide</b><br>
1.	Create new Namespace cAdmin with new database cAdmin with new access resource %DB_cAdmin<br>
2.	Into your new namespace cAdmin mirror package SYS from database CACHESYS<br>
3.	Create new resource %cAdmin with public USE on<br>
4.	Create new role cAdminRole, containing %cAdmin resource (step 3) and %Admin_Manage resource<br>
5.	Import all Cache classes from this repository https://github.com/eduard93/cAdmin-Server/ Either download zip or clone git<br>
6.	In cAdmin.WebSocket class modify resource parameter to match %cAdmin resource<br>
7.	Compile all classes<br>
8.	Create new user cAdminUser with roles %DB_cAdmin (step 1), cAdminRole (step 4) and %Admin_Manage role<br>
9.	For user cAdminUser on tab SQL Tables add access to Select and Delete  for table cAdmin_data.CconsoleLog from cAdmin namespace <br>

<b>Use (JavaScript)</b><br>
ws = new WebSocket("ws://<server ip>:<server port>/csp/<Namespace> /cAdmin.WebSocket.cls");<br>
ws.onopen = function(){ ws.send(JSON.stringify({User:" cAdminUser ",Password:" cAdminUserPassword"}))}; <br>
ws.onmessage = function(m){console.log(m)};<br>
ws.send(‘devtools:RandomNumber’);<br>

In this example we, first, create new websocket object and point it to our websocket.<br>
Next, we specify what to send to server after establishing the connection – JSON, containing authorization information.<br>
After this use ws.send to send requests from request map <br>
Use ws.readyState to check that WebSocket is working<br>

<b>Notes</b><br>
Please refer to included Caché documentation and manual.pdf for further information.
