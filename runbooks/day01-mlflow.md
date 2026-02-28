# 🚀 Day 01 – MLflow on Kubernetes

> Objective: kind(K8s) 위에 MLflow Tracking Server를 배포하고, 로컬에서 실험 로그/아티팩트 기록을 검증한다.

---

## 🏗 Architecture
Client → MLflow Tracking Server (K8s)  
Backend Store: SQLite (PVC)  
Artifact Store: PVC

---

## ⚙ Resources
- Namespace: `mlops`
- Deployment: `mlflow`
- Service: `mlflow`
- PVC: `mlflow-pvc (2Gi)`

---

## 🚀 Commands

```bash
kind create cluster --name mlops-lab
kubectl create ns mlops

kubectl apply -f manifests/mlflow/mlflow.yaml

kubectl -n mlops get pods,svc,pvc
kubectl -n mlops port-forward svc/mlflow 5000:5000