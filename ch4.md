# IoT Communication & Access Technologies: Complete Tree Diagram

* **IoT Communication Fundamentals**
    * **Connecting Smart Objects**
    * **Communication Criteria**
        * **Range**
            * **Short Range**: Tens of meters (e.g., Bluetooth, VLC)
            * **Medium Range**: Tens to hundreds of meters (e.g., WiFi, ZigBee, PLC)
            * **Long Range**: > 1.6 km / 1 mile (e.g., 4G/5G, NB-IoT, LoRaWAN)
        * **Frequency Bands**
            * **Licensed**: Cellular (900-2100 MHz), NB-IoT (700-900 MHz)
            * **Unlicensed (ISM)**: 2.4 GHz, 5 GHz, 868 MHz (India), 915 MHz
        * **Power Consumption**
            * **Powered Nodes**: Continuous power source; mobility is complex
            * **Battery-Powered Nodes**: Limited energy; requires low-power access (LPWA)
        * **Topology**
            * **Star**: Central hub; used in WiFi and Long-Range tech
            * **Mesh**: Self-healing; used in ZigBee and Wi-SUN
            * **Peer-to-Peer**: Direct device-to-device
        * **Constrained Devices (RFC 7228)**
            * **Class 0**: < 10 KB RAM, < 100 KB Flash (e.g., Push button)
            * **Class 1**: > 10 KB RAM, > 100 KB Flash (e.g., Sensors)
            * **Class 2**: > 50 KB RAM, > 250 KB Flash (e.g., Smart meter)
        * **Network Characteristics (LLNs)**
            * Data rate & throughput
            * Latency & determinism
            * Overhead & payload (IPv6 MTU vs. Link layer limits)

* **IoT Access Technologies (Layer 1 & 2)**
    * **IEEE 802.15.4 (Low-Rate WPAN)**
        * **Physical Layer (PHY)**
            * Frequency/Data rates: 2.4 GHz (250 kbps), 868/915 MHz
            * Modulations: OQPSK, BPSK, ASK
        * **MAC Layer**
            * Frame Types: Data, Beacon, Acknowledgement (ACK), Command
            * Addressing: 16-bit short or 64-bit extended
        * **Security**: AES 128-bit encryption + Message Integrity Code (MIC)
    * **ZigBee Stack**
        * **ZigBee PRO**: AODV routing over mesh; application profiles
        * **ZigBee IP**: Adopts IPv6, 6LoWPAN, and RPL routing
    * **LoRaWAN (Unlicensed LPWA)**
        * **PHY**: Chirp Spread Spectrum (CSS) modulation
        * **MAC Classes**
            * **Class A**: Bi-directional, battery optimized (Default)
            * **Class B**: Extra receive slots via gateway beacons
            * **Class C**: Continuous listening (Powered nodes)
        * **Security**: Network Session Key (NwkSKey) + Application Session Key (AppSKey)
    * **NB-IoT (Licensed LPWA)**
        * 3GPP Standard; 10+ year battery life; deep indoor coverage
    * **IEEE 802.11ah (Wi-Fi HaLow)**
        * Sub-GHz Wi-Fi; extended range; supports large number of devices
    * **Additional Protocol Stacks**
        * **6LoWPAN**: IPv6 adaptation layer for 802.15.4
        * **WirelessHART**: Time-synchronized mesh for 2.4 GHz
        * **Thread**: IPv6-based mesh for home automation
        * **ISA100.11a**: Industrial process control standard



* **IoT Design Methodology (10 Steps)**
    1. **Purpose & Requirements**: Define system goals
    2. **Process Model**: Define use cases
    3. **Domain Model**: Define entities, devices, and services
    4. **Information Model**: Define data structures/attributes
    5. **Service Specifications**: Map processes to services
    6. **IoT Level**: Define system complexity level
    7. **Functional View**: Map levels to functional groups
    8. **Operational View**: Choose communication and storage options
    9. **Device & Component Integration**: Hardware/Software integration
    10. **Application Development**: Final software creation




# IoT Communication & Access Technologies: Comprehensive Study Notes

---

# 1. Communication Fundamentals

Communication fundamentals define the **key criteria used to select appropriate communication technologies** for connecting smart objects in the Internet of Things (IoT).

A large number of **wired and wireless access technologies** exist for IoT systems. Wireless communication is especially popular because:

