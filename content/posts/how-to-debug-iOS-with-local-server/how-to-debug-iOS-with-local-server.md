---
title: "How to debug iOS with local server"
date: 2023-06-29T14:27:48+01:00
---

When you need to test interactions within your app that require a custom web page, such as engaging with payment options in a pop-up browser via universal links or deep links, the process might seem daunting at first. However, with the right approach, it becomes manageable and straightforward.

Like in the screenshot below:

![Deeplinks menu](/posts/how-to-debug-iOS-with-local-server/deeplinks_menu.png)

Recently, I encountered a task that required testing payment interactions on a web page within a pop-up browser. The first step was to capture the link, modify it by removing and adding certain parameters, and then proceed. The second step involved opening the web page and handling a deep link from it, which would close the pop-up browser.

To ensure everything worked as intended, I needed a webpage that could handle all types of links and that could be opened in iOS Simulator. First idea that came to my mind is using a local server with such page. After a quick search, I found a simple code using Python, which was perfect for my needs. This code allows you to set up a local server and test various links in an HTML format:
****
```python
from http.server import HTTPServer, BaseHTTPRequestHandler

class Serv(BaseHTTPRequestHandler):
****
    def do_GET(self):
       if self.path == '/':
           self.path = '/test.html'
       try:
           file_to_open = open(self.path[1:]).read()
           self.send_response(200)
       except:
           file_to_open = "File not found"
           self.send_response(404)
       self.end_headers()
       self.wfile.write(bytes(file_to_open, 'utf-8'))

httpd = HTTPServer(('localhost',8081),Serv)
httpd.serve_forever()
```

To use this server, you simply place any links you need in HTML format in a file named `test.html` and save it. Then, run the server using the command `python your-python-saved-name.py`.

The line before the last one in the script allows you to configure the local host and its port, which is set to `8081` by default. If this port is busy, you can easily switch to another, such as `8082`.

This method provides a straightforward way to test web interactions within your app, saving tons of time during compiling or debugging of your app.

---

Hey everyone,

Getting into app debugging with web pages? I’ve just tackled testing a payment webpage that pops up in an app. The goal was to grab the URL, adjust the parameters, and make sure the deep links worked smoothly before closing the browser.

![[deeplinks_menu.png]]

To get it right, I set up a simple local server using Python:

```python
from http.server import HTTPServer, BaseHTTPRequestHandler

class Serv(BaseHTTPRequestHandler):

    def do_GET(self):
       if self.path == '/':
           self.path = '/test.html'
       try:
           file_to_open = open(self.path[1:]).read()
           self.send_response(200)
       except:
           file_to_open = "File not found"
           self.send_response(404)
       self.end_headers()
       self.wfile.write(bytes(file_to_open, 'utf-8'))

httpd = HTTPServer(('localhost',8081),Serv)
httpd.serve_forever()
```

Place your content into test.html, save this script, and run it with python your-file-name.py. Choose localhost and a free port, like 8081, and you’re good to go.

Now you’re ready to seamlessly test all those links between your app and the web!

