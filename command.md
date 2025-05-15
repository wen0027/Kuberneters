# 创建一个namespace
kubectl create namespace ns-nginx
# 命令行快速创建一个deployment的yaml文件模板
kubectl create deployment nginx-deployment --image=nginx:1.19.1 --dry-run=client -o yaml > nginx-deployment.yaml
# 命令行快速创建一个service的yaml文件模板 nodeport为service的yaml模板类型[nodeport|clusterip|loadbalancer]
kubectl create service nodeport nginx-service -n ns-nginx --tcp=80:8080 --dry-run=client -o yaml > nodeport-service.yaml
# 查看yaml文件中可用的apiVersion
kubectl api-version
kubectl api-resources