- It simplifies deployment.
- It allows mobility of smart objects.
- It avoids complex cabling infrastructure.
- It enables scalable device connectivity.

When designing IoT systems, several **communication characteristics must be evaluated**, such as:

- Range
- Frequency bands
- Power consumption
- Network topology
- Device constraints

These criteria help engineers determine which communication technology is suitable for specific IoT applications.

---

## Range

Communication **range** defines the maximum distance between two devices that can communicate reliably.

IoT communication technologies are usually categorized into three main ranges.

### Short Range

Short-range communication supports **distances of a few meters up to tens of meters**.

These technologies are commonly used as **replacements for wired connections like serial cables**.

**Characteristics**

- Low power consumption  
- Low data rate  
- Suitable for indoor environments  
- Usually used in personal devices  

**Examples**

- Bluetooth (IEEE 802.15.1)  
- Visible Light Communication (VLC – IEEE 802.15.7)

**Typical Applications**

- Wearable devices  
- Wireless keyboards and mice  
- Smart home sensors  
- Fitness trackers  

---

### Medium Range

Medium-range communication supports **distances from tens to hundreds of meters**.

These technologies are commonly used for **home automation, industrial monitoring, and local IoT networks**.

**Examples**

Wireless:

- WiFi (IEEE 802.11)  
- ZigBee (IEEE 802.15.4)  
- LoRa (in some configurations)

Wired:

- Ethernet (IEEE 802.3)  
- Power Line Communication (PLC – IEEE 1901.2)

**Typical Applications**

- Smart homes  
- Building automation  
- Industrial sensor networks  
- Smart agriculture monitoring  

---

### Long Range

Long-range communication supports **distances greater than 1 mile (1.6 km)** and often up to several kilometers.

These technologies are used in **wide-area IoT deployments**.

**Examples**

- Cellular Networks (2G, 3G, 4G, 5G)  
- NB-IoT  
- LoRaWAN  
- WiFi HaLow (IEEE 802.11ah)

**Typical Applications**

- Smart cities  
- Asset tracking  
- Environmental monitoring  
- Smart agriculture  
- Utility monitoring  

---

## Frequency Bands

Wireless communication operates using **radio frequency spectrum**, which is regulated by national and international organizations such as:

- ITU (International Telecommunication Union)  
- FCC (Federal Communications Commission)

Frequency bands are divided into **licensed and unlicensed categories**.

---

### Licensed Bands

Licensed bands require **government authorization** to operate.

Telecommunication companies typically purchase licenses to operate networks.

**Characteristics**

- Controlled spectrum usage  
- Reduced interference  
- Reliable communication  

**Examples**

- Cellular communication (900–2100 MHz)  
- NB-IoT (700–900 MHz)  
- WiMAX  

These technologies are typically used for **large-scale IoT deployments requiring reliability**.

---

### Unlicensed Bands (ISM Bands)

Unlicensed bands are known as **Industrial, Scientific, and Medical (ISM) bands**.

Anyone can use these frequencies without a license, but **interference protection is not guaranteed**.

**Common ISM Bands**

- 2.4 GHz → WiFi, Bluetooth, ZigBee  
- 5 GHz → WiFi  
- 868 MHz → LoRa (Europe / India)  
- 915 MHz → LoRa (USA)

In India specifically:

- **865–867 MHz ISM band is allowed**

These bands are widely used because they **reduce deployment costs**.

---

## Power Consumption

Power consumption is one of the **most important factors in IoT communication design**.

IoT devices can be classified based on their power source.

---

### Powered Nodes

Powered nodes are devices that have a **continuous power supply**.

Examples include:

- Industrial machines  
- Smart gateways  
- Smart TVs  
- Servers  

**Characteristics**

- No strict power limitations  
- High communication performance possible  
- Suitable for continuous operation  

However, deployment flexibility is limited because **power outlets must be available**.

---

### Battery-Powered Nodes

Battery-powered nodes rely on **small batteries** for energy.

These devices must use **extremely energy-efficient communication technologies**.

**Characteristics**

- Portable  
- Flexible deployment  
- Requires low power communication protocols  
- Must support long battery life (often 10+ years)

Examples include:

- Environmental sensors  
- Wearables  
- Smart meters  
- Remote monitoring devices  

