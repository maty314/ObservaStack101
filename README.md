# ObservaStack101

Is an observability stack designed for monitoring, log management, and automated alerting.
The primary purpose is to practice and get familiar with these observability tools.
A simple dashboard is out-of-the box showing logs using Loki and Metrics using Prometheus.
It integrates **Prometheus**, **Grafana**, **Loki**, **Alertmanager**, and **Promtail**.

## Prerequisites
- 🐳 Run with Docker



## Pipeline
### Logs
[System Log] --> [Promtail] --> [Loki] --> [Grafana Dashboard]

- [System Log]: Event generation in the system (e.g., logger "Simulating a critical system event").
- [Promtail]: Collects system logs and forwards them to Loki.
- [Loki]: Indexes and stores logs efficiently for fast querying.
- [Grafana Dashboard]: Visualizes logs with filters, searches, and correlation with metrics.

### Metrics
[System Metrics (Node Exporter)] --> [Prometheus] --> [Alertmanager] --> [Notifications (Email, Slack)] 
                                              ↘
                                           [Grafana Alerts]

- [System Metrics (Node Exporter)]: Collects metrics such as CPU usage, memory, network stats, etc.
- [Prometheus]: Monitors these metrics and evaluates predefined alert rules.
- [Alertmanager]: Receives alerts from Prometheus and manages notification routing (email, Slack, etc.).
- [Notifications (Email, Slack)]: Sends automated notifications to the configured channels.
- [Grafana Alerts]: Displays active alerts directly in Grafana for real-time monitoring.


## Folder Structure
```bash
ObservaStack101/
├── alertmanager/
├── grafana/
├── loki/
├── prometheus/
├── promtail/
└── docker-compose.yml
```

## How to run it
### 1️⃣ Clone the repository
```bash
git clone https://github.com/maty314/ObservaStack101.git
cd ObservaStack101
```

### 2️⃣ Start the stack
```bash
docker-compose up -d
```
This will start all services: Prometheus (9090), Grafana (3000), Loki (3100), Alertmanager (9093), and Promtail.

### 3️⃣ Access Grafana
Open http://localhost:3000
Default credentials:
- Username: admin
- Password: admin

### 4️⃣ Stop the stack
Whenever you are done with the tests you can stop the docker stack by running:
```bash
docker-compose down
``` 
