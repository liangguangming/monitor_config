# 部署monitor

## 部署顺序
1. 创建命名空间
```sh
kubectl create ns monitoring
```
2. 部署promethus
```sh
kubectl apply -f promethus/pv.yaml
kubectl apply -f promethus/pvc.yaml
kubectl apply -f promethus/promethus.yaml
kubectl apply -f promethus/volumn.yaml
kubectl apply -f promethus/role.yaml
kubectl apply -f promethus/service.yaml
kubectl apply -f promethus/issuers.yaml
kubectl apply -f promethus/ingress.yaml
```
3. 部署grafana
```sh
kubectl apply -f grafana/pv_pvc.yaml
kubectl apply -f grafana/chown.yaml
kubectl apply -f grafana/grafana.yaml
```