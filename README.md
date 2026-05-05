🌐 Line-Based TCP Client–Server (ACP Protocol)
<div align="center"> <svg width="600" height="120"> <rect width="600" height="120" fill="#0f172a"/> <text x="50%" y="40%" dominant-baseline="middle" text-anchor="middle" fill="#38bdf8" font-size="22"> Application Communication Protocol (ACP) </text> <text x="50%" y="70%" dominant-baseline="middle" text-anchor="middle" fill="#94a3b8" font-size="14"> Client ↔ Server | TCP | ASCII | Real-time Validation </text> </svg> <br/> <img src="https://img.shields.io/badge/Protocol-TCP-blue"/> <img src="https://img.shields.io/badge/Type-Client--Server-green"/> <img src="https://img.shields.io/badge/Language-C++-orange"/> <img src="https://img.shields.io/badge/Status-Completed-brightgreen"/> <img src="https://img.shields.io/badge/Validation-100%25-success"/> <img src="https://img.shields.io/badge/IPv4%2FIPv6-Supported-blueviolet"/> </div>
📌 Overview

This project implements a line-based TCP communication protocol (ACP) using a custom-built client and server in C++.

It simulates a real-world request–response system where:

The server generates computational tasks
The client processes and responds
The server validates correctness in real-time

👉 Built to demonstrate network programming, protocol design, and system reliability

🧠 Protocol Design
📡 Communication Flow
![Network Topology](./images/topology.png)
⚙️ Features
🔹 Client (Lab 1a)
Supports DNS, IPv4, IPv6 resolution
Handles protocol negotiation
Parses and computes:
Integer ops → add, sub, mul, div
Float ops → fadd, fsub, fmul, fdiv
Implements precision-safe float comparison
Handles errors:
Resolve failure
Connection failure
Protocol mismatch
🔹 Server (Lab 1b)
Handles 1 active client + queue of 5
Rejects overload (6th client ❌)
Generates random computation tasks
Enforces timeout (5 seconds)
Validates client results:
Integer → exact match
Float → tolerance check (< 0.0001)
🔢 Operations Supported
Type	Operations
Integer	add, sub, mul, div
Floating	fadd, fsub, fmul, fdiv
🖼️ Architecture
<div align="center"> <svg width="700" height="250"> <rect x="50" y="80" width="150" height="80" fill="#1e293b"/> <text x="125" y="125" fill="white" text-anchor="middle">Client</text> <rect x="500" y="80" width="150" height="80" fill="#1e293b"/> <text x="575" y="125" fill="white" text-anchor="middle">Server</text> <line x1="200" y1="120" x2="500" y2="120" stroke="#38bdf8" stroke-width="3"/> <text x="350" y="105" fill="#38bdf8" text-anchor="middle">TCP Connection</text>

<text x="350" y="170" fill="#94a3b8" text-anchor="middle">Request ↔ Response ↔ Validation</text>
</svg>

</div>
🧪 Example Execution
$ ./client 13.53.76.30:5000

Host 13.53.76.30, and port 5000.
ASSIGNMENT: mul 9 26
OK (myresult=234)
🛠️ Build & Run
# Clone repo
git clone https://github.com/yourusername/np_assignment1.git
cd np_assignment1

# Build
make

# Run client
./client <IP|DNS>:<PORT>

# Run server
./server <IP|DNS>:<PORT>

# Clean build
make clean
📂 Project Structure
np_assignment1/
├── clientmain.cpp
├── servermain.cpp
├── calcLib.c
├── calcLib.h
├── Makefile
├── client
├── server
└── README.md
🔍 Validation Strategy

✔ Tested against reference server
✔ Verified protocol compliance
✔ Simulated:

Connection failures
Timeout scenarios
Incorrect results

✔ Achieved:

100% protocol accuracy
Reliable client-server interaction
🚧 Challenges Solved
Handling TCP stream parsing with newline delimiters
Managing floating-point precision errors
Implementing DNS + IPv4 + IPv6 compatibility
Designing queue-based connection handling
Ensuring robust error handling & recovery
📊 Key Learnings
Protocol design must consider edge cases + failure modes
TCP communication requires strict parsing discipline
Floating-point comparisons are never exact
Scalability starts with good connection handling logic
🤝 Future Improvements
Multi-threaded server handling
TLS/SSL secure communication
UTF-8 protocol upgrade
Load balancing across multiple servers
😄 Fun Note

Built a protocol where even a small typo = ERROR 😅

Computers are strict… no “almost correct” allowed

🔗 Connect
💼 LinkedIn: https://github.com/prudhviponnada/
⭐ Support

If you like this project:
👉 Star the repo
👉 Share feedback
👉 Connect with me
