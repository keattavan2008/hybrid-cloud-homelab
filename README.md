# 🏛️ Hybrid Cloud & AI Digital Twin Architecture

## 📋 Executive Summary
This project represents a sophisticated, self-hosted hybrid cloud simulation designed to replicate real-world **Enterprise Modernization** scenarios. The architecture integrates legacy Windows ecosystems with modern Linux-based microservices, focusing on **Zero Trust Security**, **Polyglot AI Development**, and **Cloud-Native Observability**.

---

## 🏗️ Architectural Overview

<p align="center">
  <img width="2816" height="1504" alt="ArchetecturalDiagram" src="https://github.com/user-attachments/assets/1c7e6e6a-7df7-4003-97b4-0dcef257ada0" />
</p>


### 1. Infrastructure Layer (The Private Cloud)
* **Host:** Raspberry Pi 5 (Ubuntu 25.x) serving as an on-premise data center.
* **Infrastructure as Code (IaC):** All services are defined and deployed via Docker Compose stacks managed by **Portainer**, ensuring instant disaster recovery and version-controlled configuration.
* **Zero Trust Networking:** The environment is isolated from the public internet. Access is strictly controlled via a **WireGuard VPN** tunnel.
* **Ingress Controller:** **Nginx Reverse Proxy** manages traffic routing, SSL termination, and load balancing.
* **DNS & Privacy:** **AdGuard Home** paired with **Unbound** functions as a recursive DNS resolver for enterprise-grade filtering and caching.

### 2. Application Layer (Legacy Modernization & Hybrid Strategy)
This layer demonstrates the bridge between legacy desktop applications and modern cloud microservices.

* **The "Migration" Pattern (C#/.NET)**
    * **Frontend:** A Windows Forms (C# .NET Framework 4.8) application modernized with embedded **WebView2** controls for rich UI capabilities.
    * **Backend:** A decoupled **.NET 8 Core API** handling business logic, simulating a cloud-native microservice.
    * **The Bridge:** Business entities shared via a **.NET Standard 2.0** library, proving backward compatibility between legacy and modern frameworks.

* **The "AI Native" Pattern (Python)**
    * **Frontend:** A lightweight **Streamlit** RAG application.
    * **Polyglot Architecture:** Consumes the same vector data sources as the .NET applications, demonstrating co-existence of C# and Python in the same ecosystem.

### 3. Data & AI Layer (The Intelligence)
A distributed data mesh supporting both transactional and semantic search workloads.

* **Vector Database:** **Qdrant** stores high-dimensional embeddings for RAG (Retrieval-Augmented Generation) workloads.
* **Relational Database:** **MariaDB** handles standard transactional data.
* **Edge Computing:** **Azure SQL Edge** runs containerized to simulate IoT/Edge data collection compatible with Microsoft ecosystems.

### 4. Observability & SRE Layer (The "Watchtower")
Implementation of "Single Pane of Glass" monitoring.

* **Distributed Tracing:** The .NET 8 backend streams **OTLP telemetry** to a Linux-hosted **.NET Aspire Dashboard**, visualizing request paths across the network.
* **Synthetic Monitoring:** **Uptime Kuma** performs automated health checks and SLA tracking on all APIs and Databases.
* **Metrics:** **Grafana** visualizes real-time system resource usage (CPU, RAM, Thermal) and Docker container health.

---

## 🛠️ Tech Stack Summary

| Category | Technologies |
| :--- | :--- |
| **Platforms** | ![Linux](https://img.shields.io/badge/Linux-FCC624?style=flat-square&logo=linux&logoColor=black) ![Windows](https://img.shields.io/badge/Windows_11-0078D4?style=flat-square&logo=windows-11&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![Raspberry Pi](https://img.shields.io/badge/Raspberry_Pi-A22846?style=flat-square&logo=raspberry-pi&logoColor=white) |
| **Languages** | ![C#](https://img.shields.io/badge/C%23-239120?style=flat-square&logo=c-sharp&logoColor=white) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white) ![SQL](https://img.shields.io/badge/SQL-CC2927?style=flat-square&logo=microsoft-sql-server&logoColor=white) ![Bash](https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnu-bash&logoColor=white) |
| **Frameworks** | ![.NET 8](https://img.shields.io/badge/.NET_8-512BD4?style=flat-square&logo=dotnet&logoColor=white) ![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=flat-square&logo=streamlit&logoColor=white) ![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat-square&logo=nginx&logoColor=white) |
| **Data** | ![Qdrant](https://img.shields.io/badge/Qdrant-Vector_DB-black?style=flat-square) ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white) ![Azure SQL](https://img.shields.io/badge/Azure_SQL_Edge-0089D6?style=flat-square&logo=microsoft-azure&logoColor=white) |

---
