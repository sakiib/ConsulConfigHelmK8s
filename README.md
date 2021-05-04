- `kind create cluster --name dc1`
- `helm repo add hashicorp https://helm.releases.hashicorp.com`
- `helm repo update`
- `helm install -f config.yaml consul hashicorp/consul --version "0.31.1"`
- `helm list --all --all-namespaces` - list all installation
- `helm delete consul` - to delete using name "consul"

```
NAME                                                              READY   STATUS    RESTARTS   AGE
pod/consul-connect-injector-webhook-deployment-645cffdc5d-mmm22   1/1     Running   0          10m
pod/consul-controller-77548c95bd-8j4w5                            1/1     Running   0          10m
pod/consul-hb2xs                                                  1/1     Running   0          10m
pod/consul-server-0                                               1/1     Running   0          10m
pod/consul-webhook-cert-manager-9d6dbf8f5-wltql                   1/1     Running   0          10m

NAME                                  TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)                                                                   AGE
service/consul-connect-injector-svc   ClusterIP   10.105.224.26   <none>        443/TCP                                                                   10m
service/consul-controller-webhook     ClusterIP   10.109.99.64    <none>        443/TCP                                                                   10m
service/consul-dns                    ClusterIP   10.99.106.76    <none>        53/TCP,53/UDP                                                             10m
service/consul-server                 ClusterIP   None            <none>        8500/TCP,8301/TCP,8301/UDP,8302/TCP,8302/UDP,8300/TCP,8600/TCP,8600/UDP   10m
service/consul-ui                     NodePort    10.105.70.165   <none>        80:30619/TCP                                                              10m
service/kubernetes                    ClusterIP   10.96.0.1       <none>        443/TCP                                                                   37m

NAME                    DESIRED   CURRENT   READY   UP-TO-DATE   AVAILABLE   NODE SELECTOR   AGE
daemonset.apps/consul   1         1         1       1            1           <none>          10m

NAME                                                         READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/consul-connect-injector-webhook-deployment   1/1     1            1           11m
deployment.apps/consul-controller                            1/1     1            1           11m
deployment.apps/consul-webhook-cert-manager                  1/1     1            1           11m

NAME                                                                    DESIRED   CURRENT   READY   AGE
replicaset.apps/consul-connect-injector-webhook-deployment-645cffdc5d   1         1         1       11m
replicaset.apps/consul-controller-77548c95bd                            1         1         1       11m
replicaset.apps/consul-webhook-cert-manager-9d6dbf8f5                   1         1         1       11m

NAME                             READY   AGE
statefulset.apps/consul-server   1/1     11m
```

Resources: 
- https://learn.hashicorp.com/tutorials/consul/kubernetes-kind