# Networking
- Network is a system where two or more devices are linked together to share data, resources, and information. These networks can range from simple setups, like connecting two devices in your home, to massive global systems, like the Internet.
- They allow devices like computers, smartphones, and tablets to connect and communicate with each other. Whether you’re browsing the internet, sending an email, or streaming a video, it all happens because of computer networks.

## OSI Model
- The **OSI (Open Systems Interconnection)** Model is a set of rules that explains how different computer systems communicate over a network. OSI Model was developed by the **International Organization for Standardization (ISO)**. The OSI Model consists of 7 layers and each layer has specific functions and responsibilities. This layered approach makes it easier for different devices and technologies to work together. OSI Model provides a clear structure for data transmission and managing network issues. The OSI Model is widely used as a reference to understand how network systems function.
![osi_model_7_layers](https://github.com/user-attachments/assets/72f04348-c9ef-49ec-84d7-7e867e7af0f5)

### **Breaking Down the OSI Model**
#### **1. Physical Layer (Layer 1)**
- The Physical Layer is all about the hardware that makes up a network, like cables and routers. It handles sending and receiving data.
- For example, when you plug an Ethernet cable (network cable) to connect your computer to a router. So this Physical Layer is responsible for sending and receiving data over the network using this hardware.
  - Converts data into raw **bits (0s and 1s)**.
  - Transmits bits over physical mediums like **cables, fiber optics, or Ethernet, Wi-Fi, Bluetooth**.

#### **2. Data Link Layer (Layer 2)**
- This layer takes the data from the Physical Layer and breaks it into smaller pieces called “frames.” It’s also responsible for making sure that the frames are delivered to the right place.
- For example, if you want to send an email to a friend, the Data Link Layer will break the message into smaller pieces and send them to the router, which will then send them to your friend’s computer.
  - Organizes raw bits into **frames**.
  - Uses **MAC (Media Access Control) addresses** to ensure data reaches the correct device.
  - **Ethernet, LLC (Logical Link Control) and VLANs** operate here.

#### **3. Network Layer (Layer 3)**
- This layer is in charge of routing the frames to their destination. It does this by using something called an “IP address,” which is a unique number that identifies each device on the internet.
- For example, when you type in a URL in your web browser, the Network Layer will use the website’s IP address to route the request to the correct server.
  - Handles **IP addressing** and **routing** across different networks.
  - Uses **IP headers** to determine the source and destination IP addresses.
  - **IP (Internet Protocol), ICMP (Internet Control Message Protocol), ARP (Address Resolution Protocol),and IPSec** are key protocols.

#### **4. Transport Layer (Layer 4)**
- This layer is responsible for ensuring that the data is delivered reliably from one device to another. It does this by adding something called a “checksum” to the data, which helps to detect any errors that might occur during transmission. 
- For example, when you’re streaming a video on YouTube, the Transport Layer will make sure that the video is delivered smoothly to your device by adding checksums to each chunk of the video.
- For example, if you’re downloading a large file from the internet, the Transport Layer will make sure that all of the data is transferred correctly by adding checksums to each piece of the file.
  - Ensures end-to-end communication between devices.
  - Uses **TCP (Transmission Control Protocol) and UDP (User Datagram Protocol)**.
  - **TCP (Transmission Control Protocol)** is **reliable** (checks for errors, reorders packets).  
  - **UDP (User Datagram Protocol)** is **faster but less reliable** (sends data without error checking).

#### **5. Session Layer (Layer 5)**
- This layer is responsible for setting up, maintaining, and terminating connections between devices. It helps to keep track of which devices are talking to each other and when.
- For example, if you start a video call with a friend, the Session Layer will set up a connection between your devices and keep track of the call as it’s happening.
- For example, when you make a phone call, the Session Layer will set up a connection between your phone and the other person’s phone, and then maintain the connection until the call is ended.
  - Manages **sessions** between applications using SSH (Secure Shell), SSL (Secure Sockets Layer) (e.g., logging into a website).
  - Handles opening, closing, and maintaining communication sessions.

#### **6. Presentation Layer (Layer 6)**
- This layer is responsible for translating the data into a form that can be understood by the devices on either end of the connection. It also helps to compress and decompress the data to make it more efficient.
- For example, if you’re sending a photo to a friend, the Presentation Layer will convert the photo into a format that can be sent over the internet and then decompress it on the other end so that your friend can view it.
- For example, when you upload a photo to Instagram, the Presentation Layer will compress the photo to make it smaller and easier to send over the internet, and then decompress it on the server so that it can be stored and displayed to other users.
  - Converts data into a format like  ASCII (American Standard Code for Information Interchange), JPEG (Joint Photographic Experts Group) that applications can understand which translates data between the application layer and the network format.
  - Deals with **encryption, compression, and encoding**.

#### **7. Application Layer (Layer 7)**
- This is the top layer of the OSI Model and it’s the one that users interact with. It includes things like web browsers, email clients, and other software that allow people to access and use the internet.
- For example, if you want to send an email, you would use an email client (like Microsoft Outlook or Gmail) at the Application Layer to create and send the message.
- For example, when you log into your email account, you are using the Application Layer to access and use the email service.
  - Provides **interfaces for users and applications** to communicate over a network.
  - Protocols include **HTTP, HTTPS, FTP, SMTP, DNS**.

---
