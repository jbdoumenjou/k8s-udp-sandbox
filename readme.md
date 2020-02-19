
# How to Start the Stack

```bash
k3d create --api-port 6550 --publish 80:80 --publish 8080:8080 
export KUBECONFIG="$(k3d get-kubeconfig --name='k3s-default')"
k3d i containous/traefik:latest
kubectl apply -f conf/
echo 'WHO' | netcat -u 127.0.0.1 8000
k3d delete
```

