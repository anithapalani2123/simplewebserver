# Developing a Simple Webserver
## AIM:
To develop a simple webserver to display top five programming language

## DESIGN STEPS:
### Step 1: 
HTML content creation
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
<title>My Webserver</title>
</head>
<body>
<h1>Top 5 programming languages</h1>
<h2>1.python</h2>
Python is an interpreted high-level general-purpose programming language.It is used in web development, data science, creating software prototypes, and so on. Fortunately for beginners, Python has simple easy-to-use syntax. This makes Python an excellent language to learn to program for beginners.
<d1>
   <dt>Python applications include:</dt>
   <dd>Web Development.</dd>
   <dd>Game Development.</dd>
   <dd>Software Development.</dd>
   <dd>Artificial Intelligence.</dd>
</d1>
<h2>2.java</h2>
Java is a high-level, class-based, object-oriented programming language that is designed to have as few implementation dependencies as possible.Java is a popular programming language.  The syntax of Java is similar to C and C++, but has fewer low-level facilities than either of them.Java is used to develop mobile apps, web apps, desktop apps, games and much more.
<dl>
   <dt>Uses of Java include:</dt>
   <dd>Mobile app development.</dd>
   <dd>Desktop GUI applications.</dd>
   <dd>Gaming applications.</dd>
   <dd>IoT applications.</dd>
</dl>
<h2>3.C</h2>
C is a powerful general-purpose programming language. It can be used to develop software like operating systems, databases, compilers, and so on. C programming is an excellent language to learn to program for beginners.C helps you to understand the internal architecture of a computer, how computer stores and retrieves information.Opportunity to work on open source projects. Some of the largest open-source projects such as Linux kernel, Python interpreter, SQLite database, etc. are written in C programming.
<dl>
   <dt>Uses of C include:</dt>
   <dd>Operating System Development.</dd>
   <dd>Game Development.</dd> 
   <dd>Web Services.</dd>
   <dd>Network Devices.</dd>
</d2>
<h2>4.Javascript</h2>
JavaScript is the world's most popular programming language.JavaScript is the world's most popular programming language.JavaScript is easy to learn.JavaScript is high-level, often just-in-time compiled and multi-paradigm. It has dynamic typing, prototype-based object-orientation and first-class functions.
<dl>
   <dt>Appliacions of Javascript include:</dt>
   <dd>Web Applications.</dd>
   <dd>Server Applications.</dd>
   <dd>Mobile Apllications.</dd>
   <dd>Games Development</dd>
</dl>
<h2>5.C#</h2>
C# is a general-purpose, multi-paradigm programming language. C# encompasses static typing, strong typing, lexically scoped, imperative, declarative, functional, generic, object-oriented, and component-oriented programming disciplines.
<dl>
   <dt>Uses of C# include:</dt>
   <dd>Web Applications.</dd>
   <dd>Desktop Applications.</dd>
   <dd>Game Development.</dd>
   <dd>Web-based services.</dd>
</d1>


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
### CLIENT SIDE OUTPUT:
![CLIENTSIDEOUTPUT](./mywebserver1.png)
![CLIENTSIDEOUTPUT](./mywebserver2.png)


### SERVER SIDE OUTPUT:
![SERVERSIDEOUTPUT](./mywebserver3.png)
![SERVERSIDEOUTPUT](./mywebserver4.png)





## RESULT:
  Thus,a simple webserver is created to display top five programming languages .