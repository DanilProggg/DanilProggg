# Danil Krivobok

**System administrator / Junior DevOps engineer.** Linux, Docker, networking, monitoring, and enough Java to read an application from the inside.

At a manufacturing company I was the first system administrator and built the infrastructure from scratch: VLAN segmentation, VMware ESXi virtualization, Active Directory, a Samba file server joined to the domain, Zabbix monitoring with alerting. Routine work is automated with Bash and Python: ESXi VM backups and network device config collection with rotation.

At home I run a Proxmox lab where configurations get tested before they go anywhere real: a Kubernetes cluster running my own Java microservices, Kafka in KRaft mode deployed with Helm, a WireGuard VPN chain across two VPS.

I write the backend projects below myself, so I know what an application needs from its environment: configuration, migrations, health checks, ports, permissions, logs.

## Stack

| Area | Tools |
|---|---|
| Containers and orchestration | Docker, Docker Compose, Kubernetes, Helm |
| Virtualization | Proxmox VE, VMware ESXi |
| CI/CD | GitHub Actions (matrix builds), multi-stage Docker images |
| Linux and networking | Linux, Bash, Nginx (reverse proxy), Let's Encrypt, WireGuard, nftables, VLAN, UniFi, MikroTik |
| Monitoring | Zabbix, Prometheus |
| Windows infrastructure | Active Directory, GPO, Samba (winbind, Kerberos) |
| Scripting and backend | Python, Java 17/21, Spring Boot, PostgreSQL, RabbitMQ, Flyway |
| Learning now | Terraform / OpenTofu, Ansible (against the Proxmox lab) |

## Projects

Every project starts with one command: `docker compose up --build`.

| Project | What it is | Infrastructure |
|---|---|---|
| [booking](https://github.com/DanilProggg/booking) | Seat booking for events. Concurrent seat holds via a single atomic conditional UPDATE, idempotent payment layer | Multi-stage build, JRE-alpine runtime under a non-root user, JVM memory sized to the container limit, Postgres health check gating app start, app port bound to localhost behind a reverse proxy, config via `.env`, Flyway migrations, dev/prod profiles |
| [split-net](https://github.com/DanilProggg/split-net) | Control panel for a self-hosted WireGuard network. The app brings up the interface, registers peers through `wg` and `nft`, generates client configs | Container with `NET_ADMIN` and `/dev/net/tun` driving host networking, WireGuard UDP port, persistent volume for keys, Postgres reachable only from localhost, custom CIDR arithmetic for subnet validation |
| [Words](https://github.com/DanilProggg/Words-Backend) | Vocabulary trainer, two microservices talking RPC over RabbitMQ | Five-container stack (2 services, 2 Postgres, RabbitMQ), database per service, Helm values for RabbitMQ and Prometheus for the Kubernetes deployment |
| [PO-List](https://github.com/DanilProggg/PO-List-Backend) | Class schedule and teaching-hours tracking, **in production use** at a university department | Containerized API with Postgres, Excel report generation |
| [File-storage-with-S3](https://github.com/DanilProggg/File-storage-with-S3) | Role-based file storage on top of S3-compatible object storage | App, Postgres and MinIO in one Compose stack |

## Languages

Russian (native), English B2 for reading (technical documentation without friction).

## Looking for

A junior DevOps or system administrator role where infrastructure work and the ability to read and fix application code are both useful.

Contact: [Telegram](https://t.me/danil4ik_0) · danilkrivobokk@gmail.com
