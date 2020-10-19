# labbox
Various kubernetes apps that i use my Prisma Cloud Compute (twistlock) local lab

## Deploy Portainer
```bash
# curl -LO https://raw.githubusercontent.com/portainer/portainer-k8s/master/portainer.yaml
kubectl apply -f portainer.yaml
kubectl get svc --all-namespaces 
```
wait till the EXTERNAL-IP is assigned
```bash
open http://<external-ip>:9000/
```

## Deploy Azure Vote app
```bash
# git clone https://github.com/Azure-Samples/azure-voting-app-redis
# cd azure-voting-app-redis/
kubectl create namespace azure-vote
kubectl apply -f azure-vote-all-in-one-redis.yaml -n azure-vote
kubectl get svc -n azure-vote
```
wait till the EXTERNAL-IP is assigned to the azure-vote-front pod
```bash
open http://<external-ip>/
```

## Deploy Sock-Shop microservices app
```bash
kubectl create namespace sock-shop   
kubectl apply -f sock-shop.yaml   
kubectl get svc -n sock-shop 
```
wait till the EXTERNAL-IP is assigned to the front-end pod
```bash
open http://<external-ip>/
```

## Deploy a sample Crypto miner
```bash
# git clone --recursive https://github.com/brannondorsey/xmrig-k8s
# cd xmrig-k8s
kubectl apply -f xmrig-k8s.yaml

kubectl apply -f graboid.yaml
```


