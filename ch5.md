# Cloud Computing & IoT Infrastructure Tree Diagram

* **I. Introduction to Cloud Computing**
    * **Definition**: Service provisioning technique where resources (hardware, software, platforms) are provided as a service by providers to customers.
    * **Key Features**:
        * **Elasticity**: Flexible nature allowing users to scale resources up or down as needed.
        * **Pay-per-use**: Metered usage where users pay only for the resources consumed.
        * **Reduced Capital Cost**: Eliminates the need to invest in purchasing and maintaining physical infrastructure.
        * **Remote Accessibility**: Access to applications and data from anywhere via internet-enabled devices.

* **II. Cloud Service Models**
    * **Infrastructure-as-a-Service (IaaS)**
        * Service provider owns hardware (Servers, Storage, Network) and provides it to clients.
        * Examples: Amazon EC2, Google Compute Engine, Azure VMs.
    * **Platform-as-a-Service (PaaS)**
        * Provides complete resources to Design, Develop, Test, Deploy, and Host applications.
        * Extension of IaaS; includes software and configuration required to create applications.
        * Example: Google App Engine.
    * **Software-as-a-Service (SaaS)**
        * Service provider delivers software over the Internet.
        * Eliminates the need for local installation, maintenance, and licensing.
        * Examples: Google Docs, Salesforce, CRM.

* **III. Cloud Deployment Models**
    * **Public Cloud**: Services and infrastructure hosted off-site and accessible to the general public via the internet.
    * **Private Cloud**: Operated for a single organization; offers a greater level of security.
    * **Community Cloud**: Infrastructure accessible by a specific group of organizations.
    * **Hybrid Cloud**: A mixture of private and public clouds (sensitive data in private, non-critical in public).

* **IV. Cloud Concepts & Technologies**
    * **Virtualization**
        * Partitioning physical system resources (computing, storage, memory) into virtual resources.
        * **Hypervisor (VMM)**: Software that sits between hardware and OS to assign resource access.
        * **Types of Hypervisors**:
            * **Type-1 (Native)**: Runs directly on host hardware.
            * **Type-2 (Hosted)**: Runs on top of a conventional operating system.
        * **Approaches**: Full Virtualization (unmodified Guest OS), Para-Virtualization (modified Guest OS), and Hardware-Assisted.
    * **Software Defined Networking (SDN)**
        * Decouples the Control Plane (making traffic decisions) from the Data Plane (packet forwarding).
        * Enables centralized, programmable management of the entire network via software.
    * **MapReduce**
        * Parallel processing technique for analyzing large-scale data.
        * **Map Phase**: Breaks data down into key/value tuples.
        * **Reduce Phase**: Combines map output tuples into a smaller set of tuples.

* **V. Sensor-Cloud Architecture**
    * Paradigm shift from Wireless Sensor Networks (WSN) to virtualized sensing.
    * **Actors and Roles**:
        * **End-users**: Request Sensing-as-a-Service (Se-aaS) through web portals.
        * **Sensor-owner**: Purchases/deploys physical sensors and lends them to the provider.
        * **SCSP (Sensor-Cloud Service Provider)**: Manages virtualization, pricing, and composition.
    * **Management Solutions**:
        * **Data Caching**: Storing sensed data to prevent unnecessary sensing and save energy.
        * **Virtual Sensor Composition**: Optimal formation of virtual sensor groups.

* **VI. Fog Computing**
    * Intermediate layer between Cloud and Devices to extend services closer to the network edge.
    * **Objectives**: Solve Cloud issues regarding Volume, Latency, and Bandwidth.
    * **Working Hierarchy**:
        * **Nearest Fog Node**: Analyzes most time-sensitive data (fractions of a second).
        * **Aggregate Fog Node**: Analyzes less time-sensitive data (seconds to minutes).
        * **Cloud**: Used for non-time-sensitive data and historical analysis (hours to weeks).

* **VII. Cloud-Based Applications**
    * **Healthcare**: Real-time monitoring for chronic illness/stroke patients and secure data sharing.
    * **Energy Systems**: Monitoring smart grids and wind turbines for failure prediction.  

    # Cloud Computing & IoT Detailed Notes

