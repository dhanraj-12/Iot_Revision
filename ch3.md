# IoT Communication and Application Network: Technical Hierarchy

## 1. Introduction & Optimization Needs
* **IoT Challenges on IP**
    * High difficulty in building IoT solutions on standard IP
    * Need to integrate non-IP devices with constrained IoT nodes
    * Optimization required at various layers of the IP stack
* **Constraints and Limitations**
    * **Constrained Nodes**: Coexistence of different device classes
    * **Device Architecture**: Characteristics often differ from generic PC/Server environments
    * **Unreliable Paths**: Communication through lossy network protocol stacks
    * **Power**: Battery life requirements ranging from a few months to 10+ years

## 2. IoT vs. Web Protocol Stack
* **Data Formats**
    * IoT: Binary, JSON, CBOR
    * Web: HTML, XML, JSON
* **Application Layer**
    * IoT: CoAP, MQTT, XMPP, AMQP
    * Web: HTTP, DHCP, DNS, TLS/SSL
* **Transport Layer**
    * IoT: UDP, DTLS
    * Web: TCP, UDP
* **Internet Layer**
    * IoT: IPv6/IP Routing, 6LoWPAN
    * Web: IPv6, IPv4, IPSec
* **Network/Link Layer**
    * IoT: IEEE 802.15.4 MAC/PHY
    * Web: Ethernet, DSL, ISDN, Wi-Fi

## 3. IPv6 Fundamentals
* **Problems with IPv4**
    * Shortage of address space
    * Lack of Quality of Service (QoS) guarantees
* **New Features of IPv6**
    * Enlarged 128-bit address space
    * Fixed header format for faster processing
    * Neighbor discovery and Auto-configuration
    * Hierarchical address architecture
    * Anycast addressing (routing to "best" of replicated servers)
* **Header Optimization**
    * Checksum removed to reduce processing at routers
    * Fragmentation not allowed at intermediate routers

## 4. 6LoWPAN (IPv6 over Low Power WPAN)
* **Concept & Motivation**
    * Acronym: IPv6 over Low power Wireless Personal Area Networks
    * Designed to enable IP on battery-powered/low-bitrate 802.15.4 networks
* **Adaptation Layer Key Elements**
    * **Header Compression**: Reducing 40-byte IPv6 headers to a few bytes/bits
    * **Fragmentation**: Supporting IPv6 1280-byte MTU over 127-byte frames
    * **Layer-Two Forwarding**: Delivering datagrams over multiple radio hops
* **Topologies**
    * **Star**: All nodes reach a central Border Router (LBR)
    * **Meshed (Mesh-under)**: Layer 2 relaying; network shares same prefix
    * **Routed (Route-over)**: Nodes act as routers using RPL protocol

## 5. RPL (Routing Protocol for LLNs)
* **Algorithm & Standard**
    * Defined in RFC 6550
    * Based on distance vector algorithms
* **Topology Structure**
    * Directed Acyclic Graph (DAG)
    * Destination Oriented DAG (DODAG): One per sink/root
    * RPL Instance: Set of DODAGs sharing an Objective Function (OF)
* **Communication Patterns**
    * Multipoint-to-Point (MP2P): Nodes to central sink
    * Point-to-Multipoint (P2MP): Central server to multiple nodes
* **Control Messages (ICMPv6)**
    * DIO: DAG Information Object (discovery and configuration)
    * DIS: DAG Information Solicitation (requesting information)
    * DAO: Destination Advertisement Object (propagating route info upward)

## 6. Application Layer Protocols

### A. CoAP (Constrained Application Protocol)
* **Characteristics**
    * RESTful protocol (GET, PUT, POST, DELETE)
    * Based on UDP to reduce overhead
    * Specialized for M2M and constrained environments
* **Messaging Model**
    * **Confirmable (CON)**: Reliable transmission with retransmission
    * **Non-confirmable (NON)**: Unreliable transmission
* **Key Features**
    * **OBSERVE**: Subscription-based periodic responses
    * Easy to proxy to/from HTTP

### B. MQTT (MQ Telemetry Transport)
* **Architecture**
    * Broker-based publish/subscribe messaging
    * Lightweight, typically flows over TCP/IP
* **Quality of Service (QoS)**
    * QoS 0: "At most once" (best effort)
    * QoS 1: "At least once" (assured arrival, potential duplicates)
    * QoS 2: "Exactly once" (guaranteed arrival)
* **Key Features**
    * Small 2-byte fixed header
    * "Last will and testament" for abnormal disconnections

### C. XMPP (Extensible Messaging and Presence Protocol)
* **Architecture**
    * Decentralized, XML-based streaming
    * Addressing: `node@domain/resource` (JID)
* **Pros & Cons**
    * Advantages: Decentralized nature, isolated private servers, presence support
    * Disadvantages: Lack of native QoS and end-to-end encryption

    # IoT Communication and Application Network: Revision Guide

