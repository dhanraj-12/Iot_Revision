# Internet of Things (IoT) – Chapter 1 Notes

## Internet of Things (IoT)

### 1. Introduction to IoT
#### What is Internet
- The Internet is a global network of interconnected computer networks.
- It allows devices to communicate and exchange data using TCP/IP protocols.

#### What are Things
- "Things" are physical objects that can connect to the internet and share data.

##### Sensors
- Devices that detect or measure physical properties like temperature, light, or motion.

##### Computers
- Processing systems that analyze and store data collected from devices.

##### Mobile Devices
- Smartphones and tablets used to interact with IoT systems.

#### Evolution of Internet
- Internet evolved from simple communication networks to a platform connecting billions of smart devices.

#### Kevin Ashton Explanation
- Kevin Ashton introduced the concept of IoT where computers gain the ability to sense the physical world.

---

### 2. Definition of IoT
#### Global Network Infrastructure
- IoT is a worldwide network that connects devices and systems.

#### Self-configuring Capabilities
- Devices automatically configure themselves when connected to the network.

#### Standard Communication Protocols
- IoT devices communicate using standard protocols like HTTP, MQTT, and TCP/IP.

#### Physical and Virtual Things with Identities
- Each IoT device has a unique identity allowing it to be recognized on the network.

---

### 3. IoT Objects / Things
#### Physical Devices
- Real-world objects embedded with sensors and software.

#### Vehicles
- Connected vehicles that share data for navigation and monitoring.

#### Buildings
- Smart buildings that monitor lighting, temperature, and security.

#### Smart Devices
- Devices like smart watches, smart thermostats, and smart TVs.

#### Connected Systems
- Systems where multiple devices communicate to perform tasks automatically.

---

### 4. Sensors and Actuators

#### Sensors
- Devices that measure environmental conditions such as temperature, pressure, humidity, or light.

#### Actuators
- Devices that perform physical actions based on commands.

##### Control Mechanisms
- Used to regulate systems such as motors or valves.

##### Open/Close Valves
- Actuators can control fluid flow in pipelines.

##### Start Motion or Physical Action
- Used to trigger mechanical movements.

---

### 5. IoT Elements
#### Components that form IoT ecosystem
- Devices, networks, software platforms, and applications working together.

---

### 6. Characteristics of IoT

#### Dynamic and Self-adapting
- IoT systems adjust automatically to environmental changes.

#### Self-configuring
- Devices configure themselves when added to a network.

#### Interoperable Communication Protocols
- Different devices communicate using standardized protocols.

#### Unique Identity
- Each IoT device has a unique identifier.

#### Integrated Information Network
- Devices share data within an integrated network system.

---

### 7. Applications of IoT

#### Smart Home
- Automation of lighting, appliances, and security systems.

#### Smart Cities
- Traffic monitoring, waste management, and smart lighting.

#### Environment Monitoring
- Monitoring pollution, temperature, and weather conditions.

#### Energy Management
- Efficient management of electricity consumption.

#### Retail
- Smart inventory management and automated billing.

#### Logistics
- Real-time tracking of goods and delivery systems.

#### Agriculture
- Soil monitoring and automated irrigation systems.

#### Industry
- Industrial automation and predictive maintenance.

#### Health & Lifestyle
- Health monitoring devices and fitness trackers.

---

### 8. Physical Design of IoT

#### IoT Devices
- Devices equipped with sensors and connectivity.

#### Data Exchange Between Devices
- Devices communicate with each other over networks.

#### Data Collection
- Sensors gather environmental or operational data.

#### Cloud Processing
- Data is processed and analyzed in cloud servers.

#### Local Processing
- Some data is processed locally within the device.

---

### 9. Generic Block Diagram of IoT Device

#### Sensor Interfaces
- Connect sensors to the processing unit.

#### Internet Connectivity Interfaces
- Enable communication with the internet.

#### Memory and Storage
- Store collected data and program instructions.

#### Processor
- Executes instructions and processes sensor data.

#### Audio/Video Interfaces
- Used for multimedia input and output.

---

### 10. IoT Protocols

#### Link Layer
- Handles communication between devices in a local network.

##### Ethernet (802.3)
- Wired networking technology.

##### WiFi (802.11)
- Wireless networking technology.

##### WiMAX (802.16)
- Long-range wireless communication technology.

##### LR-WPAN (802.15.4)
- Low-power wireless networks used in IoT.

##### 2G/3G/4G
- Cellular communication networks.

---

#### Network Layer

##### IPv4
- Standard internet addressing system.

##### IPv6
- Advanced addressing system supporting more devices.

##### 6LoWPAN
- Enables IPv6 communication in low-power networks.

---

#### Transport Layer

##### TCP
- Reliable communication protocol.

##### UDP
- Faster but less reliable protocol.

---

#### Application Layer

##### HTTP
- Protocol used for web communication.

##### CoAP
- Lightweight protocol for constrained devices.

##### WebSocket
- Provides real-time communication.

##### MQTT
- Publish–subscribe messaging protocol.

##### XMPP
- Messaging protocol supporting device communication.

##### DDS
- Data distribution protocol for real-time systems.

##### AMQP
- Messaging protocol for distributed applications.

---

### 11. Logical Design of IoT

#### IoT Functional Blocks

