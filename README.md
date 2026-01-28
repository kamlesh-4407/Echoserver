# Echoserver
Echo server and client using python socket
# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

HTML content creation is done

### Step 2:

Design of webserver workflow

### Step 3:

Implementation using Python code

### Step 4:

Serving the HTML pages.

### Step 5:

Testing the webserver

## PROGRAM:
```python
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
<head>
<title> My Web Server</title>
</head>
<body>
<h1>Top Five Web Application Development Frameworks</h1>
<h2>1.Django</h2>
<h2>2. MEAN Stack</h2>
<h2>3. React </h2>
</body>
</html>'''


class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('keerthi',2323)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
##  Architecture Diagram

```bash
+--------------------------+
|  User's Web Browser      |
|  (Client: Chrome/Firefox)|
+-----------+--------------+
            |
            |  HTTP Request (GET /)
            v
+-----------+--------------+
|   Python Web Server      |
| (http.server + Handler)  |
| - Listens on Port 8000   |
| - Handles GET Requests   |
| - Sends HTML Response    |
+-----------+--------------+
            |
            |  HTML Response
            v
+--------------------------+
|  User Sees Rendered Page |
|  <h1>Hello Web Server</h1>|
+--------------------------+
```


## OUTPUT:
### SERVER OUTPUT:
#### Code 
<img width="806" height="452" alt="image" src="https://github.com/user-attachments/assets/7aea82c0-929c-448e-8a71-8d122eb46686" />

#### Output
<img width="494" height="126" alt="image" src="https://github.com/user-attachments/assets/270aa6e2-51e6-4157-8641-4845aca015ba" />

### CLIENT OUTPUT:
#### Code 
<img width="803" height="411" alt="image" src="https://github.com/user-attachments/assets/10c35c1d-880f-4e73-9c83-0600ead40a81" />

#### Output
<img width="828" height="122" alt="image" src="https://github.com/user-attachments/assets/ab67ae34-bee0-453d-a461-da9fb29a772c" />

## RESULT:
The program is executed succesfully
