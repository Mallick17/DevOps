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

### **How Data Travels Through the OSI Model (Example of an HTTP Request)**  
![Screenshot 2025-02-26 121702](https://github.com/user-attachments/assets/01442827-24b7-4c79-be6d-9f80fc57a1f5)

#### **Step 1: Application Layer (Layer 7)**
- A user sends an **HTTP request** to access a webpage.
- The **HTTP header** is added to the data.

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
  <summary>Click to view detailed Breakdown of each SEGMENT for PACKETS</summary>

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

</details>

#### **Step 4: Data Link Layer (Layer 2)**
- The packet(IP datagram) is wrapped with a **MAC header**.
- The **MAC header contains source and destination MAC addresses**.

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
