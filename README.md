# AI Bank App on KIND

### Run the AI Bank App locally using Kubernetes (KIND).

```bash
kubectl apply -f ns.yml
kubectl apply -f cm.yml
kubectl apply -f secrets.yml
kubectl apply -f pv.yml
kubectl apply -f pvc.yml
kubectl apply -f mysql-deployment.yml
kubectl apply -f ollama-deployment.yml
kubectl apply -f bankapp-deployment.yml
kubectl apply -f svc.yml
```
