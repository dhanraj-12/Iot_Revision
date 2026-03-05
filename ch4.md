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

Essential criteria for selecting and evaluating how smart objects connect to the network.

## Range

- **Short Range**: Maximum distance of tens of meters; often serves as a serial cable replacement. Examples include Bluetooth (IEEE 802.15.1) and Visible Light Communications (VLC).

- **Medium Range**: Distance of tens to hundreds of meters. Includes WiFi (802.11), ZigBee (802.15.4), and Narrowband Power Line Communications (PLC).

- **Long Range**: Distances greater than 1 mile (1.6 km). Includes Cellular (2G/3G/4G), NB-IoT, and LoRaWAN.

## Frequency Bands

- **Licensed**: Spectrum regulated by organizations like the ITU or FCC; users must subscribe to services. Common for Cellular (900–2100 MHz) and NB-IoT (700–900 MHz).

- **Unlicensed (ISM)**: Industrial, Scientific, and Medical bands where no interference protection is guaranteed. Common bands include 2.4 GHz (WiFi, Bluetooth, ZigBee) and 868 MHz (LoRa in India).

## Power Consumption

- **Powered Nodes**: Connected to a direct power source; communication is usually not limited by power constraints.

- **Battery-Powered Nodes**: Small batteries that require recharging or replacement; demands access technologies with very low power consumption to ensure long lifecycles (10+ years).

## Topology

- **Star**: All nodes connect to a central hub; prevalent in long-range and indoor Wi-Fi.

- **Mesh**: Nodes relay data for each other; common in ZigBee and PLC deployments.

- **Peer-to-Peer**: Direct communication between two nodes.

## Constrained Devices (RFC 7228)

- **Class 0**: Extremely resource-limited; < 10 KB RAM and < 100 KB Flash; no IP stack.

- **Class 1**: ~10 KB RAM and ~100 KB Flash; uses an optimized IP stack.

- **Class 2**: > 50 KB RAM and > 250 KB Flash; supports a full IP stack.

---

# 2. IoT Access Technologies (Layer 1 & 2)

## IEEE 802.15.4

- **Overview**: Standard for low-cost, low-data-rate wireless personal area networks (WPAN).

- **Physical Layer (PHY)**: Operates at  
  - 2.4 GHz (250 kbps)  
  - 915 MHz (250 kbps)  
  - 868 MHz (100 kbps)

- **MAC Layer**: Manages channel access and association; uses:
  - Data frames
  - Beacon frames
  - ACK frames
  - Command frames

- **Security**: Uses AES 128-bit encryption and Message Integrity Codes (MIC).

## ZigBee

- **ZigBee PRO**: Built on 802.15.4; features AODV routing over mesh and 128-bit AES encryption at the MAC and network layers.

- **ZigBee IP**: An evolution that adopts open IETF standards like IPv6, 6LoWPAN, and RPL for better interoperability.

## LoRaWAN

- **PHY Layer**: Uses Semtech’s Chirp Spread Spectrum modulation for high robustness against noise.

### MAC Classes

- **Class A**: Default bi-directional communication; highly battery-optimized.

- **Class B**: Adds scheduled receive windows via gateway beacons.

- **Class C**: Node is continuously listening; intended for powered devices.

- **Security**:
  - **Network Session Key (NwkSKey)** → MAC integrity  
  - **Application Session Key (AppSKey)** → End-to-end data privacy

## NB-IoT

- **Overview**: Licensed-band LPWA technology developed by 3GPP.

- **Performance**:
  - Supports 10+ year battery life
  - Improved system capacity
  - Deep indoor coverage

## IEEE 802.11ah (Wi-Fi HaLow)

- **Purpose**: Sub-GHz Wi-Fi for extended range and low-power sensor networks.

- **Topology**: Star topology that supports simple relay hops (maximum 2) to extend range.

---

# 3. IoT Design Methodology

A 10-step process for developing a complete IoT system:

1. **Purpose & Requirements**: Define the goals and system needs.  
2. **Process Model**: Specify the use cases and workflows.  
3. **Domain Model**: Define the physical entities, virtual entities, and devices.  
4. **Information Model**: Structure the relations and attributes of data.  
5. **Service Specifications**: Map processes and data to specific services.  
6. **IoT Level**: Select the system complexity level.  
7. **Functional View**: Map levels to functional groups.  
8. **Operational View**: Define hosting, storage, and communication options.  
9. **Integration**: Integrate devices and develop software components.  
10. **Application Development**: Final creation of the user application.