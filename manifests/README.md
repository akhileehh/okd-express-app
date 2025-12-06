# OKD/OpenShift Manifests

This folder contains manifests for deploying the project to OKD/OpenShift.

## Files

- `app1-deployment.yaml` / `app1-service.yaml` - app1 (port 3000)
- `app2-deployment.yaml` / `app2-service.yaml` - app2 (port 3002)
- `nginx-configmap.yaml` - nginx configuration
- `nginx-deployment.yaml` / `nginx-service.yaml` - nginx proxy
- `nginx-route.yaml` - OpenShift Route for external access

## Setup

1. Build and push images:
```bash
docker build -t <registry>/app1:latest .
docker push <registry>/app1:latest

docker build -t <registry>/app2:latest ./app2
docker push <registry>/app2:latest
```

2. Update image names in `app1-deployment.yaml` and `app2-deployment.yaml`

3. Apply manifests:
```bash
oc apply -f manifests/
```

4. Get the Route hostname:
```bash
oc get route nginx
```
