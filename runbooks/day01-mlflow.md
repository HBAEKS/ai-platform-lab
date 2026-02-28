# Day 01 – MLflow on Kubernetes

## 🎯 Objective
Deploy MLflow Tracking Server on Kubernetes (kind) and verify experiment logging.

---

## 🏗 Architecture
Client → MLflow Tracking Server (K8s)  
Backend Store: SQLite  
Artifact Store: Local PVC  

---

## 🚀 Commands

```bash
kubectl create ns mlops
kubectl apply -f mlflow.yaml
kubectl -n mlops port-forward svc/mlflow 5000:5000