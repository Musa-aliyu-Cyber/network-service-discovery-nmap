# Network Service Discovery & HTTP Service Analysis Using Nmap

## 📌 Project Overview

This project documents a controlled cybersecurity laboratory exercise focused on network service discovery and basic HTTP service analysis using Nmap and other Linux tools.

The objective was to understand how network services are identified, how ports appear during reconnaissance, and how the network interface a service binds to can affect its potential exposure.

## 🎯 Objectives

- Understand basic network service discovery.
- Identify open TCP ports.
- Identify services and service versions using Nmap.
- Understand the difference between localhost and network-interface binding.
- Analyze basic HTTP response headers.
- Identify the process responsible for a listening service.
- Practice documenting cybersecurity findings.

## 🛠️ Tools & Technologies

- Kali Linux
- Nmap
- Python 3
- curl
- ss
- VirtualBox

## 🧪 Lab Environment

| Component | Configuration |
|---|---|
| Operating System | Kali Linux |
| Network Interface | eth0 |
| Kali IP | 10.0.2.15 |
| Network | 10.0.2.0/24 |
| HTTP Service | Python SimpleHTTPServer |
| Port | TCP 8000 |

## 🔍 Methodology

### 1. Network Identification

The Kali Linux network configuration was examined using `ip addr` and `ip route` to identify the network interface, IP address, and local network.

### 2. HTTP Service Setup

A simple HTTP server was created using Python 3 and initially bound to the localhost address:

`127.0.0.1:8000`

### 3. Nmap Service Discovery

Nmap was used to scan TCP port 8000 and identify the running service.

The scan identified:

`8000/tcp open http SimpleHTTPServer 0.6`

### 4. Network Interface Binding

The HTTP server was then bound to the Kali Linux network interface:

`10.0.2.15:8000`

The listening address was verified using `ss`.

### 5. Service Analysis

Nmap was used again to identify the service and its version information.

The HTTP service was identified as:

`SimpleHTTPServer 0.6`

### 6. HTTP Header Analysis

`curl` was used to inspect the HTTP response headers.

The response included:

`HTTP/1.0 200 OK`

`Server: SimpleHTTP/0.6 Python/...`

`Content-type: text/html`

## 🔎 Key Findings

### Open Port

TCP port 8000 was open because the Python HTTP server was actively listening on the port.

### Service Identification

Nmap successfully identified the HTTP service as SimpleHTTPServer 0.6.

### Service Binding

Changing the service binding from `127.0.0.1` to `10.0.2.15` demonstrated how the interface a service listens on can affect its potential network exposure.

### Information Disclosure

The HTTP `Server` header disclosed information about the software serving the webpage.

## 📚 What I Learned

Through this project, I gained practical experience with:

- Network interface and IP identification.
- TCP ports and listening services.
- Nmap service discovery.
- Linux `ss` command.
- HTTP response analysis using `curl`.
- Service binding and network exposure.
- Basic information disclosure concepts.
- Documenting cybersecurity findings.

## 🔐 Security Consideration

This project was performed in a controlled laboratory environment using my own Kali Linux virtual machine. No unauthorized systems or third-party networks were scanned.

## 🏁 Conclusion

This project strengthened my understanding of basic network reconnaissance and HTTP service analysis. It demonstrated how services can be discovered, identified, and analyzed using common cybersecurity and Linux tools.

The project also highlighted the importance of understanding service configuration and network exposure when deploying applications.

---

**Author:** Aliyu Moses  
**Field:** Cybersecurity  
**Institution:** Nasarawa State University, Keffi
