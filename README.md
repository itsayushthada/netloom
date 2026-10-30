# netloom# netloom

> Weaving cloud networking from raw Linux primitives — one thread at a time.

A hands-on, local-first learning path for cloud networking. No cloud account needed.
Everything runs on your machine using Docker, Linux namespaces, and open-source tools.

## Philosophy

Cloud networking isn't magic. It's Linux networking with a GUI.
This repo proves it by rebuilding every cloud concept from scratch using
`ip netns`, `nftables`, bridges, veth pairs, and standard open-source tools.

## Prerequisites

- Linux (Ubuntu 22.04+ recommended)
- Docker + Docker Compose
- Basic shell comfort
- Optional: VirtualBox (for Level 6 hybrid labs)

## Tools Used

| Tool | Role |
|------|------|
| Docker | Runtime for all containers |
| vpclab + Floci | AWS VPC networking simulation (Levels 2–3) |
| LocalStack | AWS service API emulation (supplementary) |
| ip netns / nftables / bridges | Raw Linux networking (Level 1, DIY VPC) |
| haproxy | Load balancing (Level 4) |
| dnsmasq / BIND9 | DNS (Level 4) |
| nginx / varnish | TLS, CDN simulation (Level 4–5) |
| suricata | IPS/IDS (Level 5) |
| strongswan / libreswan | IPsec VPN (Level 3, 6) |
| FRR (Free Range Routing) | BGP, routing protocols (Level 6–7) |
| linkerd | Service mesh (Level 7) |
| Terraform | Infrastructure as Code (Level 7) |
| tcpdump / wireshark | Packet analysis (all levels) |

## The Path

### Level 1: Foundations
*IP addressing, subnetting, TCP/IP, DNS, basic tools*

- [ ] Subnetting practice (CIDR, VLSM, host calculation)
- [ ] IP routing with `ip netns` + veth pairs
- [ ] Packet capture: `tcpdump` + Wireshark (TCP handshake, DNS query)
- [ ] DNS deep-dive: `dig`, `dnsmasq` as local resolver
- [ ] Port scanning: `nmap` on your own machine
- [ ] Firewall basics: `nftables` allow/deny rules

### Level 2: Virtual Networking (VPC)
*Building a VPC from scratch, then with vpclab*

- [ ] DIY VPC: bridge + namespaces + NAT + nftables SGs
- [ ] Security Groups simulation (stateful, per-instance)
- [ ] NACLs simulation (stateless, per-subnet)
- [ ] vpclab + Floci: full AWS CLI VPC workflow
- [ ] Route tables: custom routes, propagation
- [ ] NAT Gateway: outbound-only internet access

### Level 3: Connectivity
*Connecting networks together*

- [ ] VPC Peering (1-to-1, non-transitive)
- [ ] Transit Gateway (hub-spoke, 3+ VPCs)
- [ ] Site-to-site VPN: `strongswan` IPsec tunnel
- [ ] NAT Gateway (built with `iptables` MASQUERADE)
- [ ] VPC Endpoints (private access via DNS override + MinIO)

### Level 4: DNS & Traffic Management
*Making things reachable and fast*

- [ ] Run your own DNS: `dnsmasq` zone + records
- [ ] L4 Load Balancer: `haproxy` TCP mode
- [ ] L7 Load Balancer: `haproxy` HTTP mode (path-based routing)
- [ ] Health checks + automatic failover
- [ ] CDN simulation: `varnish` / `nginx` caching proxy
- [ ] Health-based DNS routing (Route 53 equivalent)

### Level 5: Security
*Protecting the network*

- [ ] Network firewall: `suricata` inline IPS
- [ ] DDoS simulation + rate limiting
- [ ] TLS termination: `nginx` as ALB equivalent
- [ ] Flow logs: `tcpdump` → parse → analyze
- [ ] PrivateLink simulation (service exposure without peering)

### Level 6: Hybrid & Multi-Cloud
*Connecting on-prem to cloud*

- [ ] Hybrid VPN: local machine ↔ vpclab VPC (IPsec)
- [ ] BGP on VPN: `FRR` dynamic routing over tunnel
- [ ] SD-WAN simulation: policy-based routing across branches
- [ ] Cloud-bursting: local + remote behind single LB
- [ ] DR setup: primary + replica + failover script

### Level 7: Advanced
*Enterprise-grade patterns*

- [ ] BGP lab: `FRR` — AS path, prefix filtering, route reflection
- [ ] Anycast: two nodes advertising same IP
- [ ] Service mesh: `linkerd` — mTLS, canary, traffic splitting
- [ ] IPv6 dual-stack VPC
- [ ] Terraform: VPC + subnets + SGs + NAT as code

### Level 8: Specialized
*Cutting edge*

- [ ] High-throughput: `iperf3` benchmarks, `io_uring`
- [ ] Zero trust: per-service identity, short-lived certs
- [ ] NFV: firewall as container in datapath, horizontal scaling

## Repo Structure
   
