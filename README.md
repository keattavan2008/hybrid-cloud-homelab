# hybrid-cloud-homelab

🏛️ Project Title: Hybrid Cloud & AI Digital Twin Architecture
Executive Summary: A sophisticated, self-hosted hybrid cloud simulation designed to replicate real-world Enterprise Modernization scenarios. This architecture integrates legacy Windows ecosystems with modern Linux-based microservices, focusing on Zero Trust Security, Polyglot AI Development, and Cloud-Native Observability.

🏗️ Architectural Breakdown
1. Infrastructure Layer (The Private Cloud)
Hosted on a Raspberry Pi 5 (Ubuntu 25.x), serving as an on-premise data center.

Infrastructure as Code (IaC): All services are defined and deployed via Docker Compose stacks managed by Portainer, allowing for instant disaster recovery and version-controlled configuration.

Zero Trust Networking: The environment is completely isolated from the public internet. Access is strictly controlled via a WireGuard VPN tunnel.

Ingress Controller: Nginx Reverse Proxy manages traffic routing, SSL termination, and load balancing for backend services.

DNS & Privacy: AdGuard Home paired with Unbound functions as a recursive DNS resolver, providing enterprise-grade traffic filtering and caching.

2. Application Layer (Legacy Modernization & Hybrid Strategy)
A demonstration of bridging the gap between legacy desktop applications and modern cloud microservices.

The "Migration" Pattern (C#/.NET):

Frontend: A Windows Forms (.NET Framework 4.8) application modernised with embedded WebView2 controls for rich UI capabilities.

Backend: A decoupled .NET 8 Core API handling business logic, simulating a cloud-native microservice.

The Bridge: Business entities shared via a .NET Standard 2.0 library, proving backward compatibility between legacy and modern frameworks.

The "AI Native" Pattern (Python):

A lightweight Streamlit RAG application consuming the same vector data sources, demonstrating a polyglot architecture (C# and Python co-existing).

3. Data & AI Layer (The Intelligence)
A distributed data mesh supporting both transactional and semantic search workloads.

Vector Database: Qdrant stores high-dimensional embeddings for the RAG (Retrieval-Augmented Generation) applications.

Relational Database: MariaDB handles standard transactional data.

Edge Computing: Azure SQL Edge runs containerized to simulate IoT/Edge data collection scenarios compatible with Microsoft ecosystems.

4. Observability & SRE Layer (The "Watchtower")
Implementation of "Single Pane of Glass" monitoring.

Distributed Tracing: The .NET 8 backend streams OTLP telemetry to a Linux-hosted .NET Aspire Dashboard, visualizing request paths across the network.

Synthetic Monitoring: Uptime Kuma performs automated health checks (SLA tracking) on all APIs and Databases.

Metrics: Grafana visualizes real-time system resource usage (CPU, RAM, Thermal) and Docker container health.

🛠️ Tech Stack Summary (For ATS Scanning)
Platforms: Linux (Ubuntu), Windows 11, Docker, Raspberry Pi.

Languages: C#, Python, SQL, Bash.

Frameworks: .NET 8, .NET Framework 4.8, .NET Standard, Streamlit, .NET Aspire.

Data: Qdrant (Vector), MariaDB, Azure SQL Edge.

DevOps/SRE: Portainer, Grafana, Uptime Kuma, Nginx, WireGuard.
