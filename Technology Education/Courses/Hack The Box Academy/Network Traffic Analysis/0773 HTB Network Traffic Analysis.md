# Network Traffic Analysis

Network Traffic Analysis ( #NTA) involves packet capture from network traffic and has several uses:

- Port Characterization
- Protocol Characterization
- Establishing Environment Baselines
- Threat Monitoring
- Threat Response
- Network Insights
- Collecting Traffic Data
- Anomaly Identification
- Malware Detection
- Investigating Past Incidents

A use example for NTA is detecting a flood of SYN packets of an unused port to identify a portscan performed by a threat agent.

### Required Skills and Knowledge

A general and well-rounded understanding of the following topics would benefit anyone performing network traffic analysis.

- #TCP/IP and #OSI Model function
- Network Concepts like switching and routing
- Common Ports and Protocols
- IP Packet Composition
- TCP and UDP
- Sublayers
- Layer Encapsulation or Protocol Transport Encapsulation

### Tools

| Tool                  | Description                                                                                                                                                                  |
| --------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| tcpdump               | command-line tool that captures packets or files in LibPcap form                                                                                                             |
| Tshark                | command-line variant of Wireshark                                                                                                                                            |
| Wireshark             | Graphical network analyzer with many analytic tools                                                                                                                          |
| NGrep                 | pattern-matching tool for packet capture, similar to grep. Uses PCAP files, regex, and BPF syntax to evaluate packets and protocols                                          |
| tcpick                | command-line packet capture tool for tracking and reassembling TCP data streams                                                                                              |
| Network Taps          | devices that capture packets and send them to other devices. In-line or out-of-band options available. They are passive as they replace the packet after capturing it        |
| Networking Span Ports | capies frames from layer 2 or 3 devices during egress or ingress processing and funnel them to a collection device. Often uses port mirroring to forward data to log servers |
| Elastic Stack         | a set of tools that collect data from many sources, ingest them, depict them, and provide searching and analysis of this data                                                |
| SIEM Tools            | tools like Splunk that centralize data for analysis and visualization. Performs functions of alerting, forensic analysis, and traffic monitoring                             |

### BPF

Berkeley Packet Filter ( #BPF) syntax is a common syntax among tools related to network traffic. This language allows interfaces to read and write from the Data-Link layer offering filtering and decoding. Most command-line tools support this syntax which is described in detail [here](https://www.ibm.com/docs/en/qsip/7.4?topic=queries-berkeley-packet-filters 'detailed information about BPF syntax').

### Workflow

Network Traffic Analysis is a dynamic process with no linear order. Process is influences by the circumstances of each instance and deciding our goals while performing it.

A basic and flexible workflow for NTA is as follows:

1. Traffic Ingestion
	- Capturing traffic and implementing filters if target data is known.

2. Noise Reduction 
	- Traffic analysis can be noisy in a busy environment. After the initial capture, use filtering techniques to reduce the amount of traffic analyzed.

3. Analyze and Explore
	- Look at specific hosts, protocols, headers, and flags to determine more information.
	- Ask the following questions:
		- Is traffic ciphertext or plaintext, and is this expected?
		- Are users accessing restricted resources?
		- Are hosts making unusual communications?

4. Detect Root Issues
	- Are there errors or unresponsive devices?
	- Analyze traffic and determine benign vs malicious content.
	- Review IDS or IPS logs, run heuristics and signatures against traffic.

5. Repair and Monitor
	- Repair any known issues and continue to monitor the traffic for anomalies.