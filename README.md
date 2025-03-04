# **Complete HTTP Notes**  

## **1. What is HTTP?**  
HTTP (**Hypertext Transfer Protocol**) is the foundation of data communication on the web. It defines how **clients (browsers)** and **servers** communicate.  

### **Key Terminologies**  
- **URL (Uniform Resource Locator):** The address of a web resource.  
- **URI (Uniform Resource Identifier):** Identifies a resource but doesn't always provide a means to locate it.  
- **URN (Uniform Resource Name):** A unique name for a resource, independent of its location.  

---

## **2. HTTP Methods**  
HTTP methods define the type of operations that a client can perform on a server.  

| **Method**  | **Description** | **Example Usage** |
|------------|---------------|----------------|
| **GET**    | Retrieves a resource. | `GET /index.html` |
| **HEAD**   | Similar to GET but without the response body (used for metadata retrieval). | `HEAD /index.html` |
| **OPTIONS** | Checks available HTTP methods for a resource. | `OPTIONS /api/users` |
| **TRACE**  | Debugging tool to trace request routing. | `TRACE /debug` |
| **DELETE** | Removes a resource. | `DELETE /user/123` |
| **PUT**    | Replaces an entire resource. | `PUT /user/123` |
| **POST**   | Creates a new resource. | `POST /user` |
| **PATCH**  | Updates part of a resource. | `PATCH /user/123` |

---

## **3. HTTP Status Codes**  
HTTP responses include **status codes** that indicate the result of a request.  

| **Category** | **Meaning** | **Examples** |
|-------------|------------|-------------|
| **1XX** | Informational | `100 Continue`, `101 Switching Protocols` |
| **2XX** | Success | `200 OK`, `201 Created`, `204 No Content` |
| **3XX** | Redirection | `301 Moved Permanently`, `302 Found`, `304 Not Modified` |
| **4XX** | Client Error | `400 Bad Request`, `401 Unauthorized`, `403 Forbidden`, `404 Not Found` |
| **5XX** | Server Error | `500 Internal Server Error`, `502 Bad Gateway`, `504 Gateway Timeout` |

---

## **4. What Are HTTP Headers?**  
HTTP headers are **key-value pairs** sent along with requests and responses to provide metadata about the communication.  
They help in **content negotiation, authentication, caching, session management, and security**.  

**Example HTTP Request with Headers:**  
```http
GET /index.html HTTP/1.1
Host: www.example.com
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
Accept: text/html
```

---

## **5. Types of HTTP Headers**  

HTTP headers are categorized into different types based on their functionality:  

### **5.1. Request Headers**  
Sent by the client (browser or application) to provide information about the request.  
Used to define what data the client needs, authentication, and user preferences.  

#### **Examples:**  

- **User-Agent:** Identifies the client making the request.  
  ```http
  User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)
  ```
  - This tells the server that the request is coming from a Windows 10 computer using a **64-bit Chrome browser**.  
  - The server can use this information to serve different content for different browsers/devices.  

- **Accept:** Specifies the media type the client expects in the response.  
  ```http
  Accept: application/json
  ```
  - This tells the server that the client wants data in **JSON format** instead of HTML.  

- **Authorization:** Used for authentication. Commonly used with **Bearer tokens** for APIs.  
  ```http
  Authorization: Bearer <your_JWT_token_here>
  ```
  - This allows secure authentication using **JWT (JSON Web Token)**.  

- **Referer:** Indicates the page the request came from.  
  ```http
  Referer: https://www.google.com/
  ```
  - This helps in analytics and security to **track where requests originate from**.  

---

### **5.2. Response Headers**  
Sent by the server in response to a client request. These headers provide information about the server and how the response should be handled.  

#### **Examples:**  

- **Content-Type:** Specifies the format of the response body.  
  ```http
  Content-Type: application/json
  ```
  - This tells the client that the server is responding with **JSON data**.  
  - If it's an HTML page, it will be:  
    ```http
    Content-Type: text/html
    ```  

- **Set-Cookie:** Sends a cookie from the server to the client.  
  ```http
  Set-Cookie: sessionId=abc123; Path=/; HttpOnly
  ```
  - This sets a session cookie that the browser will send with future requests.  

- **Server:** Provides information about the server software.  
  ```http
  Server: Apache/2.4.41 (Ubuntu)
  ```
  - This tells the client that the website is hosted on an **Apache server running on Ubuntu**.  

---

### **5.3. Representation Headers**  
Define how the content is represented, including **encoding, language, and caching**.  

#### **Examples:**  

- **Content-Encoding:** Specifies the compression algorithm used to reduce the response size.  
  ```http
  Content-Encoding: gzip
  ```
  - This tells the client that the response body is compressed using **Gzip**, improving load times.  

- **Content-Language:** Specifies the language of the response content.  
  ```http
  Content-Language: en-US
  ```
  - This indicates that the response is in **English (United States)**.  

- **ETag:** Used for caching and detecting changes in a resource.  
  ```http
  ETag: "34a64df551429ccd"
  ```
  - Helps browsers avoid downloading unchanged files, improving **performance**.  

---

### **5.4. Payload Headers**  
These headers provide additional information about the request or response **body (payload)**, such as its length or type.  

#### **Examples:**  

- **Content-Length:** Specifies the size of the response body in bytes.  
  ```http
  Content-Length: 3495
  ```
  - This tells the client that the response body is **3,495 bytes long**.  