IoT technologies such as **ZigBee, LoRaWAN, and NB-IoT** are optimized for such devices.

---

## Topology

Network topology defines **how devices are interconnected and how data flows between them**.

Three major IoT network topologies exist.

---

### Star Topology

In star topology, **all devices communicate with a central node or gateway**.

Example structure:

Node    — Gateway — Node


**Advantages**

- Simple architecture  
- Easy to manage  
- Efficient communication  

**Disadvantages**

- If the gateway fails, the entire network fails.

**Used in**

- WiFi networks  
- LoRaWAN  

---

### Mesh Topology

In mesh topology, **devices relay messages for each other**.

Example structure:
Node — Node — Node


**Advantages**

- Highly reliable  
- Self-healing network  
- Extended coverage  

**Disadvantages**

- Higher complexity  
- Increased energy consumption  

**Used in**

- ZigBee  
- WirelessHART  
- Smart utility networks  

---

### Peer-to-Peer Topology

In peer-to-peer topology, **two devices communicate directly** without a central controller.

**Advantages**

- Simple communication  
- Low latency  

**Disadvantages**

- Limited scalability  

Used mainly in **small networks or direct device communication**.

---

## Constrained Devices (RFC 7228)

IoT devices often have **limited hardware resources**, which restrict their networking capabilities.

RFC 7228 defines **three classes of constrained devices**.

---

### Class 0 Devices

- RAM: < 10 KB  
- Flash: < 100 KB  
- No IP stack support  

These devices are extremely constrained and cannot directly connect to IP networks.

**Example**

- Simple push-button sensors

They usually communicate through **gateways or proxies**.

---

### Class 1 Devices

- RAM: ~10 KB  
- Flash: ~100 KB  
- Supports optimized IP stack  

These devices support **lightweight networking protocols** such as:

- 6LoWPAN  
- CoAP  

**Examples**

- Temperature sensors  
- Smart light controllers  

---

### Class 2 Devices

- RAM: > 50 KB  
- Flash: > 250 KB  
- Full IP stack supported  

These devices can run **complete networking protocols like IPv6 and TLS**.

**Examples**

- Smart meters  
- Industrial controllers  

---

# 2. IoT Access Technologies (Layer 1 & Layer 2)

IoT access technologies operate at the **Physical Layer (Layer 1)** and **Data Link Layer (Layer 2)** of the network stack.

These technologies define how devices:

- transmit signals  
- access communication channels  
- manage connectivity  

Some widely used IoT access technologies include:

- IEEE 802.15.4  
- ZigBee  
- LoRaWAN  
- NB-IoT  
- IEEE 802.11ah  

---

## IEEE 802.15.4

IEEE 802.15.4 is a standard designed for **low-cost, low-data-rate wireless personal area networks (LR-WPAN)**.

It is widely used for **battery-powered IoT devices**.

---

### Key Features

- Low power consumption  
- Low data rate  
- Short communication range  
- Simple protocol stack  
- Suitable for sensor networks  

---

### Physical Layer (PHY)

The PHY layer defines **radio frequency operation and data transmission methods**.

Common frequency bands:

| Frequency | Channels | Data Rate |
|----------|---------|-----------|
| 2.4 GHz | 16 | 250 kbps |
| 915 MHz | 10 | 250 kbps |
| 868 MHz | 3 | 100 kbps |

---

### MAC Layer

The MAC layer controls **how devices access the communication channel**.

Functions include:

- Device association  
- Channel access control  
- Data transmission  
- Security management  

MAC frame types:

- Data Frame → carries payload data  
- Beacon Frame → network synchronization  
- ACK Frame → confirms reception  
- Command Frame → network control messages  

---

### Security

IEEE 802.15.4 uses:

- **AES 128-bit encryption**
- **Message Integrity Code (MIC)** for data validation.

---

## ZigBee

ZigBee is a **protocol stack built on top of IEEE 802.15.4**.

It adds higher-layer functions such as:

- networking  
- routing  
- security  
- application support  

---

### ZigBee Features

- Low power consumption  
- Low bandwidth  
- Mesh networking support  
- High scalability  

---

### ZigBee Routing

ZigBee uses **AODV (Ad-hoc On-demand Distance Vector)** routing.

This allows dynamic routing in **mesh networks**.

---

### Security

ZigBee uses:

