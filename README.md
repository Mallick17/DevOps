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

# Server-Side Website Programming
Server-side website programming refers to the process of handling and processing user requests on a web server before sending a response back to the web browser. This involves using various programming languages and frameworks to create dynamic web pages that can interact with databases and perform complex operations.

### Static vs. Dynamic Web Servers
- **Static Web Server**:
  - Consists of a computer (hardware) with an HTTP server (software).
  - Sends files "as-is" to the browser.
  - Ideal for simple websites with fixed content.
  - **Static Content**
    - **Definition**: Files served "as-is" without modification.
    - **Use Case**: Simple websites with fixed content.
    - **Advantages**: Easy to set up and maintain.
  - The server retrieves the requested document from its file system and returns an HTTP response containing the document and a success status (usually 200 OK). If the file cannot be retrieved for some reason, an error status is returned.
   ![basic_static_app_server](https://github.com/user-attachments/assets/fc8caff8-c600-47c1-9075-cf573488c706)

- **Dynamic Web Server**:
  - Includes a static web server plus additional software (e.g., an application server and a database).
  - Generates content dynamically before sending it to the browser.
  - Used for complex websites like MDN or Wikipedia, where content is pulled from databases and templates.
  - Most of the code to support a dynamic website must run on the server. Creating this code is known as **"server-side programming"** (or sometimes **"back-end scripting"**).
  - **Dynamic Content**
    - **Definition**: Content generated or processed by the server before being sent to the client.
    - **Use Case**: Complex websites with frequently updated content (e.g., blogs, e-commerce sites).
    - **Advantages**: Greater flexibility and scalability.
    - **Challenges**: Requires a more complex technical stack (e.g., application servers, databases).
  - Requests for dynamic resources are instead forwarded (2) to server-side code (shown in the diagram as a Web Application). For "dynamic requests" the server interprets the request, reads required information from the database (3), combines the retrieved data with HTML templates (4), and sends back a response containing the generated HTML (5,6).
    ![web_application_with_html_and_steps](https://github.com/user-attachments/assets/031ac80a-c742-4109-9008-c8e4b014f4bc)

## Are server-side and client-side programming the same?
| **Aspect**                  | **Client-Side Programming**                                                                 | **Server-Side Programming**                                                                 |
|-----------------------------|--------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------|
| **Purpose**                 | Improves appearance and behavior of a rendered web page.                                   | Handles which content is returned to the browser in response to requests.                  |
| **Main Concerns**           | UI components, layouts, navigation, form validation, etc.                                  | Data validation, database interactions, sending correct data to the client.                |
| **Programming Languages**   | HTML, CSS, JavaScript.                                                                     | PHP, Python, Ruby, C#, JavaScript (NodeJS), etc.                                           |
| **Execution Environment**   | Runs inside a web browser.                                                                 | Runs on a server operating system.                                                         |
| **Access to OS**            | Limited or no access to the underlying operating system (e.g., restricted file system access). | Full access to the server operating system.                                                |
| **Browser Compatibility**   | Must handle inconsistencies in browser support for features.                               | Not applicable (developer controls the server environment).                                |
| **Frameworks**              | Simplifies layout and presentation tasks (e.g., React, Angular, Vue).                      | Provides common web server functionality (e.g., Django, Flask, Express).                   |
| **Development Speed**       | Can write code by hand for small, simple UIs; frameworks speed up development for complex UIs. | Almost always uses frameworks to avoid reinventing core functionality (e.g., HTTP servers). |
| **Example Tasks**           | Styling, animations, form validation, client-side routing.                                 | Database operations, user authentication, server-side rendering, API endpoints.            |

### Key Notes:
1. **JavaScript Exception**: JavaScript is unique as it can be used for both client-side and server-side programming (via NodeJS).
2. **Frameworks**: 
   - Client-side frameworks focus on UI/UX (e.g., React, Angular).
   - Server-side frameworks focus on backend logic (e.g., Django, Express).
3. **Control**: 
   - Client-side code is limited by browser capabilities and user environment.
   - Server-side code is fully controlled by the developer, including language and version choices.

## Server-Side Programming: Uses and Examples  

### 1. **Efficient Storage and Delivery of Information**  
**Definition**: Server-side programming dynamically retrieves data from databases or external systems and generates tailored responses (HTML, JSON, etc.), eliminating the need for static pages. It ensures scalability, reduces redundancy, and enables real-time updates across platforms.  

**Example (Amazon)**:  
When a user searches for "laptops," the server queries a database, constructs a page with product details, and delivers it instantly. Users see a consistent layout with dynamically populated results, avoiding the impracticality of creating millions of static pages.  


### 2. **Customized User Experience**  
**Definition**: Servers analyze user behavior, preferences, and history (e.g., location, past searches) to personalize content, enhancing relevance and engagement.  

**Example (Google)**:  
After searching for "football," typing "favorite" triggers autocomplete suggestions like "favorite football teams." The server uses your search history to predict queries, streamlining the experience.  


### 3. **Controlled Access to Content**  
**Definition**: Server-side code enforces authentication and authorization rules, ensuring users only access permitted data (e.g., private accounts, sensitive transactions).  

**Example (Online Banking)**:  
When you log in, the server verifies credentials and grants access to your account dashboard. You can view balances or transfer funds, but others’ data and admin functions remain restricted.  


### 4. **Store Session/State Information**  
**Definition**: Servers track user interactions via sessions (stored in cookies or databases) to maintain state, such as login status or shopping cart items.  

**Example (Subscription Sites)**:  
News platforms like *The New York Times* track free articles viewed. After a limit, the server redirects users to a paywall, preserving subscription rules across browsing sessions.  


### 5. **Notifications and Communication**  
**Definition**: Servers trigger automated alerts (emails, SMS) based on user actions or system events, keeping users informed and engaged.  

**Example (Amazon Recommendations)**:  
After browsing shoes, the server sends an email like, “Similar to your recent view: Nike Air Max.” This targets user interests to drive repeat visits.  


### 6. **Data Analysis**  
**Definition**: Servers process user data (searches, purchases, clicks) to derive insights, optimize content, and predict trends.  

**Example (Facebook Feed)**:  
The server prioritizes posts with high engagement (likes, shares) in your feed. A viral meme appears above newer but less-active posts, ensuring you see popular content first.  

---

