Project 07 – Monitoring & Observability with Prometheus and Grafana

Overview

This project demonstrates how to build a complete monitoring and observability solution on an AWS EC2 instance using Prometheus, Node Exporter, and Grafana.

The monitoring stack continuously collects infrastructure metrics from the EC2 server, stores them as time-series data, and presents them through interactive Grafana dashboards for real-time monitoring and troubleshooting.

---

Architecture

                AWS EC2 Instance
                       │
                       ▼
              Node Exporter (9100)
                       │
         Exposes system metrics
      (CPU, Memory, Disk, Network)
                       │
                       ▼
              Prometheus (9091)
                       │
      Scrapes and stores metrics
          every 15 seconds
                       │
                       ▼
               Grafana (3000)
                       │
      Visualizes metrics through
        real-time dashboards

---

Technology Stack

Tool| Purpose
Prometheus| Collects and stores time-series metrics
Node Exporter| Exposes Linux system metrics
Grafana| Visualizes monitoring data through dashboards
AWS EC2| Hosts the monitoring environment
Ubuntu Linux| Operating System
Systemd| Manages services and automatic startup

---

Metrics Monitored

The monitoring solution tracks several important system metrics, including:

- CPU utilization
- System load average
- Memory usage
- Swap utilization
- Disk usage
- Disk I/O
- Network traffic
- System uptime
- Running processes

---

Project Setup

Install Prometheus

wget https://github.com/prometheus/prometheus/releases/download/v2.45.0/prometheus-2.45.0.linux-amd64.tar.gz

tar -xvf prometheus-2.45.0.linux-amd64.tar.gz

sudo mv prometheus-2.45.0.linux-amd64/prometheus /usr/local/bin/

---

Install Node Exporter

wget https://github.com/prometheus/node_exporter/releases/download/v1.6.1/node_exporter-1.6.1.linux-amd64.tar.gz

tar -xvf node_exporter-1.6.1.linux-amd64.tar.gz

sudo mv node_exporter-1.6.1.linux-amd64/node_exporter /usr/local/bin/

---

Install Grafana

wget -q -O - https://packages.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null

echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://packages.grafana.com/oss/deb stable main" | sudo tee /etc/apt/sources.list.d/grafana.list

sudo apt update

sudo apt install grafana -y

---

Prometheus Configuration

The Prometheus configuration scrapes metrics from both the Prometheus server and the Node Exporter every 15 seconds.

global:
  scrape_interval: 15s

scrape_configs:
  - job_name: prometheus
    static_configs:
      - targets:
          - localhost:9091

  - job_name: node_exporter
    static_configs:
      - targets:
          - localhost:9100

---

Grafana Dashboard

Grafana was configured to use Prometheus as its data source.

The Node Exporter Full dashboard (Dashboard ID 1860) was imported to visualize:

- CPU utilization
- Memory usage
- Disk usage
- Network traffic
- System load
- Historical performance trends
- System uptime

---

Service Management

Prometheus, Node Exporter, and Grafana were configured as systemd services, ensuring they:

- Start automatically after server reboot.
- Restart automatically if a service fails.
- Run continuously in the background.

---

Screenshots

<img width="958" height="535" alt="Screenshot 2026-07-09 082621" src="https://github.com/user-attachments/assets/adaf6ed2-ed3f-4167-be0c-51c94d0c11c2" />
<img width="950" height="514" alt="Screenshot 2026-07-09 092529" src="https://github.com/user-attachments/assets/d2ff4ebd-7922-498b-bcd6-771644345552" />
<img width="953" height="530" alt="Screenshot 2026-07-09 083207" src="https://github.com/user-attachments/assets/8aa8e874-484d-4f8b-b5ee-1f12f7d523b4" />
<img width="953" height="499" alt="Screenshot 2026-07-09 093235" src="https://github.com/user-attachments/assets/d5796c3a-39ed-4ac2-a89f-828e91d75c01" />

---

Key Skills Demonstrated

- Infrastructure Monitoring
- Observability
- Prometheus Configuration
- Node Exporter Deployment
- Grafana Dashboard Configuration
- Linux System Administration
- Service Management with systemd
- AWS EC2 Administration
- Performance Monitoring
- Troubleshooting Using Metrics

---

Key Learnings

Through this project, I gained hands-on experience with:

- Deploying a complete monitoring stack on AWS.
- Collecting infrastructure metrics using Node Exporter.
- Configuring Prometheus to scrape and store time-series data.
- Building monitoring dashboards with Grafana.
- Running monitoring services using systemd.
- Understanding the importance of observability in modern DevOps environments.
## Author
**Emmanuel** — DevOps Engineer 

