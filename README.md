# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
    <title>Top five Revenue Generating Software Companies</title>
  <body>
      <table border="1"cellspacing="5"cellpadding="3">
        <caption>Top five Revenue Generating Software Companies
        </caption>
        <tr>
            <th>S.NO</th>
            <th>Company</th>
            <th>Revenue</th>
        </tr>
        <tr>
            <td>1</td>
            <td>Microsoft</td>
            <td>65 Billion</td>
        </tr>
        <tr>
            <td>2</td>
            <td>Oracle</td>
            <td>29.6 Billion</td>
        </tr>
        <tr>
            <td>3</td>
            <td>IBM</td>
            <td>29.1 Billion</td>
        </tr>
        <tr>
            <td>4</td>
            <td>SAP</td>
            <td>6.4 Billion</td>
        </tr>
        <tr>
            <td>5</td>
            <td>Symantec</td>
            <td>5.7 Billion</td>
        </tr>
    </table>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:
![Alt text](<../WhatsApp Image 2023-11-07 at 18.03.34_19975f8f.jpg>)
![Alt text](<../Screenshot (15).png>)
## RESULT:
The program for implementing simple webserver is executed successfully.
