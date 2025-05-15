# 创建一个namespace
kubectl create namespace ns-nginx
# 命令行快速创建一个deployment的yaml文件模板
kubectl create deployment nginx-deployment --image=nginx:1.19.1 --dry-run=client -o yaml > nginx-deployment.yaml
