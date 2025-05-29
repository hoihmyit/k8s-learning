# k8s-learning

## Create a Kind cluster with Podman Desktop with the Kind config file: kind-config.yaml
### For example:
```
kind: Cluster
apiVersion: kind.x-k8s.io/v1alpha4
nodes:
  - role: control-plane
    extraPortMappings:
      - containerPort: 31297  # NodePort exposed by nginx service
        hostPort: 8888        # Expose on host machine at port 8888
```


## Run the deployment.yml
kubectl apply -f sample-nginx/deployment.yaml

## Run the service.yml
kubectl apply -f sample-nginx/service.yaml

## Access to nginx via:
http://localhost:8088