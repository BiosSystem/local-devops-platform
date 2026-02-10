🚀 Local DevOps Platform
A production-grade, local Kubernetes environment built with GitOps principles. This project demonstrates how to bootstrap a complete infrastructure stack—including observability, ingress, and security—using the App-of-Apps pattern.

🏗️ Architecture
This platform follows a "Hub-and-Spoke" GitOps model. A single Root Application monitors the Git repository and orchestrates the deployment of all platform tools and application workloads.

Orchestration: Kubernetes (via Orbstack/Kind).

GitOps Engine: ArgoCD.

Pattern: App-of-Apps for hierarchical resource management.

🛠️ Tech Stack & Methodology
Observability: Prometheus & Grafana for real-time cluster metrics and SLO tracking.

Ingress Management: Nginx Ingress Controller providing local DNS resolution via *.local.

Security & Policy: Kyverno for Policy-as-Code to enforce cluster guardrails.

Persistence: Dynamic volume provisioning using local-path storage.

📂 Project Structure
Plaintext
local-devops-platform/
├── bootstrap/           # Manual entry point for cluster initialization
├── apps/
│   ├── infrastructure/  # Platform tools (Prometheus, Ingress, Kyverno)
│   └── workloads/       # Business applications (Weather App)
└── scripts/             # Automation scripts for environment parity



🚀 Getting Started
Clone the Repo:

Bash
git clone https://github.com/BiosSystem/local-devops-platform.git
cd local-devops-platform
Bootstrap the Cluster: Run the provided script to install ArgoCD and the Root Application:

Bash
./scripts/bootstrap.sh
Access the Platform: Add the following to your /etc/hosts to access local dashboards: 127.0.0.1 grafana.local argocd.local weather.local