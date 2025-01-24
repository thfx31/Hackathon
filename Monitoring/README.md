# Monitoring Stack with Prometheus, Grafana, and Node Exporter

This project provides a simple Docker Compose setup to deploy Prometheus, Grafana, and Node Exporter for monitoring system metrics and visualizing them in Grafana.

## Components

1. **Node Exporter**: Exports host system metrics for Prometheus.
2. **Prometheus**: Scrapes metrics from Node Exporter and stores them.
3. **Grafana**: Visualizes Prometheus metrics in a user-friendly dashboard.

## Docker Compose Setup

### Prerequisites

- Docker
- Docker Compose

### Running the Stack

1. Clone this repository:
   ```bash
   git clone <https://github.com/thfx31/Hackathon/tree/main/Monitoring>
   cd <Monitoring>
   ```

2. Start the stack using Docker Compose:
   ```bash
   docker-compose up -d
   ```

3. Access the services:
   - **Grafana**: Open [http://localhost:3000](http://localhost:3000) in your browser. Default login is `admin/admin`.
   - **Prometheus**: Open [http://localhost:9090](http://localhost:9090) to view Prometheus.

### Services Configuration

- **Node Exporter**:
  - Exposes system metrics on port `9100` and provides detailed data about the host system.
  - Mounted volumes to expose host's `/proc`, `/sys`, and `/` directories for system-level metrics.

- **Prometheus**:
  - Exposes the Prometheus UI on port `9090` for querying and analyzing metrics.
  - Scrapes metrics from the `node-exporter` service using the configuration in `prometheus.yml`.
  - Default scrape interval is set to `15s`.

- **Grafana**:
  - Exposes the Grafana UI on port `3000` for visualizing the metrics collected by Prometheus.
  - Stores data in a Docker volume (`grafana-storage`) for persistent storage of dashboards and settings.

### Volumes

- **prometheus_data**: Persists Prometheus data.
- **grafana-storage**: Persists Grafana dashboards and configurations.

### Configuration Files

- **prometheus.yml**: Prometheus configuration file. The `scrape_configs` section defines the scrape targets, and the global scrape interval is set to `15s`.

  ```yaml
  global:
    scrape_interval: 15s  # Interval to scrape metrics

  scrape_configs:
    - job_name: 'node-exporter'
      static_configs:
        - targets: ['node-exporter:9100']  # Address of the Node Exporter
  ```

## Stopping the Stack

To stop the stack, run:

```bash
docker-compose down
```

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
```

In this updated `README.md`, I've included the configuration snippet for `prometheus.yml`, explaining how the scrape interval is set and where Prometheus scrapes metrics from.
