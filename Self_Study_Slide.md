# Overview: This slide gives a brief introduction about **Ping** and **Traceroute** Network Diagnotics Utilities.

## About Ping - Network Diagnostic Utility

**Ping** is a widely used network diagnostic utility designed to test the connectivity between two devices on a network. It operates by sending a series of Internet Control Message Protocol (ICMP) Echo Request packets to a target device and receiving ICMP Echo Reply packets in response.

## How Ping Works

1. **ICMP Echo Request:** A device sends an ICMP packet to a specified IP address or hostname.
2. **Echo Reply:** If the target is reachable, it responds with an ICMP Echo Reply packet.
3. **Latency Measurement:** Ping calculates the time taken for the round trip (request and reply) and displays it in milliseconds.
4. **Packet Loss:** If some packets fail to reach the target or return, it indicates potential network issues.

## Key Metrics Provided by Ping

1. **Latency (Round-Trip Time):** Measures the time (in milliseconds) for a packet to travel to the target and back.
2. **Packet Loss:** Indicates how many packets failed to reach the destination or return.
3. **TTL (Time To Live):** The remaining "hops" (routers or devices) a packet can traverse before being discarded.

## Common Uses of Ping

1. **Check Connectivity:** Verify if a device, server, or website is reachable.
   **Example: ping google.com**
2. **Measure Network Performance:** Identify latency issues between devices.
3. **Troubleshoot Network Problems:** Determine if packet loss or delays are causing issues.
4. **Identify Routing Problems:** Analyze delays across different network nodes.
