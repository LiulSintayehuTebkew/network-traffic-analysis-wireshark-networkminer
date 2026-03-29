# Wireshark Display Filters — SOC Analyst Reference

## Protocol Filters
- `ip`                         — all IP traffic
- `tcp`                        — all TCP traffic
- `udp`                        — all UDP traffic
- `dns`                        — all DNS traffic
- `http`                       — all HTTP traffic
- `tls`                        — all TLS/HTTPS traffic
- `smb` or `smb2`              — SMB file sharing traffic
- `ftp`                        — FTP traffic
- `icmp`                       — ICMP ping traffic

## HTTP Filters
- `http.request`               — HTTP requests only
- `http.response`              — HTTP responses only
- `http.request.method == "POST"` — POST requests only
- `http.request.method == "GET"`  — GET requests only
- `http.user_agent`            — show User-Agent field
- `http.response.code == 200`  — successful responses
- `http.response.code == 404`  — not found responses

## DNS Filters
- `dns.qry.name`               — DNS query names
- `dns.flags.response == 0`    — DNS queries only
- `dns.flags.response == 1`    — DNS responses only

## TLS Filters
- `tls.handshake.type == 1`    — TLS Client Hello
- `tls.handshake.extensions_server_name` — SNI field

## IP and Port Filters
- `ip.addr == 192.168.1.1`     — traffic to or from specific IP
- `ip.src == 192.168.1.1`      — traffic FROM specific IP
- `ip.dst == 192.168.1.1`      — traffic TO specific IP
- `tcp.port == 80`              — traffic on port 80
- `tcp.dstport == 443`          — destination port 443
- `not ip.addr == 192.168.1.1`  — exclude specific IP

## TCP Flags
- `tcp.flags.syn == 1 and tcp.flags.ack == 0` — SYN only (scan)
- `tcp.flags.rst == 1`         — RST packets (rejected connections)
- `tcp.analysis.retransmission` — retransmitted packets

## DHCP
- `dhcp`                        — DHCP traffic (find hostnames)
- `dhcp.option.hostname`        — DHCP hostname field

## Combining Filters
- `ip.src == 10.0.0.1 and http`        — HTTP from specific IP
- `dns and ip.addr == 8.8.8.8`         — DNS through Google
- `http and not ip.addr == 192.168.1.1` — HTTP excluding one IP

## Follow Stream
- Right-click any packet → **Follow → TCP Stream**
- Right-click any packet → **Follow → HTTP Stream**
- Right-click any packet → **Follow → TLS Stream**
