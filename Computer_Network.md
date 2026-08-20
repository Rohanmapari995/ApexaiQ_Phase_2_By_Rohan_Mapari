# 🌐 Computer Networking Basics

A beginner-friendly guide to understanding the **Internet, data transfer, IP addresses, port numbers, network types, topologies, OSI model, client-server architecture, and Internet protocols**.

## 📚 Table of Contents

1. [What is the Internet?](#1-what-is-the-internet)
2. [How is Data Transferred Over the Internet?](#2-how-is-data-transferred-over-the-internet)
3. [IP Address](#3-ip-address)
4. [Port Number](#4-port-number)
5. [Types of Networks](#5-types-of-networks)
6. [Network Topology](#6-network-topology)
7. [OSI Model](#7-osi-model)
8. [OSI Model Layers](#8-osi-model-layers)
9. [Client-Server Architecture](#9-client-server-architecture)
10. [Internet Protocols](#10-internet-protocols)
11. [How Everything Works Together](#11-how-everything-works-together)
12. [Quick Revision](#12-quick-revision)

---

# 1. What is the Internet?

The **Internet** is a worldwide network that connects millions of computers, smartphones, servers, and other devices so that they can communicate and share data.

### In simple words

> **Internet = Network of Networks**

### Example

```text
Your Computer
      ↓
Wi-Fi Router
      ↓
ISP
      ↓
Internet
      ↓
Web Server
```

### Important Terms

| Term | Meaning |
|---|---|
| Device | Computer, phone, server, etc. |
| Router | Directs data between networks |
| ISP | Internet Service Provider |
| Server | Computer that provides services/data |
| Client | Device/application requesting a service |

---

# 2. How is Data Transferred Over the Internet?

When you send data over the Internet, it is usually divided into small units called **packets**.

```text
Original Data
     ↓
Divided into Packets
     ↓
Network
     ↓
Routers
     ↓
Destination
     ↓
Packets Reassembled
     ↓
Original Data
```

### Step-by-Step Process

1. **Data is created**
2. **Data is divided into packets**
3. **Packets travel through routers**
4. **Destination receives packets**
5. **Packets are reassembled**

Each packet can contain information such as:

- Source IP address
- Destination IP address
- Port number
- Data
- Control information

### Simple Analogy

Think of sending a large book:

```text
Book
 ↓
Box 1
Box 2
Box 3
Box 4
 ↓
Transport Network
 ↓
Destination
 ↓
Boxes Combined
 ↓
Original Book
```

---

# 3. IP Address

An **IP address** is a logical address assigned to a device or network interface. It helps identify the source and destination of network communication.

### Example IPv4

```text
192.168.1.10
```

IPv4 uses **32 bits**.

### Example IPv6

```text
2001:0db8:85a3::8a2e:0370:7334
```

IPv6 uses **128 bits**.

### Types of IP Addresses

#### Private IP

Used inside local networks.

Common private IPv4 ranges include:

```text
10.0.0.0/8
172.16.0.0/12
192.168.0.0/16
```

#### Public IP

Used for communication over the public Internet.

---

# 4. Port Number

A **port number** identifies a particular application or network service running on a device.

### Easy Analogy

> **IP Address = Building Address**  
> **Port Number = Room Number**

Example:

```text
192.168.1.10:8080
```

Here:

```text
192.168.1.10 → IP Address
8080         → Port Number
```

### Common Port Numbers

| Port | Protocol/Service |
|---:|---|
| 20/21 | FTP |
| 22 | SSH |
| 23 | Telnet |
| 25 | SMTP |
| 53 | DNS |
| 80 | HTTP |
| 110 | POP3 |
| 143 | IMAP |
| 443 | HTTPS |

---

# 5. Types of Networks

Networks can be classified according to their geographical coverage.

## 5.1 PAN — Personal Area Network

A small network around an individual.

Examples:

- Bluetooth earbuds
- Smartwatch
- Phone

```text
Phone
 ↕
Smartwatch
```

## 5.2 LAN — Local Area Network

A network covering a small area such as a home, office, school, or laboratory.

```text
PC ──┐
PC ──┤
PC ──┼── Switch ── Router
PC ──┤
PC ──┘
```

## 5.3 MAN — Metropolitan Area Network

A network covering a city or metropolitan area.

```text
College A ──┐
College B ──┼── City Network
College C ──┘
```

## 5.4 WAN — Wide Area Network

A network covering a large geographical area.

```text
India ───── USA ───── Europe
```

The Internet is a global interconnected system of networks and operates at a WAN/global scale.

### Easy Way to Remember

```text
PAN → Person
LAN → Building
MAN → City
WAN → Country / World
```

---

# 6. Network Topology

**Network topology** describes how devices are connected in a network.

Main types:

- Bus
- Star
- Ring
- Mesh
- Tree
- Hybrid

## 6.1 Bus Topology

All devices share a common main cable.

```text
PC ─── PC ─── PC ─── PC
       Main Cable
```

### Advantages

- Simple
- Low cost

### Disadvantages

- Main cable failure can affect the network
- Difficult to troubleshoot
- Performance can decrease as devices increase

## 6.2 Star Topology

All devices connect to a central device, usually a switch.

```text
       PC
       |
PC ─ Switch ─ PC
       |
       PC
```

### Advantages

- Easy to manage
- Easy to troubleshoot
- Failure of one cable normally affects only one device

### Disadvantage

- Failure of the central switch can affect connected devices

Star topology is very common in modern LANs.

## 6.3 Ring Topology

Devices are connected in a ring.

```text
PC ── PC
|      |
PC ── PC
```

## 6.4 Mesh Topology

Devices have multiple connections.

```text
A ───── B
|\     /|
| \   / |
|  \ /  |
|  / \  |
| /   \ |
C ───── D
```

### Advantages

- Highly reliable
- Multiple paths are available

### Disadvantages

- Expensive
- Complex to install and maintain

## 6.5 Tree Topology

A hierarchical arrangement of networks.

```text
          Core
         /    \
       SW      SW
      /  \    /  \
    PC   PC  PC   PC
```

## 6.6 Hybrid Topology

A combination of two or more network topologies.

Examples:

```text
Star + Bus
Star + Ring
```

---

# 7. OSI Model

**OSI = Open Systems Interconnection**

The OSI model is a conceptual model that explains how network communication is organized into **7 layers**.

| Layer | Name |
|---:|---|
| 7 | Application |
| 6 | Presentation |
| 5 | Session |
| 4 | Transport |
| 3 | Network |
| 2 | Data Link |
| 1 | Physical |

### Mnemonic

> **Please Do Not Throw Sausage Pizza Away**

```text
7 → Application
6 → Presentation
5 → Session
4 → Transport
3 → Network
2 → Data Link
1 → Physical
```

---

# 8. OSI Model Layers

## Layer 1 — Physical

Deals with the actual transmission of bits.

Examples:

- Ethernet cables
- Fiber-optic cables
- Radio signals
- Electrical signals
- Connectors

**Data Unit:** Bits

```text
10110101
```

## Layer 2 — Data Link

Responsible for communication between devices on the same local network.

Examples:

- Ethernet
- Wi-Fi

It works with **MAC addresses**.

**Data Unit:** Frame

## Layer 3 — Network

Responsible for routing data between networks.

### Main Concept

**IP Address**

### Important Protocol

**IP**

### Main Device

**Router**

**Data Unit:** Packet

## Layer 4 — Transport

Provides communication between applications.

### Main Protocols

- TCP
- UDP

### TCP

TCP provides reliable, ordered delivery.

```text
Send
 ↓
Receive
 ↓
Acknowledge
 ↓
Continue
```

### UDP

UDP is faster and has lower overhead, but does not provide TCP's delivery guarantees.

Common uses include:

- Online gaming
- Streaming
- Voice/video communication

**Data Units:**

```text
TCP → Segment
UDP → Datagram
```

## Layer 5 — Session

Manages communication sessions between applications.

```text
Start Session
      ↓
Communication
      ↓
End Session
```

## Layer 6 — Presentation

Deals with the representation and transformation of data.

Functions include:

- Data formatting
- Encryption/decryption
- Compression
- Character encoding

## Layer 7 — Application

The layer closest to the user and applications.

Examples:

- HTTP
- HTTPS
- FTP
- SMTP
- DNS

Examples of applications:

- Web browser
- Email client
- FTP client

---

# 9. Client-Server Architecture

In **client-server architecture**, the client requests a service and the server provides it.

## Client

A **client** is a device or application that requests a service.

Examples:

- Web browser
- Mobile application
- Email application

## Server

A **server** is a computer/system that provides a service or resource.

Examples:

- Web server
- Database server
- Email server
- File server

### Basic Architecture

```text
       CLIENT
      Browser
         |
         | Request
         ↓
      INTERNET
         |
         ↓
       SERVER
     Web Server
         |
         | Response
         ↓
       CLIENT
      Browser
```

### Example

```text
Client:
"Give me the webpage."

Server:
"Here is the webpage."
```

### Real-World Analogy

```text
Customer → Waiter → Kitchen
           Request

Kitchen → Waiter → Customer
           Response
```

The customer is similar to the **client**, while the kitchen is similar to the **server**.

---

# 10. Internet Protocols

A **protocol** is a set of rules that defines how devices communicate.

Think of protocols as the **rules of communication between computers**.

| Protocol | Full Form | Purpose |
|---|---|---|
| HTTP | HyperText Transfer Protocol | Web communication |
| HTTPS | HTTP Secure | Secure web communication |
| TCP | Transmission Control Protocol | Reliable data delivery |
| UDP | User Datagram Protocol | Fast communication |
| IP | Internet Protocol | Addressing and routing |
| DNS | Domain Name System | Converts domain names to IP addresses |
| DHCP | Dynamic Host Configuration Protocol | Automatically provides IP configuration |
| FTP | File Transfer Protocol | File transfer |
| SSH | Secure Shell | Secure remote access |
| SMTP | Simple Mail Transfer Protocol | Sending email |
| POP3 | Post Office Protocol 3 | Receiving email |
| IMAP | Internet Message Access Protocol | Accessing email from a mail server |

---

# 11. How Everything Works Together

Suppose you enter:

```text
www.example.com
```

into your browser.

## Step 1 — DNS

The browser/system needs the server's IP address.

```text
www.example.com
       ↓
      DNS
       ↓
IP Address
```

## Step 2 — Client Creates a Request

The browser creates an HTTP/HTTPS request.

```text
Browser
   ↓
HTTPS Request
```

## Step 3 — Transport Layer

TCP may provide reliable transport.

```text
HTTPS
  ↓
TCP
```

## Step 4 — IP

IP provides source and destination addressing.

```text
Source IP
Destination IP
```

## Step 5 — Routers Forward Packets

Packets travel through routers toward the destination.

```text
Your PC
   ↓
Router
   ↓
Router
   ↓
Router
   ↓
Web Server
```

## Step 6 — Server Sends Response

```text
Web Server
    ↓
Response
    ↓
Internet
    ↓
Your Router
    ↓
Your PC
    ↓
Browser
```

The webpage is then displayed in your browser.

---

# 12. How the Concepts Relate

```text
                     INTERNET
                        |
                Network of Networks
                        |
             ┌──────────┴──────────┐
             │                     │
          CLIENT                 SERVER
             │                     │
          Browser              Web Server
             │                     │
             └──────────┬──────────┘
                        │
                     Routers
                        │
                     Packets
                        │
               IP Address + Port
                        │
                   Protocols
                        │
                    OSI Model
```

---

# ⭐ Quick Revision

| Concept | Simple Meaning |
|---|---|
| Internet | Network of interconnected networks |
| Packet | Small unit of transmitted data |
| IP Address | Identifies a network interface/device |
| Port | Identifies an application/service |
| Router | Forwards packets between networks |
| Protocol | Rules for communication |
| LAN | Local network |
| WAN | Large geographical network |
| Topology | Arrangement of network devices |
| OSI | 7-layer networking reference model |
| Client | Requests a service |
| Server | Provides a service |
| TCP | Reliable transport protocol |
| UDP | Fast, connectionless transport protocol |
| DNS | Converts domain names to IP addresses |
| HTTP/HTTPS | Web communication protocols |

---

# 🧠 Most Important Things to Remember

```text
Internet
   ↓
Connects Networks

IP Address
   ↓
Identifies Network Location

Port Number
   ↓
Identifies Application/Service

Router
   ↓
Forwards Packets

Protocol
   ↓
Rules of Communication

OSI Model
   ↓
Explains Network Communication

Client
   ↓
Requests Service

Server
   ↓
Provides Service
```

## 🔑 One-Line Summary

> **When a client communicates with a server over the Internet, data is divided into packets, addressed using IP addresses and ports, transported using protocols such as TCP/UDP, routed through networks by routers, and delivered to the destination application.**
