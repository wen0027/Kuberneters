# 创建一个namespace
kubectl create namespace ns-nginx
# 命令行快速创建一个deployment的yaml文件模板
kubectl create deployment nginx-deployment --image=nginx:1.19.1 --dry-run=client -o yaml > nginx-deployment.yaml
# 获取deployment的详细信息
kubectl describe deployment nginx-deployment -n ns-nginx

# 命令行快速创建一个service的yaml文件模板 nodeport为service的yaml模板类型[nodeport|clusterip|loadbalancer]
kubectl create service nodeport nginx-service -n ns-nginx --tcp=80:8080 --dry-run=client -o yaml > nodeport-service.yaml

# 将nginx放到置两个副本
kubectl scale deployment/nginx-deployment --replicas=2 -n ns-nginx

# 查看yaml文件中可用的apiVersion
kubectl api-version
kubectl api-resources
# 命令行创建一个hpa(HorizontalPodAutoscaler)的yaml模板文件
kubectl autoscale deployment nginx-deployment -n ns-nginx --cpu-percent=50 --min=1 --max=5 --dry-run=client -o yaml > hap.yaml
# 获取hpa资源信息
kubectl get hap -n ns-nginx
