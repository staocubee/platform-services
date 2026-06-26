# platform-services
Purpose

Provides reusable platform services that applications depend upon.

Technologies
Helm
Kubernetes
ArgoCD
GitOps
Deployment

Deploy after infrastructure is complete.

Infrastructure
      ↓
Foundation Services
      ↓
Applications
Installation
kubectl apply -f manifests/

or sync via ArgoCD.

Features
Central authentication
Secret management
Continuous Delivery
Monitoring
Logging
Service Mesh
Container Registry
License

MIT
# 3. foundation-services/README.md

````markdown
# Foundation Services

Foundation Services contains the shared services used by applications running on the Kubernetes platform.

These services provide security, secret management, CI/CD support, service mesh, messaging, and observability.

## Services

Examples include:

- ArgoCD
- Vault
- Istio
- Prometheus
- Grafana
- Loki
- Harbor
- Jenkins
- SonarQube
- Nexus
- Redis
- RabbitMQ

## Repository Structure

```
foundation-services/
├── argocd/
├── vault/
├── monitoring/
├── service-mesh/
├── ci-cd/
├── registry/
└── README.md
eval "$(ssh-agent -s)"
ssh-add -K /Users/mac/.ssh/id_rsa_techbeing
git push -u origin main --force
# argocd
kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d
# nexus
kubectl exec -it nexus-nexus-repository-manager-74f65d5978-q94n6 -n nexus -- /bin/bash
cat /nexus-data/admin.password

# grafana
kubectl -n monitoring get secret monitoring-grafana -o jsonpath="{.data.admin-password}" | base64 -d
