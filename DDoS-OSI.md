# DoS and DDoS Attacks by OSI Layer

This document provides a structured overview of common and historically
observed Denial-of-Service (DoS) and Distributed Denial-of-Service
(DDoS) attack types, mapped approximately to the OSI and TCP/IP layers.
Some techniques span multiple layers, and the mapping is therefore
indicative rather than strict.

This reference is organized for:

-   IoT security testing
-   Network hardening
-   Threat modeling
-   Security documentation and reporting

## Summary: DoS by OSI Layer

### Layer 1 --- Physical Layer DoS

-   Wired physical-layer DoS
-   Wireless physical-layer DoS

### Layer 2 --- Data Link Layer DoS

-   Ethernet/MAC DoS
-   ARP-based DoS
-   VLAN and switching DoS
-   Wireless Layer 2 DoS

### Layer 3 --- Network Layer DoS

-   IP flooding
-   Routing protocol DoS
-   IPv6-specific DoS
-   Reflection and amplification (Layer 3/Layer 4 hybrid)

### Layer 4 --- Transport Layer DoS

-   TCP-based DoS
-   UDP-based DoS
-   SCTP, QUIC, and other transport-protocol attacks

### Layer 5 --- Session Layer DoS

### Layer 6 --- Presentation Layer DoS

### Layer 7 --- Application Layer DoS

-   HTTP/HTTPS DoS
-   DNS DoS
-   Email service DoS
-   Authentication service DoS
-   Database DoS
-   IoT/OT protocol DoS

## Distributed DoS (DDoS) Techniques

DDoS techniques can operate across multiple OSI layers.

### Botnet-Based and Amplification Attacks

-   Mirai-style IoT botnet flooding
-   Memcached amplification
-   DNS amplification
-   NTP amplification
-   SSDP amplification
-   CLDAP amplification
-   CHARGEN amplification

### Multi-Vector DDoS

-   Simultaneous SYN and HTTP flooding
-   Layer-switching or multi-layer attacks
-   Carpet-bombing attacks

## Resource-Exhaustion Categories

Resource exhaustion is independent of the OSI layer being targeted.

### CPU Exhaustion

-   TLS cryptographic-processing exhaustion
-   Regular-expression (regex) backtracking attacks
-   Hash-collision CPU exhaustion

### Memory Exhaustion

-   Buffer exhaustion
-   Session-cache exhaustion
-   Kernel-memory exhaustion

### Storage Exhaustion

-   Log flooding
-   Disk-space exhaustion
-   Queue saturation

### Thread and Process Exhaustion

-   Fork bombs
-   Thread-pool exhaustion
-   Container resource starvation

## IoT-Specific DoS Attacks

-   Over-the-air (OTA) update flooding
-   Firmware-downgrade loop triggering
-   Discovery-protocol flooding
-   MQTT broker exhaustion
-   mDNS flooding
-   SSDP flooding
-   Host/guest role-flapping attacks
-   Replay-triggered state instability
-   Keepalive starvation
-   Battery-drain attacks
-   Sensor-polling floods
-   Bluetooth Low Energy (BLE) pairing exhaustion
-   Zigbee association flooding
-   CAN bus dominant-bit DoS
-   Modbus request flooding or register-operation abuse
-   Industrial gateway overload

## Protocol-State Manipulation DoS

These attacks target protocol logic or state machines.

-   Replay-induced state desynchronization
-   Election manipulation
-   Token exhaustion
-   Sequence-number desynchronization
-   Keepalive spoofing
-   Heartbeat flooding
-   State-machine deadlock triggering
-   Protocol-downgrade abuse

## Permanent or Semi-Permanent DoS (PDoS / "Phlashing")

These attacks can damage firmware, configuration, or storage and may
leave a device unusable until it is recovered or replaced.

-   Corrupt firmware flashing
-   Bootloader corruption
-   EEPROM overwrite
-   Filesystem corruption
-   Configuration wiping
-   Unsafe OTA update abuse
-   Secure-boot corruption
-   Flash-memory wear-out attacks

## Cloud and Modern Infrastructure DoS

### Containers and Kubernetes

-   Pod exhaustion
-   Kubernetes API flooding
-   etcd resource exhaustion
-   Service-mesh flooding

### Cloud Services

-   API gateway exhaustion
-   Lambda/serverless invocation flooding
-   CDN cache-bypass flooding

## AI/ML Service DoS

-   Prompt flooding
-   Token exhaustion
-   GPU-memory exhaustion
-   Model-inference flooding
-   Vector-database query exhaustion

## Common DoS Classification by Technique

  -----------------------------------------------------------------------
  Technique | Example
  ----------------------------------- -----------------------------------
  Flooding                   ------------------- SYN flood

  Amplification            -------------------             DNS amplification

  Reflection                  -------------------             NTP reflection

  Resource exhaustion  -------------------           Session exhaustion

  Protocol abuse           -------------------           Rapid Spanning Tree Protocol (RSTP)  topology-change abuse

  Parsing abuse              -------------------         XML entity-expansion or other XML parsing exhaustion

  State manipulation      -------------------            Replay-induced state desynchronization

  Algorithmic complexity  -------------------            Regex-based denial of service (ReDoS)

  Permanent corruption -------------------  Firmware "phlashing"
  -----------------------------------------------------------------------

## Important Note

> **Caution:** Not every technique listed is practical against modern,
> hardened systems. Some are historical, partially mitigated,
> vendor-specific, or dependent on a particular misconfiguration or
> implementation weakness.

This overview is intended as a taxonomy for threat modeling, authorized
penetration-test planning, IoT assessment matrices, and security
test-case preparation. The presence of a technique in this list does not
mean that a particular device is vulnerable to it. Testing should be
authorized, scoped, and performed with safeguards to avoid disrupting
production systems.
