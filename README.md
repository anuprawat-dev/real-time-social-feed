# Real-Time Social Feed Engine (X/Twitter-style)  
*Live Demo Coming Soon* • Built by Anup Singh Rawat  

A high-performance, real-time social feed system that handles 10K+ posts/second using *fan-out-on-write* architecture — exactly how X.com (Twitter) works.

### Why This Project?
- Uses *Java + Kafka* (same as X.com’s backend)
- Deployed with *Terraform + Kubernetes/OpenShift* (matches your Globus & E-Mech experience)
- Production-grade IaC, CI/CD, monitoring — everything recruiters want to see

### Architecture

# users -> API Gateway -> Java Spring Boot -> Kafka Producer ,  Kafka Topics -> Consumer -> Cassandra / Radis Timeline Kubernetes Pods -> Users see real-time feed 

- *Backend*: Java 17, Spring Boot, Kafka  
- *Database*: Cassandra (timeline), MySQL (users/posts)  
- *Message Queue*: Apache Kafka (MSK-style)  
- *Orchestration*: Kubernetes / OpenShift-ready manifests  
- *IaC*: Terraform (provisions EKS/GKE + Kafka + RDS)  
- *CI/CD*: Jenkins + Docker  
- *Monitoring*: CloudWatch, Prometheus + Grafana ready  

### Quick Start (Local)
```bash
git clone https://github.com/anuprawat-dev/real-time-social-feed.git
cd real-time-social-feed
docker-compose up -d    # Starts Kafka + Cassandra + backend

### Production Deployment (Terraform + k8s)
cd terraform

terraform init && terraform apply -auto-approve   # Spins up full cluster
kubectl apply -f k8s/

cd terraform
terraform init && terraform apply -auto-approve   # Spins up full cluster
kubectl apply -f k8s/
