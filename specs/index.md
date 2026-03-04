---
layout: docs
doc_title: Marlowe Tech Specs
permalink: /documentation/specs/
---

Marlowe consists of a 1SU (Scalable Unit) NVIDIA DGX H100 SuperPOD.
One H100 Scalable Unit is 31 NVIDIA DGX H100 servers.

Compute power: 11.1 PFlops.

## DGX H100 Specs

Each DGX H100 has:

- 2 x Intel Xeon Platinum 8480C
- 8 x NVIDIA H100 80GB
- 2TB Memory
- 400G NICs for fast data access

## Networking

Marlowe consists of four main networks:

- 400Gb InfiniBand compute network to connect all compute nodes together
- 400Gb InfiniBand storage network to connect all compute nodes to the DDN ExaScaler scratch storage
- 100Gb Ethernet network to connect to DDN IntelliFlash storage (used for home and project directories)
- 100Gb Ethernet network to connect to the campus network (SUNet) and the outside world

## Storage

- 2.5PB of DDN ExaScaler Lustre storage
- 3PB of DDN IntelliFlash storage
