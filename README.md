## **What is a Web Server?**
A **web server** is a computer that stores and delivers the files for one or more **websites**. When you type a URL into your browser, the web server sends the requested web page files to your browser so you can view them.

**Important Note**: Don’t confuse **websites** with **web servers**. A web server can host multiple websites. For example, if someone says, "My website is not responding," it usually means the web server hosting the website is having issues, making the website unavailable.

---

## Web Server(Explained)
A **web server** is a system that hosts and delivers web content to users over the internet. It can refer to both the hardware and software components that work together to serve web pages and other resources to clients (typically web browsers).

### Components of a Web Server

1. **Hardware**
- A web server, on the hardware side, is a computer that stores:
  - **Web server software** (e.g., Apache, Nginx).
  - **Website files** (e.g., HTML documents, images, CSS stylesheets, JavaScript files, fonts, and videos).
- The hardware connects to the internet and facilitates data exchange with other devices.

2. **Software**
- The software side of a web server includes:
  - An **HTTP server**: Software that understands **URLs** (web addresses) and **HTTP** (the protocol used by browsers to request and display web pages).
  - Additional components for dynamic web servers, such as:
    - **Application servers**: Software that processes and generates dynamic content.
    - **Databases**: Stores data used to generate dynamic content.

### What is HTTP?
- HTTP is a **textual, stateless protocol** used for transferring hypertext (linked web documents) between clients and servers.
  - **Textual**: Commands are plain-text and human-readable.
  - **Stateless**: Neither the server nor the client retains information about previous interactions.

### How a Web Server Works
- **Basic Workflow of HTTP**
1. **Request**: A client(browser) sends an HTTP request for a file hosted on the web server.
2. **Processing**: The HTTP server receives the request, locates the file, and processes it (if necessary).
3. **Response**: The server sends the file back to the browser via HTTP. If the file is not found, the server returns a **404 error**.
![webserver-http](https://github.com/user-attachments/assets/c3f41f1c-0c06-4907-a3ce-2f98f8df0514)


