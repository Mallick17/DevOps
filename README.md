# DevOps
Concepts related to Development &amp; Operations.

## **What is a Web Page?**
A **web page** is a document that can be displayed in a web browser (like Chrome, Firefox, or Safari). It can include:
- **Text**: The main content of the page.
- **Style information**: Controls how the page looks (e.g., colors, fonts, layout).
- **Scripts**: Adds interactivity, like buttons that respond when clicked.
- **Media**: Images, videos, and audio.

Every web page has a unique address called a **URL** (Uniform Resource Locator). To view a web page, simply type its URL into your browser's address bar and press Enter.

---

## **What is a Website?**
A **website** is a collection of related **web pages** that share the same domain name (e.g., `www.example.com`). Websites are connected through **links**, which allow users to navigate from one page to another.

When you visit a website, the first page you usually see is called the **homepage**. This page often serves as the main entry point to the rest of the site.

---

## **What is a Web Server?**
A **web server** is a computer that stores and delivers the files for one or more **websites**. When you type a URL into your browser, the web server sends the requested web page files to your browser so you can view them.

**Important Note**: Don’t confuse **websites** with **web servers**. A web server can host multiple websites. For example, if someone says, "My website is not responding," it usually means the web server hosting the website is having issues, making the website unavailable.

---

## **What is a Search Engine?**
A **search engine** is a special type of website (like Google, Bing, or DuckDuckGo) that helps you find web pages from other websites. It works by indexing billions of web pages and allowing you to search for specific information.

**Common Confusion**: Many people mix up **search engines** and **browsers**. Here’s the difference:
- A **browser** (e.g., Chrome, Firefox) is software that retrieves and displays web pages.
- A **search engine** is a website that helps you find web pages.

For example, when you open a browser, it might show a search engine's homepage (like Google) or a search bar. This is why the two are often confused.

---
## **How Does the Web Work?**
When you use the web, a lot happens behind the scenes to deliver the content you see. Here’s a simplified breakdown:

1. **You Make a Request**:
   - You type a URL into your browser or click a link.
   - Your browser sends a request to the web server where the website is hosted.

2. **The Web Server Responds**:
   - The web server processes the request and sends the requested files (e.g., the web page, images, or videos) back to your browser.

3. **Your Browser Displays the Content**:
   - The browser receives the files and assembles them into the web page you see.
   - If the web page includes additional resources (like images or scripts), the browser will make more requests to fetch those.

4. **You See the Result**:
   - Once all the files are loaded, the browser displays the complete web page.

This process uses a technology called **HTTP** (Hypertext Transfer Protocol), which defines how requests and responses are handled.

### **Example: Loading a Website**
Let’s say you visit `www.example.com`:
1. Your browser requests the main HTML file for the homepage from the web server.
2. The server sends the HTML file to your browser.
3. The browser reads the HTML file and finds instructions to load additional resources (e.g., images, styles, scripts).
4. The browser requests these resources from the server.
5. Once all resources are loaded, the browser displays the complete webpage.
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
