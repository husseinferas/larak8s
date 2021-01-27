<p align="center">
<h3 align="center">Larak8s</h3>
<p align="center"> Template for deploying Laravel application with Kubernetes  </p>
<br>

---


### Requirements

* Kubernetes Cluster (minikube, kubeadm, EKS, AKS, GKE, ...).
* Kubectl connected with the cluster and ready.
* Storage class and PV storage.

### Usage

* Clone this repo:

```bash
git clone https://github.com/husseinferas/larak8s && cd  larak8s
```

* Create new namespace :
```bash
kubectl create namespace larak8s
```

* Deploy your project :
```bash
kubectl apply -k .
```

* Delete the project :
```bash
kubectl delete -k .
```


### Customization

* Customized your laravel image: <br>
inside app/deployment

```yaml
...
      containers:
      - name: laravel
        image: <YOUR_IMAGE>
        ports:
        - containerPort: 80
...
```

* Customized your namespace: <br>
  you can find and replace the default namespace ``larak8s`` with your namespace

```yaml
...
metadata:
  namespace: <YOUR_NAMESPACE>
  name: laravel
...
```


* Further Customization: <br>
  you can customize anything you want in all the resources
  
 ---

* **Note** don't forget to apply your changes 
```bash
kubectl apply -k .
```


### Contributing

Pull requests are welcome. For major changes.

### License

Larak8s is licensed under the terms of the [MIT License](https://github.com/husseinferas/larak8s/blob/master/LICENSE)
(See LICENSE file for details).
