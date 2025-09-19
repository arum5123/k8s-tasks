# Kubernetes Webserver Pod Commands

## 1. Create Pod
kubectl apply -f webserver.yaml

## 2. Check Pod status
kubectl get pods

## 3. View logs (sidecar)
kubectl logs webserver -c sidecar-container

## 4. Push YAML to GitHub
git add webserver.yaml
git commit -m "Add webserver pod"
git push

