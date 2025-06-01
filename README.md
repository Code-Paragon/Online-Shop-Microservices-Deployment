# 🛒 Online Shop Microservices Deployment

A comprehensive deployment solution for a cloud-native online shop application built on a microservices architecture using Kubernetes and Helm. This repository encapsulates Helm charts, service-specific configurations, monitoring, and utility scripts for automated installation and teardown.

---

## 🧩 Features

- **Modular Microservices Deployment** via reusable Helm charts  
- **Service-Specific Configurations** under `/values/` for each microservice  
- **Centralized Deployment Control** using `helmfile.yaml`  
- **Built-In Monitoring Stack** with Prometheus and Alertmanager  
- **Infrastructure as Code** support for reproducibility and automation  

---

## 🚀 Microservices Included

| Service                  | Port   | Description                            |
|--------------------------|--------|----------------------------------------|
| `frontend`               | 80     | Web frontend exposed via LoadBalancer  |
| `cartservice`            | 7070   | Shopping cart backed by Redis          |
| `productcatalogservice`  | 3550   | Product listings                       |
| `recommendationservice`  | 8080   | Personalized suggestions               |
| `checkoutservice`        | 5050   | Handles checkout workflow              |
| `currencyservice`        | 7000   | Currency conversion                    |
| `paymentservice`         | 50051  | Handles payments securely              |
| `emailservice`           | 5000   | Sends order confirmations              |
| `shippingservice`        | 50051  | Manages shipping and tracking          |
| `adservice`              | 9555   | Serves contextual ads                  |
| `redis-cart`             | 6379   | Redis store for shopping cart          |

---

## ⚙️ Installation

```bash
./install.sh

---

## 🧹 Uninstallation

```bash
./uninstall.sh


---

## 📊 Monitoring

- `PrometheusRule` and `AlertmanagerConfig` defined under `/monitoring/`
- Alerts for:
  - High CPU Load
  - Pod CrashLooping
  - Redis Availability and Connection Saturation

---

## 🛠 Project Structure

```text
charts/                    # Helm charts for services and Redis
values/                    # Helm values for each microservice
monitoring/                # Prometheus + Alertmanager configs
helmfile.yaml              # Helmfile to orchestrate multi-chart installs
install.sh / uninstall.sh  # Helper scripts for setup/teardown
config.yaml                # Kubernetes deployment samples
