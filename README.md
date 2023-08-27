# Kubernetes Microservice Flask Application with MongoDB Database
This is a microservice application built using Flask and deployed on Kubernetes

Setup (3 ways)
- https://github.com/satyam19arya/kubestarter/blob/main/kubeadm_installation.md
- https://killercoda.com/playgrounds/scenario/kubernetes
- https://github.com/satyam19arya/kubestarter/blob/main/minikube_installation.md

Steps:
```
mkdir project
cd project/
git clone https://github.com/satyam19arya/K8s_kubeadm_flask_project.git
cd K8s_kubeadm_flask_project/
cd k8s/
ls
kubectl apply -f mongo-pv.yml
kubectl apply -f mongo-pvc.yml
kubectl apply -f mongo.yml
kubectl get pods
kubectl apply -f taskmaster.yml
kubectl get pods
kubectl exec -it <pod_name> -- bash
mongosh
exit
curl http://127.0.0.1:30007
curl http://127.0.0.1:30007/tasks
curl -d '{"task":"study"}' -H "Content-type: application/json" -X POST http://127.0.0.1:30007/task
curl http://127.0.0.1:30007/tasks
kubectl apply -f mongo-express.yml
curl http://127.0.0.1:30000
```

Note: Make sure to open port 30000 and 30007 in your inbound SG rules

## Outputs
<img width="539" alt="image" src="https://github.com/satyam19arya/K8s_kubeadm_flask_project/assets/77580311/8e65dc40-32e6-4878-a7b7-76931f9c2f4f">

<img width="361" alt="image" src="https://github.com/satyam19arya/K8s_kubeadm_flask_project/assets/77580311/2b96ce9d-cabc-4b95-a570-02647346576a">

<img width="627" alt="image" src="https://github.com/satyam19arya/K8s_kubeadm_flask_project/assets/77580311/1ec5c765-2f65-46c1-813c-17d368517b17">