## 1. Introduction & Optimization Needs
* **IoT Challenges on IP**: Standard IP stacks are often too heavy for "Things," necessitating specialized integration for non-IP devices.
* **Optimization Necessity**: Power and bandwidth restrictions require optimizations across all layers of the IP stack to maintain connectivity.
* **Constrained Nodes**: IoT is a platform where diverse device classes coexist, often lacking the resources of standard IT servers.
* **Unreliable Paths**: Network stacks must be resilient enough to communicate through unstable or lossy radio paths.
* **Power Constraints**: Devices are frequently battery-powered with lifespan requirements ranging from months to over 10 years.

## 2. IoT vs. Web Protocol Stack
* **Data Formats**: IoT uses compact binary formats (CBOR, Binary) or lightweight JSON; the Web relies on verbose HTML and XML.
* **Application Layer**: IoT uses specialized M2M protocols like CoAP, MQTT, and XMPP; the Web uses HTTP and DNS.
* **Transport Layer**: IoT prioritizes UDP and DTLS for lower overhead; the Web relies heavily on TCP for reliable streaming.
* **Internet Layer**: IoT introduces 6LoWPAN to adapt IPv6 for low-power radios, whereas the Web uses standard IPv4/IPv6.
* **Network/Link Layer**: IoT typically uses IEEE 802.15.4 (Low-Rate WPAN); the Web uses Ethernet or Wi-Fi.



## 3. IPv6 Fundamentals
* **IPv4 Limitations**: Shortage of address space and lack of native Quality of Service (QoS) make IPv4 insufficient for billions of IoT nodes.
* **IPv6 Benefits**:
    * **Addressing**: 128-bit space allows for a massive number of unique endpoints.
    * **Header Format**: A simplified, fixed header format speeds up hardware processing and forwarding.
    * **Auto-configuration**: Supports neighbor discovery and stateless address setup for easy deployment.
    * **Anycast**: Allows routing a packet to the "best" or nearest server in a replicated group.
* **Key Changes**: Removed the header checksum and disallowed fragmentation at intermediate routers to reduce processing latency.

## 4. 6LoWPAN (IPv6 over Low Power WPAN)
* **Definition**: A standard designed to enable IPv6 to run over IEEE 802.15.4 radio networks.
* **Adaptation Layer Functions**:
    * **Header Compression**: Shrinks the 40-byte IPv6 header to a few bytes by removing common or redundant fields.
    * **Fragmentation**: Slices large 1280-byte IPv6 packets into small fragments to fit the 127-byte 802.15.4 MTU.
    * **L2 Forwarding**: Enables datagram delivery across multiple radio hops.
* **Topologies**:
    * **Star**: Direct connection to a central Border Router (LBR).
    * **Mesh-under**: Relays frames at the link layer; looks like one subnet to the internet.
    * **Route-over**: Nodes act as IP routers, typically using the RPL protocol.



## 5. RPL (Routing Protocol for LLNs)
* **Algorithm**: A distance-vector protocol designed specifically for Low-power and Lossy Networks (LLNs).
* **Topology (DODAG)**: Organizes nodes into a Directed Acyclic Graph where traffic flows toward a central "sink" or root.
* **Traffic Flows**: Optimized for Multipoint-to-Point (nodes to root) and Point-to-Multipoint (root to nodes) traffic.
* **Control Messages**: 
    * **DIO (Information Object)**: Broadcasts instance and configuration info to build the graph.
    * **DIS (Solicitation)**: Solicits info from neighbors to join a graph.
    * **DAO (Advertisement Object)**: Advertises destination prefixes upward to enable downward routing.



## 6. Application Layer Protocols

### A. CoAP (Constrained Application Protocol)
* **Architecture**: A RESTful protocol (GET, PUT, POST, DELETE) specialized for M2M and constrained environments.
* **Transport**: Uses UDP to minimize the "handshake" and connection overhead associated with TCP.
* **Reliability**: Employs "Confirmable" (CON) messages with exponential back-off for guaranteed delivery.
* **Observe**: A feature allowing clients to "subscribe" to a resource and receive periodic updates when it changes.

### B. MQTT (MQ Telemetry Transport)
* **Architecture**: A broker-based publish/subscribe model that decouples senders and receivers.
* **QoS Levels**: 
    * **QoS 0**: At most once (best effort).
    * **QoS 1**: At least once (arrival guaranteed, duplicates possible).
    * **QoS 2**: Exactly once (arrival guaranteed, no duplicates).
* **Features**: Extremely low overhead with a 2-byte fixed header and "Last Will" for abnormal disconnections.



### C. XMPP (Extensible Messaging and Presence Protocol)
* **Architecture**: A decentralized, XML-based streaming protocol.
* **Addressing**: Uses a Jabber ID (JID) in the `node@domain/resource` format.
* **Pros/Cons**: Offers high decentralization and built-in presence but lacks native QoS and is more text-heavy than binary protocols.