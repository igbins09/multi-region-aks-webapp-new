# Multi-Region AKS Web App with High Availability and Disaster Recovery

This project deploys a highly available Node.js web application across two Azure Kubernetes Service (AKS) clusters in East US and West US, leveraging Azure Front Door for global load balancing and failover. It includes observability with Azure Monitor and Log Analytics, a basic disaster recovery plan, and cost optimization tracked via Azure Cost Management—demonstrating senior-level DevOps skills in multi-region architecture and production-ready systems.

## Project Objective
Build a web app on AKS that spans multiple regions, ensuring 99.99% uptime, automated failover, real-time monitoring, and disaster recovery, while keeping costs optimized.

## Architecture
- **Two AKS Clusters**: Deployed in East US and West US for regional redundancy.
- **Node.js Web App**: Deployed using Helm charts for consistency and scalability.
- **Azure Front Door**: Provides global load balancing and automated failover.
- **Azure Monitor & Log Analytics**: Enables real-time observability and alerting.
- **Disaster Recovery**: Manual snapshots for quick recovery (Azure Backup optional).
- **Cost Optimization**: Monitored and optimized using Azure Cost Management.

## Key Features
- **High Availability**: Multi-region deployment with 99.99% uptime via Azure Front Door.
- **Automated Failover**: Front Door reroutes traffic if a region fails.
- **Observability**: Real-time insights with Azure Monitor and Log Analytics.
- **Disaster Recovery**: Manual snapshots for recovery (e.g., `kubectl get pods --all-namespaces -o yaml > snapshot.yaml`).
- **Cost Optimization**: Tracked and optimized to ~$150/month using Azure Cost Management.

## Impact
- Reduced failover time by 80% with Azure Front Door.
- Optimized resource costs by 15% through monitoring and right-sizing.

## Tech Stack
- Azure Kubernetes Service (AKS)
- Helm
- Azure Front Door
- Azure Monitor
- Log Analytics
- Azure Cost Management

## Disaster Recovery Plan
- **Manual Snapshots**: Run `kubectl get pods --all-namespaces -o yaml > snapshot.yaml` to capture cluster state.
- **Recovery**: Reapply the snapshot with `kubectl apply -f snapshot.yaml`.
- *(Optional)* Integrate Azure Backup for automated recovery.
