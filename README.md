# Kubernetes Microservice Flask Application with MongoDB Database
This is a microservice application built using Flask and deployed on Kubernetes
### Prerequisites:
One master node and one worker node (https://github.com/satyam19arya/kubestarter/blob/main/kubeadm_installation.md)

Steps:
```
mkdir project
cd project/
git clone https://github.com/satyam19arya/K8s_kubeadm_flask_project.git
ls
cd K8s_kubeadm_flask_project/
ls
cd k8s/
ls
kubectl apply -f mongo-pv.yml
kubectl apply -f mongo-pvc.yml
kubectl apply -f mongo-secret.yml
kubectl apply -f mongo-configmap.yml
kubectl apply -f mongo.yml
kubectl get pods
kubectl apply -f taskmaster.yml
kubectl get pods
```

To confirm mongoDB running:
```
kubectl get pods
kubectl exec -it <pod_name> -- bash
mongosh
exit
```
Note: Make sure to open port 30000 and 30007 in your inbound SG rules

<img width="539" alt="image" src="https://github.com/satyam19arya/K8s_kubeadm_flask_project/assets/77580311/8e65dc40-32e6-4878-a7b7-76931f9c2f4f">

<img width="878" alt="Screenshot 2023-08-18 172934" src="https://github.com/satyam19arya/K8s_kubeadm_flask_project/assets/77580311/a06bb4e0-9195-4564-b1bc-3c59871e5627">
