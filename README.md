# Developing a Simple Webserver

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>NAME:Django</h1>
<h2>This is Web Application Framework written in python</h2>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
## Server side output:
![2](https://user-images.githubusercontent.com/119405017/210164847-d46c32ad-e735-4037-a493-934270b19037.png)
## Client side output:
![1out](https://user-images.githubusercontent.com/119405017/210164852-593a3a6b-f865-4f42-9662-9edf5ab83f8f.png)


## RESULT:
The program is executed succesfully
