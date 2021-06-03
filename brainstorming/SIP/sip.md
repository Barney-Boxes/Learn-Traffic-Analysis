# VoIP & SIP 

What are PBX systems?  

What is the SIP protocol?  
- Session Initiation Protocol (SIP)
- RFC 3261
- Exists at the Application layer
  - creates, manages, & terminates sessions between 2 or more participants.
  - can make use of UDP, TCP (5060), & TLS over TCP (5061)
- Isn't always synonymous with VoIP, regularly uses Real-time Transport Protocol (RTP) for delivery of Voice, and Session Discription Protocol (SDP) for initializing the RTP stream.
 
How does SIP work?  
- CIA Triad considerations
  - Phone Taps
  - MitM attacks
- Tracing SIP packets
- Acts as an intermediary protocol to help 
- Simple Traversal of UDP over NAT (STUN)

What does SIP look like?
- SIP looks like HTTP, has header, body, consists of printable chars, & supports various methods.
- SIP request methods look like ` INVITE, REGISTER, OPTIONS, BYE, CANCEL `
- SIP borrows the SMTP `TO` & `FROM` headers, as well as message formatting.

Why is SIP targeted?  
- Isnt just calls, can also be Multimedia disto, conferences, IM's, & online games. 

How is SIP targeted?  
- Example attacks
- Examples of Targets/weakpoints

Why SIP/VoIP vs PBX?  

How to Prevent/Mitigate Security issues with SIP/VoIP systems.

Describe SIP architecture devices
- SIP Proxies (Stateful & Stateless)
- Registrars
  - Handles & processes a REGISTER request, keeps DB of addresses mapped to specific UA clients or clients
- Redirect Servers

## Lab Scenarios
1. 2 UA clients connected directly
2. 2 UA clients connected via SIP Proxy (stateful), All in one
3. 2 UA clients connected via SIP Proxy (stateless), All in one
4. 2 UA clients connected via Redirect Server, SIP Proxy, Registrar
5. Setting up and using SIPvicious
6. Setting up and using eyeBeam

## Attacks
### 
