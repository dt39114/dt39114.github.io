---
layout: post
title: System Design 101- Communication Protocols
subtitle: Let's unerstand how the systems talk
cover-img: /assets/img/1.jpg
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [systemDesign, TPM]
author: Dhruba Jyoti Talukdar
---
If you're a Technical Program Manager, product owner, or engineer stepping into system design, you've likely heard terms like _**HTTP**_, _**REST**_, _**GraphQL**_, _**WebSockets**_, or _**gRPC**_ tossed around. These are not just tech buzzwords — they’re how systems talk to each other.

This article breaks down the core communication protocols, how they work, and when to use each — using real-world analogies, crisp comparisons, and practical use cases.

##  🧱 1. Transport Protocols: The Foundation 
These protocols define how data moves between systems.

**⚙️ TCP (Transmission Control Protocol)**
Like sending a certified letter — guaranteed delivery and in the right order
Used by: **HTTP, REST, GraphQL, gRPC, WebSockets**

**⚡ UDP (User Datagram Protocol)
Like tossing leaflets from a plane — fast, no delivery guarantee
Used by: **Video calls, online gaming, DNS**

**📝 Tip**: Start with TCP unless you're working on real-time, latency-critical apps (games, video).


## 🔁 2. Request-Response Protocols
These protocols let one system request data from another and wait for a response.

**🌐 HTTP / HTTPS**
The foundation of the web
**Stateless**, each request is independent
HTTPS adds security with encryption (TLS).
🔧 Use for: Any modern web app or API.

**🧠 REST (Representational State Transfer)**
An architecture style **built on HTTP**
Uses standard verbs: **GET, POST, PUT, PATCH, DELETE**
Returns JSON or XML.
Stateless, simple to use and debug.
🔧 Use for: Most web and mobile APIs.

**🛁 SOAP (Simple Object Access Protocol)**
Heavyweight, XML-based.
Highly structured with strict contracts.
Built-in security, error handling, transaction support.
🔧 Use for: Legacy Banking, enterprise systems (E.G. SAP ERP), B2B APIs

**📦 gRPC (Google Remote Procedure Call)**
Binary, super fast, uses Protocol Buffers (Protobuf).
Runs on HTTP/2, supports streaming.
Ideal for machine-to-machine communication. 
🔧 Use for: Microservices, internal service-to-service calls

## **🧩 GraphQL**
Clients specify exactly the data they need.
One request can fetch deeply nested data.
Highly efficient, schema-driven.
**🔧 Use for: Modern UIs, dashboards, mobile apps with variable data needs.** 

## 3. Real-Time Protocols
These allow systems to maintain live connections for instant updates.

**📡 WebSockets**
Full-duplex, long-lived connection
Both client and server can push data anytime
Runs on TCP
🔧 Use for: Chat, gaming, live trading apps

**📬 Server-Sent Events (SSE)**
One-way communication (server → client)
Uses HTTP to stream updates.
Simpler than WebSockets, but limited.
🔧 Use for: News feeds, stock tickers, notifications.
📭 4. Message-Based Communication (Asynchronous)
Used when systems don’t wait for a response — improves decoupling, scalability.

## 🔃 Message Queues & Event Streams
Clients send messages to a broker (e.g., Kafka, RabbitMQ)
Other systems process messages asynchronously
Supports retries, buffering, durability
🔧 Use for: Order processing, logs, audit trails, microservice coordination.