- **128-bit AES encryption**
- Security at MAC, network, and application layers.

---

### ZigBee Applications

- Smart homes  
- Industrial automation  
- Smart energy systems  
- Asset tracking  
- Environmental monitoring  

---

## ZigBee IP

ZigBee IP was introduced to support **Internet interoperability**.

Unlike traditional ZigBee, ZigBee IP uses **IETF standards**.

Supported protocols:

- IPv6  
- 6LoWPAN  
- ICMPv6  
- RPL routing  

This allows **direct IP connectivity for IoT devices**.

---

## LoRaWAN

LoRaWAN is a **Low-Power Wide-Area Network (LPWAN) protocol** designed for long-range IoT communication.

It operates in **unlicensed sub-GHz frequency bands**.

---

### LoRa PHY Layer

LoRa uses **Chirp Spread Spectrum (CSS)** modulation.

Advantages:

- Robust against interference  
- Long communication range  
- Good signal penetration  
- Low power consumption  

Typical range:

- 5–15 km in rural areas  
- 2–5 km in urban environments  

---

### LoRaWAN MAC Classes

LoRaWAN devices are divided into **three classes**.

#### Class A

- Default mode  
- Lowest power consumption  
- Two receive windows after transmission  

Best for **battery-powered sensors**.

---

#### Class B

- Scheduled receive windows  
- Gateway sends periodic beacons  
- Enables predictable communication  

---

#### Class C

- Device continuously listens for messages  
- Highest power consumption  
- Suitable for powered devices  

---

### LoRaWAN Security

LoRaWAN uses **two security layers**.

**Network Session Key (NwkSKey)**

- Ensures network-level integrity  
- Protects MAC messages  

**Application Session Key (AppSKey)**

- Ensures end-to-end data encryption  
- Protects application data  

---

## NB-IoT

NB-IoT (Narrowband IoT) is a **licensed LPWA technology developed by 3GPP**.

It operates on **existing cellular infrastructure**.

---

### Features

- Very low power consumption  
- Deep indoor coverage  
- High scalability  
- Long battery life (10+ years)

---

### Applications

- Smart meters  
- Smart parking  
- Environmental monitoring  
- Smart agriculture  

---

## IEEE 802.11ah (Wi-Fi HaLow)

IEEE 802.11ah is a **low-power WiFi standard designed for IoT devices**.

It operates in **sub-GHz frequency bands**, allowing longer range compared to traditional WiFi.

---

### Features

- Extended WiFi coverage  
- Low power consumption  
- Supports thousands of devices  
- Operates below 1 GHz  

---

### Topology

IEEE 802.11ah mainly uses **star topology**.

It also supports **relay hops (maximum two)** to extend network coverage.

---

# 3. IoT Design Methodology

IoT system design follows a **structured methodology** to ensure scalability, reliability, and efficiency.

A widely used **10-step IoT design methodology** is described below.

---

### 1. Purpose & Requirements

Define:

- system goals  
- functional requirements  
- performance constraints  
- cost limitations  

Example: Smart irrigation system to reduce water usage.

---

### 2. Process Model

Define the **workflow of system operations**.

Example:

Sensor → Data Processing → Decision → Actuation.

---

### 3. Domain Model

Identify **all entities in the system**, such as:

- physical devices  
- virtual entities  
- users  
- services  

---

### 4. Information Model

Define how **data is structured and exchanged**.

Example:

{
temperature: 28,
humidity: 65,
timestamp: "2026-03-05"
}


---

### 5. Service Specifications

Define services such as:

- data collection  
- analytics  
- notification  
- control  

---

### 6. IoT Level

Select the **system architecture level**, depending on system complexity.

Examples:

- Device-to-device  
- Device-to-cloud  
- Edge computing architectures  

---

### 7. Functional View

Map system components to **functional groups** such as:

- sensing  
- communication  
- data processing  
- storage  
- application interface  

---

### 8. Operational View

Define operational aspects such as:

- hosting environment  
- cloud platforms  
- communication infrastructure  

---

### 9. Integration

Integrate:

- hardware devices  
- software systems  
- cloud platforms  
- APIs  

---

### 10. Application Development

Develop the **end-user application**.

Examples:

- Mobile apps  
- Web dashboards  
- Monitoring systems  

This final step delivers the **complete IoT solution**.
