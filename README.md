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

### **How Data Travels Through the OSI & TCP/IP Model (Example of an HTTP Request)**  
#### Key Difference of TCP/IP Model Compared to OSI Model
- Network Access Layer (Equivalent to OSI Layers 1 & 2)
  - Handles both physical transmission and framing of data for delivery.
  - OSI separates physical transmission and data framing, while TCP/IP combines them into one layer (Network Access).
  - The TCP/IP model is more practical and closely follows real-world networking implementations.
![OSI-vs-TCP](https://github.com/user-attachments/assets/5498ea21-5e75-4618-8349-08394bcf2a64)

**Data Flow Diagram**
![Screenshot 2025-02-26 121702](https://github.com/user-attachments/assets/01442827-24b7-4c79-be6d-9f80fc57a1f5)

#### **Step 1: Application Layer (Layer 7)**
- The **Application Layer** is where user-facing applications and protocols operate. It’s responsible for enabling communication between different applications across a network.
- **A user sends an HTTP request to access a webpage:**
- When a user types a URL in their browser (e.g., `www.example.com`), an **HTTP request** is generated by the browser. HTTP is a protocol used by web browsers to request and display web pages.

- **Example HTTP Request:**
    ```
    GET /index.html HTTP/1.1
    Host: www.example.com
    User-Agent: Mozilla/5.0
    Accept-Language: en-US,en;q=0.5
    ```
<details>
  <summary>Click to view detailed Breakdown of HTTP header</summary>
  
This is the **Application Layer**'s responsibility: to create a request that the **Transport Layer** can send over the network.

#### The **Application Layer** adds the relevant **protocol headers** to the data. Some of these headers include:

1. **HTTP Method**
   - **Example**: `GET`
     - This specifies the action to be performed (e.g., retrieving a page from the server).
  
2. **Resource**
   - **Example**: `/index.html`
     - This specifies the resource being requested from the server (e.g., a webpage).

3. **Protocol Version**
   - **Example**: `HTTP/1.1`
     - This indicates the version of the HTTP protocol being used.

4. **Host**
   - **Example**: `www.example.com`
     - This specifies the server's domain name or IP address to which the request is being sent.

5. **User-Agent**
   - **Example**: `Mozilla/5.0`
     - This identifies the client application (web browser) making the request.

6. **Other Headers**
   - Examples: `Accept-Language`, `Accept-Encoding`, `Connection`, etc.
     - These headers contain additional information about how the client prefers to receive data, which languages it supports, and whether the connection should be kept open or closed.

---

### **Breakdown of each HTTP header (for Application Layer)**:

1. **HTTP Method**
   - **Example**: `GET`
     - Specifies the action the client wants to perform, like retrieving or posting data. Other methods include `POST`, `PUT`, `DELETE`, etc.

2. **Resource**
   - **Example**: `/index.html`
     - Identifies which part of the website or resource the client is requesting from the server.

3. **Protocol Version**
   - **Example**: `HTTP/1.1`
     - Specifies the version of the protocol the client is using to communicate with the server.

4. **Host**
   - **Example**: `www.example.com`
     - The domain or IP address where the request is being sent.

5. **User-Agent**
   - **Example**: `Mozilla/5.0`
     - Identifies the software or application making the request. It helps the server know how to respond based on the client’s capabilities.

6. **Other Headers**
   - **Example**: `Accept-Language: en-US`
     - These headers tell the server additional preferences, such as which language the client prefers for the response.

---

### **Protocol Data Unit (PDU) at the Application Layer**:
At the **Application Layer**, the **PDU** is the **message** or **data** that is being sent. The **Application Layer** prepares this message by adding the necessary headers (e.g., HTTP, SMTP, FTP). 

Once the **Application Layer** prepares the message, it is passed down to the **Transport Layer**, which adds its own headers (e.g., TCP or UDP headers), breaking the data into smaller segments.

---

</details>

#### **Step 2: Transport Layer (Layer 4)**
- The data from the application layer is broken into smaller parts as per the MSS(Maximum Segment Size) of the network and the TCP header is added to the smaller parts.
- A **TCP header** includes the following
```ini
1. Source Port          ##  12345  
2. Destination Port     ##  80  
3. Flag bits            ##  DF, MF  
4. Sequence Number      ##  4567890123  
5. Checksum             ##  0x1A2B3C4D  
6. Options Field        ##  Max Segment Size: 1460, No-Operation
```

<details>
  <summary>Click to view detailed Breakdown of each SEGMENT</summary>

### Breakdown of each segment:

1. **Source Port**  
   - **Example**: `12345`  
     This represents the source port number, indicating which application on the sender's side is sending the data.

2. **Destination Port**  
   - **Example**: `80`  
     This represents the destination port number. Port 80 is commonly used for HTTP traffic.

3. **Flag bits**  
   - **Example**: `DF, MF`  
     Flag bits control the fragmentation of the segment. 
     - **DF** (Don't Fragment): Tells routers not to fragment the packet.
     - **MF** (More Fragments): Indicates more fragments of the same packet are coming.

4. **Sequence Number**  
   - **Example**: `4567890123`  
     This is a sequence number used to keep track of the ordering of segments in the TCP connection. It ensures that data is reassembled in the correct order at the destination.

5. **Checksum**  
   - **Example**: `0x1A2B3C4D`  
     The checksum is used for error checking to ensure the integrity of the data in the TCP segment. If any bit errors occur during transmission, the checksum will not match and the segment will be discarded.

6. **Options Field**  
   - **Example**: `Max Segment Size: 1460, No-Operation`  
     This field allows for various options such as the maximum segment size (MSS) or no-operation instructions for padding the segment.

These segments form the key parts of a TCP header and play crucial roles in establishing reliable data transmission.

</details>

- Source and Destination port are required because it tells in which PDU(Protocol Data Unit - the PDU is a segment (for TCP) or a datagram (for UDP)) is to be delivered in the receiver host. The checksum field of the TCP is calculated by taking into account the TCP header, data and IP pseudo-header. The Checksum ensures that correct data is sent and received. Thus, after all these processing the broken data packets are called Segments.
  
#### **Step 3: Network Layer (Layer 3)**
- The segments received from the Transport layer are further processed to form the Packets.
- The **IP header contains source, destination IP addresses and has many fields include the following**.
```ini
1. Source IP Address        ##  192.168.1.1
2. Destination IP Address   ##  10.0.0.5
3. TTL (Time to Live)       ##  64
4. Identification           ##  0x12345
5. Protocol Type            ##  6 (TCP)
6. Version (Protocol Version) ##  4 (IPv4)
7. Options                  ##  No-Option
```

<details>
  <summary>Click to view detailed Breakdown of each PACKETS field</summary>

### Breakdown of each segment:

1. **Source IP Address**  
   - **Example**: `192.168.1.1`  
     This is the IP address of the sender (the source of the packet).

2. **Destination IP Address**  
   - **Example**: `10.0.0.5`  
     This is the IP address of the recipient (the destination of the packet).

3. **TTL (Time to Live)**  
   - **Example**: `64`  
     TTL is a field used to limit the lifetime of the packet. It specifies the number of hops (routers) the packet is allowed to pass through before being discarded. Each router that processes the packet decrements this value by 1. If TTL reaches 0, the packet is dropped. 

4. **Identification**  
   - **Example**: `0x12345`  
     This value is used to uniquely identify fragments of a larger IP packet. When a packet is fragmented, the identification value helps the receiver reassemble the fragments into the correct order.

5. **Protocol Type**  
   - **Example**: `6`  
     This indicates the protocol used in the data portion of the IP packet. For example:
     - `6` means **TCP** (Transmission Control Protocol).
     - `17` means **UDP** (User Datagram Protocol).
     - `1` means **ICMP** (Internet Control Message Protocol).

6. **Version (Protocol Version)**  
   - **Example**: `4`  
     This specifies the IP protocol version being used. For IPv4, this is `4`, and for IPv6, it would be `6`.

7. **Options**  
   - **Example**: `No-Option`  
     The options field allows for additional features or controls in the IP header (like security, routing, or timestamp options). If no options are used, it might be empty, or the field might be marked as "No-Option".

These segments are part of the **IP header** and help ensure the proper delivery and handling of IP packets across networks.

- When data is sent over a network, the **IP body** contains the actual **segment** that was received from the **Transport Layer** (like a TCP segment). This segment is not changed in any way by the IP layer.

However, the **IP header** is added to this body. The IP header contains important information like:
- **Source and Destination IP addresses**
- **TTL (Time to Live)**, which decreases every time the packet passes through a router
- **Protocol Type** (whether it’s TCP, UDP, etc.)

As the packet travels through the network, the IP header is updated, especially the **TTL**, which changes each time the packet goes through a router (or hop). 

Together, the **IP header** and the **body** (which contains the segment) form the **IP packet**. 

The **IP layer** also handles **fragmentation**. If a packet is too large to travel through a network (because of the **Maximum Transmission Unit** or MTU), it is broken into smaller pieces at the **routers** along the way. These pieces are called fragments, and they can be reassembled at the destination.

</details>

#### **Step 4: Data Link Layer (Layer 2)**
- The packet(IP datagram) is wrapped with a **MAC header**.
- The Packets received from the Network Layer further processed to form the Frames.
- The **MAC header contains source, destination MAC addresses as mentioned below with few other segments**.
```ini
1. Source MAC Address      ##  00:1A:2B:3C:4D:5E
2. Destination MAC Address ##  00:5E:4D:3C:2B:1A
3. Data                    ##  Hello, this is a test message.
4. Length                  ##  0x0014 (20 bytes)
5. Checksum (CRC)          ##  0xA1B2C3D4
```

<details>
  <summary>Click to view detailed Breakdown of each FRAME field</summary>

### Breakdown of each frame field:

1. **Source MAC Address**  
   - **Example**: `00:1A:2B:3C:4D:5E`  
     This is the **MAC address** of the device sending the frame. It is unique to each network interface card (NIC).

2. **Destination MAC Address**  
   - **Example**: `00:5E:4D:3C:2B:1A`  
     This is the **MAC address** of the device receiving the frame.

3. **Data**  
   - **Example**: `Hello, this is a test message.`  
     This is the actual **payload** or data being sent inside the frame.

4. **Length**  
   - **Example**: `0x0014` (20 bytes)  
     The **length** indicates the size of the data portion of the frame. In this case, it’s 20 bytes.

5. **Checksum (CRC)**  
   - **Example**: `0xA1B2C3D4`  
     The **checksum** or **CRC** (Cyclic Redundancy Check) is used to detect errors in the frame. If the checksum doesn’t match when the receiver checks it, the frame is discarded.

This is the basic structure of an **Ethernet frame**, which is used to transmit data on a local network. The frame ensures the data is correctly addressed, sized, and checked for errors.

</details>

- The source MAC address is resolved by using the ARP(Address Resolution Protocol). The Source and Destination MAC address would keep on modifying as the Frame moves in the network. The Modification of the MAC address is done by the Routers. Data is the segment that is received from the network layer. The length is the total MTU(maximum transferable unit) of the network. All concepts will be clear with the diagram given below.


#### **Step 5: Physical Layer (Layer 1)**
- Data is converted into **raw bits (0s and 1s)** and transmitted through the network.

#### **Step 6: Data Transmission Over the Internet**
- The data is sent **from the sender (Device A) to the receiver (Device B)**.
- It passes through **multiple routers**, with each router updating the **MAC addresses** for the next hop.

#### **Step 7: Data Reassembly at the Receiver**
- At **Device B**, the process is reversed:
  - **Physical Layer** receives raw bits. -- Physical Layer: Receives the raw bits.
  - **Data Link Layer** reads MAC addresses. -- Data Link Layer: Removes the MAC header.
  - **Network Layer** extracts the IP header. -- Network Layer: Removes the IP header.
  - **Transport Layer** reassembles TCP segments. -- Transport Layer: Removes the TCP header.
  - **Application Layer** processes the HTTP request. -- Application Layer: Processes the HTTP request.

---

#### TCP vs. UDP
- **TCP (Transmission Control Protocol)**:
  - **Reliability**: Provides reliable, error-checked communication.
  - **Process**: Divides data into segments, each with a sequence number for reassembly.
  - **Use Case**: Used when data integrity is crucial (e.g., web browsing, email).

- **UDP (User Datagram Protocol)**:
  - **Speed**: Faster and simpler than TCP.
  - **Reliability**: Does not provide error-checking or reliability.
  - **Use Case**: Used when speed is more important than reliability (e.g., video streaming, online gaming).

---

## OSI vs TCP/IP Model

| **Parameter**                     | **OSI Model**                                                                                                   | **TCP/IP Model**                                                                                             |
|------------------------------------|-----------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------|
| **Full form**                      | OSI stands for Open Systems Interconnection.                                                                    | TCP/IP stands for Transmission Control Protocol/Internet Protocol.                                          |
| **Definition**                     | It is a generic, protocol-independent standard that serves as a communication gateway between the network and the end-user. | This is a protocol-dependent model that allows the connection of hosts over a network.                      |
| **Number of layers**               | 1. Physical<br>2. Data Link<br>3. Network<br>4. Transport<br>5. Session<br>6. Presentation<br>7. Application       | 1. Network Access<br>2. Internet<br>3. Transport<br>4. Application                                           |
| **Reliability**                    | It is less reliable.                                                                                           | TCP/IP is more reliable.                                                                                     |
| **Protocol replacement**           | Protocols are easy to replace.                                                                                 | Protocols are not easy to replace.                                                                            |
| **Function**                        | It offers standardization to different hardware devices, such as routers and switches.                         | It provides a connection between various computers but does not provide standardization to hardware devices. |
| **Approach type**                  | Follows a vertical approach.                                                                                   | Follows a horizontal approach.                                                                                |
| **Data link and physical layer**   | The data link layer and physical layer are separate.                                                           | The data link and physical layers are combined as a single host-to-network layer.                           |
| **Service type**                   | In the OSI model, the network layer provides connection-oriented and connectionless services.                   | In this model, the network layer provides only connectionless service.                                      |
| **Assurance**                       | The transport layer provides a guarantee for the delivery of packets.                                           | The transport layer in this model does not provide assurance for delivery of packets.                       |
| **Session and presentation layer** | The session and presentation layers are separate.                                                              | The session and presentation layers are not segregated and are included in the application layer.            |
| **Minimum header size**            | The minimum header size is 5 bytes.                                                                             | The minimum header size is 20 bytes.                                                                          |