* **I. Introduction to Cloud Computing**
    * **Definition**: A service provisioning technique where computing resources like hardware (servers, storage), software, and platforms are provided as a service by providers to customers.
    * **Elasticity**: The flexible nature of the cloud allows users to scale resource capacities up or down dynamically based on requirements.
    * **Pay-per-use**: Computing usage is metered, and customers only pay for the specific amount of resources used.
    * **Capital Cost Reduction**: Users do not need to invest money to purchase, manage, or scale physical infrastructure and software licenses.
    * **Remote Accessibility**: Applications and data stored in the cloud can be accessed from anywhere at any time through internet-connected devices.

* **II. Cloud Service Models**
    * **Infrastructure-as-a-Service (IaaS)**
        * The provider owns hardware (Servers, Storage, Network), and the client pays to use these on a per-use basis.
        * Examples include Amazon Elastic Compute (EC2), Google Compute Engine, and Azure VMs.
    * **Platform-as-a-Service (PaaS)**
        * Provides all resources needed to design, develop, test, deploy, and host applications without hardware maintenance costs.
        * It is an extension of IaaS that includes the software and configurations required to create applications.
        * Example: Google App Engine (GAE).
    * **Software-as-a-Service (SaaS)**
        * Software is provided as a service over the internet, eliminating local installation and licensing needs.
        * Application logic runs in the cloud rather than on the user's computer.
        * Examples: Google Docs, Salesforce (Sales/Service/Marketing Clouds).



* **III. Cloud Deployment Models**
    * **Public Cloud**: Services and infrastructure are hosted off-site by a provider and are easily accessible to the general public via the internet.
    * **Private Cloud**: Operated for a single organization, accessible via a private network, and managed internally or by a third party for higher security.
    * **Community Cloud**: Infrastructure and services are shared and accessible by a group of specific organizations.
    * **Hybrid Cloud**: A mixture of private and public clouds; critical data is stored in the private cloud, while non-critical data is stored in the public cloud.

* **IV. Cloud Concepts & Technologies**
    * **Virtualization**
        * The technology of partitioning a physical system's resources (CPU, Memory, Network) into multiple virtual resources.
        * **Hypervisor (VMM)**: Software that sits between the hardware and the OS to assign resource access.
        * **Type-1 vs Type-2**: Type-1 runs directly on hardware; Type-2 runs on top of a host operating system.
        * **Approaches**: Full Virtualization (unmodified Guest OS), Para-Virtualization (modified Guest OS kernel), and Hardware-Assisted (uses Intel VT-x/AMD-V).
    * **Software Defined Networking (SDN)**
        * SDN separates the control plane (traffic decisions) from the data plane (packet forwarding).
        * This allows the entire network behavior to be programmed in a centrally controlled manner using software applications and APIs.
    * **MapReduce**
        * A parallel processing model for analyzing large-scale data.
        * **Map Phase**: Breaks data into tuples (key/value pairs).
        * **Reduce Phase**: Combines map output tuples into a smaller, meaningful set.



* **V. Sensor-Cloud Architecture**
    * **Paradigm Shift**: Moves away from traditional Wireless Sensor Networks (WSN) where data is "dumped" to a model where sensor nodes are virtualized resources.
    * **Key Actors**:
        * **End-users**: Request Sensing-as-a-Service (Se-aaS) without knowing which physical sensors are allocated to them.
        * **Sensor-owner**: Purchases hardware and lends it to the provider (SCSP).
        * **SCSP**: Manages the virtualization layer, pricing, and resource composition.
    * **Management**: Includes optimal composition of virtual nodes and data caching to save sensor energy by preventing unnecessary sensing.

* **VI. Fog Computing**
    * **Purpose**: Extends cloud services closer to IoT devices to handle the huge volume of data and reduce latency.
    * **Hierarchy of Analysis**:
        * **Nearest Fog Node**: Analyzes most time-sensitive data in fractions of a second (e.g., immediate accident prevention).
        * **Aggregate Fog Node**: Processes data that can wait seconds to minutes.
        * **Cloud**: Used for non-time-sensitive data and long-term historical analysis (hours to weeks).



* **VII. Applications**
    * **Healthcare**: Real-time monitoring of stroke patients to alert doctors during emergencies and historical data analysis for future risk prediction.
    * **Energy Systems**: Industrial machines and smart grids use sensors to gather maintenance data for condition monitoring and failure prediction (e.g., CloudView framework).