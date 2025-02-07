# Analyze-Network-Attacks


## Section 1: Identifying the Type of Attack

One potential explanation for the **website’s connection timeout error** is a **Denial of Service (DoS) attack**.  
The logs indicate that the **web server stops responding** after being **overloaded with SYN packet requests**.  
This suggests that the attack could be a specific type of **DoS attack** known as **SYN flooding**.

---

## Section 2: How the Attack Causes Website Malfunction

When website visitors attempt to establish a connection with the web server, a **three-way handshake** occurs using the **TCP protocol**. The handshake consists of the following steps:

1. **SYN Packet** – The visitor’s machine (source) sends a **SYN** request to the web server (destination) to initiate a connection.
2. **SYN-ACK Packet** – The web server replies with a **SYN-ACK**, acknowledging the request and reserving system resources.
3. **ACK Packet** – The visitor’s machine sends an **ACK** to confirm the connection, completing the handshake.

### **How the SYN Flood Attack Works**
In a **SYN flood attack**, a **malicious actor** sends **a large number of SYN packets** all at once.  
- The web server **reserves resources** for each connection but **never receives the final ACK packet**.  
- This **exhausts the server’s resources**, preventing it from handling legitimate connections.  

### **Impact on the Website**
- **Server Overload:** The logs indicate that the web server is **overwhelmed** and cannot process new connection requests.
- **Connection Failures:** Legitimate visitors are unable to establish a connection, receiving **connection timeout errors**.

This analysis confirms that a **SYN flood attack** is likely responsible for the website’s **service disruption**.

---

By analyzing the network logs and understanding TCP handshake behavior, we can **detect, prevent, and mitigate SYN flood attacks** to restore service availability.