##### Device
- Physical devices that collect and send data.

##### Communication
- Mechanisms used to transfer data between devices.

##### Services
- Data processing and analytics services.

##### Management
- Device monitoring and control.

##### Security
- Protection of devices and communication.

##### Application
- User interfaces for controlling IoT systems.

---

#### IoT Communication Models

##### Request-Response
- Client sends request and server responds.

##### Publish-Subscribe
- Devices publish messages and subscribers receive them.

##### Push-Pull
- Data producers push messages to queues and consumers retrieve them.

##### Exclusive Pair
- Persistent connection between two devices.

---

#### IoT Communication APIs

##### REST-based APIs
- Communication using HTTP methods.

##### WebSocket APIs
- Full-duplex communication for real-time interaction.

---

### 12. IoT Enabling Technologies

#### Wireless Sensor Networks
- Networks of sensors collecting and transmitting data.

##### Weather Monitoring
- Tracking weather conditions.

##### Air Quality Monitoring
- Measuring pollution levels.

##### Soil Moisture Monitoring
- Monitoring soil conditions in agriculture.

##### Smart Grids
- Intelligent electricity distribution systems.

##### Structural Monitoring
- Monitoring infrastructure safety.

---

#### Cloud Computing

##### IaaS
- Provides virtualized computing resources.

##### PaaS
- Provides development platforms.

##### SaaS
- Provides software applications over the internet.

---

#### Big Data Analytics

##### Sensor Data
- Data collected from sensors.

##### Machine Data
- Data generated by industrial machines.

##### Health Data
- Medical monitoring data.

##### Location Data
- GPS and tracking information.

##### Inventory Data
- Product tracking and stock management.

---

#### Communication Protocols

##### Data Exchange Rules
- Standards for transmitting data.

##### Flow Control
- Managing data transmission rates.

##### Retransmission
- Resending lost data packets.

---

#### Embedded Systems

##### Digital Watches
- Embedded computing devices.

##### Cameras
- Devices with built-in processors.

##### POS Terminals
- Payment processing devices.

##### Smart Appliances
- Connected home appliances.

---

### 13. IoT System Components

#### Device
- Hardware collecting data.

#### Resource
- Software components managing device data.

#### Controller Service
- Controls device operations.

#### Database
- Stores IoT data.

#### Web Service
- Enables communication between systems.

#### Analysis Component
- Processes and analyzes collected data.

#### Application
- Interface for user interaction.

---

### 14. IoT Levels

#### Level 1
- Single device performing sensing and processing.

#### Level 2
- Device with cloud-based storage and application.

#### Level 3
- Cloud-based storage and analytics.

#### Level 4
- Multiple devices with local analysis and cloud storage.

#### Level 5
- Multiple sensors with coordinator node.

#### Level 6
- Large-scale IoT system with cloud analytics and centralized control.

---

### 15. Convergence of IT and OT

#### IT (Information Technology)
- Manages data processing and communication systems.

#### OT (Operational Technology)
- Controls industrial devices and processes.

#### Integration through IoT
- IoT connects IT systems with operational devices.

---

### 16. IoT Challenges

#### Scale
- Managing billions of connected devices.

#### Security
- Protecting devices and data from attacks.

#### Privacy
- Protecting sensitive user information.

#### Big Data
- Handling large volumes of generated data.

#### Interoperability
- Ensuring devices from different manufacturers work together.

---

### 17. IoT Network Architecture and Design

#### Data Transport
- Transmitting data across networks.

#### Data Collection
- Gathering information from sensors.

#### Data Analysis
- Processing data to extract useful insights.

#### Action on Data
- Taking automated decisions based on analyzed data.

---

### 18. IoT Architectures

#### oneM2M Architecture

##### Application Layer
- Interfaces connecting applications with IoT systems.

##### Services Layer
- Middleware providing common services.

##### Network Layer
- Communication infrastructure.

---

#### IoTWF Architecture

##### Layer 1 – Physical Devices
- Sensors and actuators generating data.

##### Layer 2 – Connectivity
- Network connections between devices.

##### Layer 3 – Edge Computing
- Local data processing near devices.

##### Layer 4 – Data Accumulation
- Data storage systems.

##### Layer 5 – Data Abstraction
- Data processing and formatting.

##### Layer 6 – Application
- User-facing applications.

##### Layer 7 – Collaboration & Processes
- Business processes and decision making.

---

### 19. Simplified IoT Architecture

#### Core IoT Functional Stack

##### Things Layer
- Physical smart devices.

##### Communication Network Layer

###### Access Network
- Connects devices to the gateway.

###### Gateway & Backhaul
- Transfers data from devices to central servers.

###### Network Transport
- Protocols handling data transfer.

###### IoT Network Management
- Manages device communication and operations.

---

#### IoT Data Management and Compute Stack

##### Edge Layer
- Processing near sensors.

##### Fog Layer
- Intermediate data processing.

##### Cloud Layer
- Centralized data storage and analytics.

---

### 20. IoT Communication Protocols

#### HTTP
- Web-based communication protocol.

#### WebSocket
- Real-time communication protocol.

#### XMPP
- Messaging protocol for distributed systems.

#### CoAP
- Lightweight protocol for constrained devices.

#### MQTT
- Publish-subscribe messaging protocol used in IoT.
