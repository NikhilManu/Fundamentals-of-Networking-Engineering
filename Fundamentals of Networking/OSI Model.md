## Open Systems Interconnection Model (OSI)

### Why do we need a communication model ?

#### Agnostic Applications

- Without standard model, the application must have knowledge of the underlying network medium.
- Imagine if you have to author different version of your apps so that it works on Wifi, ethernet, LTE and fiber.

#### Network Equipment Management

- Without standard model, upgrading n/w equipments become difficult

#### Decoupled Innovation

- Innovations can be done in each layer separately without affecting the rest of the models.

### What is the OSI Model?

7 Layers each describe a specific n/w component.

- Layer 7 - Application - HTTP/FTP/gRPC
- Layer 6 - Presentation - Encoding, Serialization
- Layer 5 - Session - Connection establishment, TLS
- Layer 4 - Transport - UDP/TCP
- Layer 3 - Network - IP
- Layer 2 - Data Link - Frames, Mac Address Ethernet
- Layer 1 - Physical - Electric signals, fiber or radio waves

# Ex from perspective of Sender

Sending a POST request to an HTTPS webpage

- Layer 7 - Application
  - POST request with JSON data to HTTPS server
- Layer 6 - Presentation
  - Serlialize JSON to flat byte string
- Layer 5 - Session
  - Request to establish TCP connection/TLS
- Layer 4 - Transport
  - Sends SYN request target port 443
- Layer 3 - Network
  - SYN is placed an IP packet(s) and adds the source/dest IPs
- Layer 2 - Data Link
  - Each packet goes into a single frame and adds the source/dest MAC addresses
- Layer 1 - Physical
  - Each frame becomes string of bits which converted into either a radio, electric or light signal

# Ex from Perspective of Receiver

Receiver compueter receives the POST request the other way round

- Layer 1 - Physical
  - Radio, electric or light is received and converted into digital bits.
- Layer 2 - Data Link
  - The bits from layer 1 is assembled into frames
- Layer 3 - Network
  - The frames from layer 2 are assembled into IP Packets
- Layer 4 - Transport
  - The IP packets from layer 3 are assembled into TCP segments
  - Deals with Congestion control/flow control/retransmission in case of TCP
  - if Segment is SYN we don't need to go further into more layers as we are still processing the connection request
- Layer 5 - Session
  - The connection session is established or identified
  - We only arrive at this layer when necessary (three way handshake is done)
- Layer 6 - Presentation
  - Deserialize flat byte string back to JSON for the app to consume
- Layer 7 - Application
  - Application understands the JSON POST request and your request receive event is triggered.

## ShortComings of the OSI Model

- Too many layers which can be hard to comprehend
- Hard to argue about which layer does what
- Simpler to deal with Layer 5,6,7 as just one layer, Application (TCP/IP does just that)
