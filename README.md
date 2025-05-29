# k8s-learning

## 🚀 Deploy NGINX on Kubernetes with Kind and Podman Desktop
#### This project sets up an NGINX deployment in a Kind (Kubernetes-in-Docker) cluster running inside Podman Desktop, exposing it to the host machine at localhost:8088.


### 📝 Prerequisites
- Podman Desktop installed and running
- kubectl installed and configured to talk to the Kind cluster
- Kind installed inside Podman Desktop with kind-config.yaml:
    ```
    kind: Cluster
    apiVersion: kind.x-k8s.io/v1alpha4
    nodes:
    - role: control-plane
        extraPortMappings:
        - containerPort: 31297  # NodePort exposed by nginx service
            hostPort: 8888        # Expose on host machine at port 8888
    ```


### Run the deployment.yml
kubectl apply -f sample-nginx/deployment.yaml

### Run the service.yml
kubectl apply -f sample-nginx/service.yaml

### Verify Deployment and Service
kubectl get pods
kubectl get svc nginx-service

### Access to nginx via:
http://localhost:8088