# Monitoring Stack: Prometheus + Grafana + Node-exporter

A ready-to-deploy monitoring stack based on Docker Compose. It includes Prometheus, Grafana, Node Exporter, and Nginx as a reverse proxy.

## 🚀 Quick Start

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/MounTemed/Monitoring
    cd monitoring
    ```

2.  **Launch the services:**
    ```bash
    podman compose up -d
    ```

## 🛠️ Stack Components

| Service         | Purpose                      | Access                        |
| :-------------- | :--------------------------- | :---------------------------- |
| **Nginx**       | Reverse proxy for Grafana    | `http://localhost`            |
| **Grafana**     | Visualization & dashboards   | `http://localhost` (via Nginx)|
| **Prometheus**  | Metrics collection & storage | `http://localhost:9090`       |
| **Node Exporter**| Host metrics exporter        | `http://localhost:9100/metrics`|

## ⚙️ Configuration

*   **Service Definitions**: `compose.yaml`
*   **Prometheus Scrape Targets**: `prometheus.yml`
*   **Nginx Configuration**: `images/nginx.conf`
*   **Grafana Dashboards**: `grafana/*.json` (to be imported manually)
*   **Deployment Automation**: `ansible/` #TODO

## 🏗️ Project Structure
```
.
├── ansible/          # Automation playbooks #TODO
├── compose.yaml      # Docker Compose file
├── grafana/          # Grafana dashboards
├── images/           # Files to build the Nginx image
├── prometheus.yml    # Prometheus configuration
└── README.md
