## 3 Parts Kubernetes YAML configuration file
- Metada

    ``` yaml
    apiVersion: apps/v1
    kind: Deployment
    metadata:
      name: nginx-deployment
      labels:
        app: nginx 
    ```

- Specification
    ``` yaml
    spec: 
        replicas: 2   
        selector:
          matchLabels:
            app: nginx
        template:
          metadata:
            labels:
              app: nginx
          spec:   
            containers:
            - name: nginx
              image: nginx:1.16
              ports:
              - containerPort: 80
    ```
- Status
    - status is from the k8s
    by example, if the pod replicas running : 1, and then you apply new configuration file which on the file your configure number of replicas is : 2, the k8s can comparing of pod running with the configuration file. if not match, the k8s can update that with the new configuration file you apply to.
    - the question is, where does k9s get this status data, answer is Etcd holds the current status of any k8s components!

### Example
- Configuration of Pod
    ![images](https://github.com/ikromnurrohim/kubernetes/blob/master/assets/template-pod.png)

- Connect Deployment to Pod
    ![images](https://github.com/ikromnurrohim/kubernetes/blob/master/assets/connection-depl-to-pods.png)
- Connect Service to Deployement
    ![images](https://github.com/ikromnurrohim/kubernetes/blob/master/assets/connection-service-to-depl.png)
    
