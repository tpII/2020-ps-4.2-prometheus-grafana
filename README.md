# Raspberry Pi Monitoring with Prometheus & Grafana

A centralized monitoring solution for Raspberry Pi devices using **Prometheus, Grafana, Node Exporter, Docker, and VirtualBox**.

The project was developed as part of the *Taller de Proyecto II* course and focuses on building a lightweight monitoring architecture capable of collecting, storing, querying, and visualizing system metrics from multiple Raspberry Pi devices.

## Architecture

The monitoring stack follows a centralized architecture:

**Raspberry Pi → Node Exporter → Prometheus → Grafana**

The Raspberry Pi devices run only **Node Exporter**, keeping the monitoring overhead on the devices as low as possible.

**Prometheus** and **Grafana** run independently on a monitoring server using **Docker Compose**. Prometheus periodically scrapes the metrics exposed by Node Exporter, while Grafana uses Prometheus as its data source to query and visualize the collected information.

For development and testing, multiple Raspberry Pi devices were simulated using **Raspberry Pi OS virtual machines running in VirtualBox**.

## Monitored Metrics

The Grafana dashboard provides real-time visualization of several system metrics, including:

- CPU utilization
- RAM usage
- Disk usage and capacity
- System uptime
- Network upload and download activity

Prometheus queries are performed using **PromQL**.

A Grafana dashboard variable was also implemented to dynamically select the Raspberry Pi instance to monitor, allowing multiple devices to be managed from a single dashboard.

## Technologies

- **Prometheus** — metrics collection and time-series storage
- **Grafana** — dashboards and data visualization
- **Node Exporter** — system metrics exporter
- **PromQL** — querying and processing Prometheus metrics
- **Docker & Docker Compose** — deployment of the monitoring services
- **VirtualBox** — Raspberry Pi environment virtualization
- **Raspberry Pi OS / Linux**
- **SSH & TCP/IP networking**

## Project Documentation

The complete development process, including research, architecture decisions, configuration, troubleshooting and implementation details, is documented in the project's [GitHub Wiki](../../wiki).

Additional project reports, configuration files and supporting material are available within this repository.