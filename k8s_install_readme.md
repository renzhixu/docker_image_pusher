rancher部署

1.部署rancher 
docker run -d -p 8055:80 -p 8443:443  --restart=unless-stopped  -v /data/rancher:/var/lib/rancher  -v /data/auditlog:/var/log/auditlog  --name rancher  --privileged=true  rancher/rancher:v2.5.9  

2.部署K8S集群
  2.1 创建自定义k8s集群
  2.2 复制注册命名到k8s主机

3.注册失败的主机第二次注册需清理掉当前主机所有k8s残余文件
  3.1 
  rm -rf /etc/ceph  /etc/cni  /etc/kubernetes  /opt/cni  /opt/rke  /run/secrets/kubernetes.io  /run/calico  /run/flannel  /var/lib/calico  /var/lib/etcd  /var/lib/cni  /var/lib/kubelet  /var/lib/rancher/rke/log  /var/log/containers  /var/log/pods  /var/run/calico