- **Content-Disposition:** Used to instruct the browser how to handle the response content.  
  ```http
  Content-Disposition: attachment; filename="file.pdf"
  ```
  - This tells the browser to **download the file as an attachment** instead of displaying it in the browser.  

---

## **Common HTTP Headers and Their Uses**  

| **Header Name**   | **Description** | **Example** |
|-------------------|---------------|------------|
| **User-Agent**    | Identifies the client making the request. | `User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)` |
| **Accept**        | Specifies the content type the client expects. | `Accept: application/json` |
| **Authorization** | Used for authentication (JWT, Basic Auth, etc.). | `Authorization: Bearer <token>` |
| **Content-Type**  | Defines the format of the request/response body. | `Content-Type: application/json` |
| **Cookie**        | Stores session data. | `Cookie: sessionId=xyz123; Path=/` |
| **Cache-Control** | Controls caching behavior. | `Cache-Control: no-cache, max-age=3600` |
| **Referer**       | Specifies the source of the request. | `Referer: https://www.example.com/` |
| **ETag**         | Used for versioning and caching. | `ETag: "abcdef123456"` |

---

## **How HTTP Headers Help in Authentication & Caching?**  

### 🔒 **Authentication Headers:**  
- Used to handle **user logins, guest users, and session management**.  
- Examples: `Authorization`, `Set-Cookie`.  
- Example for **Basic Authentication** (Base64 encoded credentials):  
  ```http
  Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=
  ```

### ⚡ **Caching Headers:**  
- Used to **store resources** in the browser or proxy caches to reduce server load.  
- Examples: `Cache-Control`, `ETag`.  
- Example for **no caching**:  
  ```http
  Cache-Control: no-cache, no-store, must-revalidate
  ```

---

## **Deprecated Headers (X-Prefix Headers)**  
❌ **Headers with the "X-" prefix were deprecated in 2012.**  
- Older custom headers used `"X-"` as a prefix (e.g., `X-Powered-By`).  
- New standards avoid `"X-"` in favor of more meaningful names.  
- Example of a deprecated header:  
  ```http
  X-Frame-Options: DENY
  ```

---


## **6. CORS (Cross-Origin Resource Sharing) & Security Headers**  
CORS and security headers help in **controlling access** and **preventing attacks**.  

### **🔹 CORS Headers** (Used for cross-origin access control)  

| **Header** | **Description** | **Example** |
|-----------|---------------|------------|
| **Access-Control-Allow-Origin** | Specifies which origins can access the resource. | `Access-Control-Allow-Origin: *` |
| **Access-Control-Allow-Methods** | Lists allowed HTTP methods. | `Access-Control-Allow-Methods: GET, POST` |
| **Access-Control-Allow-Headers** | Specifies which headers can be used. | `Access-Control-Allow-Headers: Content-Type` |

### **🔹 Security Headers**  

| **Header** | **Description** | **Example** |
|-----------|---------------|------------|
| **Strict-Transport-Security** | Enforces HTTPS. | `Strict-Transport-Security: max-age=31536000; includeSubDomains` |
| **X-Content-Type-Options** | Prevents MIME-type sniffing. | `X-Content-Type-Options: nosniff` |
| **X-Frame-Options** | Prevents clickjacking. | `X-Frame-Options: DENY` |
| **X-XSS-Protection** | Prevents reflected XSS attacks. | `X-XSS-Protection: 1; mode=block` |
| **Content-Security-Policy** | Restricts scripts and resources. | `Content-Security-Policy: default-src 'self'` |

---

## **7. Common HTTP Headers & Their Uses**  

| **Header** | **Type** | **Description** | **Example** |
|-----------|---------|---------------|------------|
| **User-Agent** | Request | Identifies the client (browser, OS). | `User-Agent: Mozilla/5.0` |
| **Accept** | Request | Specifies accepted response formats. | `Accept: application/json` |
| **Authorization** | Request | Handles authentication. | `Authorization: Bearer <token>` |
| **Referer** | Request | Indicates the request source. | `Referer: https://google.com` |
| **Content-Type** | Response | Defines response format. | `Content-Type: text/html` |
| **Set-Cookie** | Response | Sends cookies to the client. | `Set-Cookie: sessionId=xyz123; Path=/` |
| **Cache-Control** | Both | Controls caching behavior. | `Cache-Control: no-cache` |
| **ETag** | Response | Helps with caching. | `ETag: "abcdef123456"` |

---

## **8. Authentication & Caching in HTTP Headers**  

### **🔐 Authentication Headers**  
Used for managing **logged-in users, session tokens, and credentials**.  
- Example for **Basic Authentication**:  
  ```http
  Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=
  ```

### **⚡ Caching Headers**  
Help store responses **in the browser or CDN to reduce load times**.  
- Example for **no caching**:  
  ```http
  Cache-Control: no-cache, no-store, must-revalidate
  ```

---

## **9. Deprecated Headers (X-Prefix Headers)**  
🚫 **Headers with the "X-" prefix were deprecated in 2012.**  
- Older headers used `"X-"` (e.g., `X-Powered-By`), but newer headers avoid this.  
- Example of a **deprecated header**:  
  ```http
  X-Frame-Options: DENY
  ```

---

## **Conclusion**  
Understanding HTTP headers is **crucial for web security, API communication, and optimization**.  
✅ **Proper authentication headers** improve security.  
✅ **Caching headers** enhance performance.  
✅ **CORS & security headers** protect against attacks.  
