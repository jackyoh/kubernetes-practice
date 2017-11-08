## 此Repository主要用來紀錄研究使用 Kubernetes 的 Command ##

* Download Etcd Command
```
$cd /opt
$ https://github.com/coreos/etcd/releases/download/v2.2.0/etcd-v2.2.0-linux-amd64.tar.gz
```

* Start Etcd Service Command
```
$ /opt/etcd-v2.2.0-linux-amd64
$ ./etcd -name etcd --data-dir '/var/lib/etcd' --listen-client-urls 'http://0.0.0.0:2379,http://0.0.0.0:4001' --advertise-client-urls 'http://0.0.0.0:2379,http://0.0.0.0:4001'
```

* Download Kubernetes Command
```
$ cd /opt
$ wget https://github.com/kubernetes/kubernetes/releases/download/v1.1.1/kubernetes.tar.gz
$ tar zxvf kubernetes.tar.gz
$ cd server
$ tar zxvf kubernetes-server-linux-amd64.tar.gz
```

* Start Kubernetes Master 的 API Server Service
```
$ cd /opt/kubernetes/server/kubernetes/server/bin
$ ./kube-apiserver --logtostderr=true --v=0 --etcd_servers=http://host1:4001 --insecure-bind-address=0.0.0.0 --insecure-port=8080 --service-cluster-ip-range=192.168.1.0/24
```
