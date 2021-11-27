### Create deployment
``` bash
kubectl create deployment NAME --image=image [--dry-run] [option]
kubectl create deployment nginx-depl --image=nginx
```
### Blueprint for creating pods
### Most basic configuration for deployment


### get deployment
``` console
kubectl get deployment
```
### get pod
``` console
kubectl get pod
```
### get replicaset
``` console
kubectl get replicaset
```
### replicaset is managing the replicas of the Pod

### Layer of Abstraction
- Deployment manages a replicaset 
- Replicaset manages all  of the replicas
- Pod is an abstraction of the container
- Container (Docker)
- Everithing below Deployment is handled by Kubernetes

### Edit deployment
``` console
kubectl edit deployment [name]
```


### Debugging Pods
``` console
kubectl logs [pod name]
kubectl describe [pod name]
``` 

### for commend line on the pod [di dalam pod] -it = interactive
``` console
kubectl exec -it [pod name] -- bin/bash
```

### Delete deployment
``` console
kubectl delete deployment [name]
```

### Apply
### kubectl apply -f [file name]
```
kubectl apply -f config-file.yaml
```



## Summary 

### CRUD commands
Crate Deployment        
``` console
kubectl create deployment [name]
```
Edit Deployment        
``` console
kubectl edit deployment [name]
``` 
Delete Deployment       
``` console
kubectl delete deployment [name]
```


### Status of different K8s components
``` console
kubectl get nodes | pod | services | replicaset | deployment
```

### Debugging pods
Get info about Pod or Sevice       
``` console
kubectl describe pod [pod name] | service [service name]
``` 
Get more info about Pod
``` console
kubectl get [pod] | [service] -o wide
``` 
Get update configuration file Deployment
``` console
kubectl get deployment [name deployment] -o yaml    # which actually reside from Etcd
kubectl get deployment nginx-deploymnent -o yaml > nginx-deploymnent-result.yaml    # to make result on file
``` 
Log to console              
``` console
kubectl logs [pod name]
``` 
Get interactive terminal    
``` console
kubectl exec -it [pod name] -- bin/bash
``` 

### Use configuration file for CRUD
Apply a configuration file      
``` console
kubectl apply -f [file name]
```

Delete with configuration file   
``` console
kubectl delete -f [file name]
```
