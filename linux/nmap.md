common scan
```bash
nmap -sV -sC -p- <target>
```

fast scan(common ports)
```bash
nmap –F 192.168.0.1
```
ports
```bash
nmap –p 1-200 192.168.0.1

```
all ports
```bash
nmap –p– 192.168.0.1
```
To scan using TCP connect (it takes longer, but is more likely to connect):
```bash
nmap –sT 192.168.0.1
```
To perform the default SYN scan (it tests by performing only half of the TCP handshake):
```bash
nmap –sS 192.168.0.1
```
scan UDP ports instead of TCP ports
```bash
nmap –sU –p 80,130,255 192.168.0.1
```
Run a fast scan on the target system, but bypass host discovery
```bash
nmap –Pn –F 192.168.0.1
```
detect the operating system
```bash
nmap –A 192.168.0.1
```
to probe for the services that might be using different ports
```bash
nmap –sV 192.168.0.1
```
---

