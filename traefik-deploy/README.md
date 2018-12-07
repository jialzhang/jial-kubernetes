
# 用DaemonSet方式部署traefik

kubectl apply -f daemonset-deploy/

serviceaccount/traefik-ingress-controller created
daemonset.extensions/traefik-ingress-controller created
service/traefik-ingress-service created
clusterrole.rbac.authorization.k8s.io/traefik-ingress-controller created
clusterrolebinding.rbac.authorization.k8s.io/traefik-ingress-controller created
service/traefik-web-ui created
ingress.extensions/traefik-web-ui created

#给node打labels，限制traefix在特定的node节点启动

#查看所有node节点的labels  

kubectl get node --show-labels

#给node 10.200.52.133 打labels

kubectl label node 10.200.52.133 traefik=traefik

#查看traefik-ingress-controller是否创建

kubectl -n kube-system get pod 


