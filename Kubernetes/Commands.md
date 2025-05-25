## General
kubectl cluster-info

kuberctl version

kubectl config get-contexts

kubectl config use-context kind-dev-cluster

kubectl api-resources

kubectl api-versions

kubectl create -f <file.yml>

kubectl create deployment <deployment-name> --image=nginx:latest --replicas=2

kubectl apply -f <file.yml>

kubectl get pods -l app=nginx (-l is for label)

kubectl create namespace <namespace-name>

kubectl get namespace

kubectl get all --all-namespaces

kubectl exec myhelloworld-d477658d8-4vl8h -- ls /app

kubectl exec myhelloworld-d477658d8-4vl8h -- /bin/bash

kubectl get service

kubectl expose deployment/<deployment-name> --name=myapp-cip-service --port=80
creating a ClusterIp service for a deployment, CLusterIP is for inter application communication within the cluster
myapp-cip-service is the service for the pods of the deployment - deployment-name. Other app talk using the service - myapp-cip-service

kubectl exec -it myhelloworld-d477658d8-4vl8h -- /bin/bash
root@myhelloworld-d477658d8-4vl8h:/# curl 10.96.0.1:443

10.96.0.1 is the ip of myapp-cip-service


kubectl expose deployment/<deployment-name> --name=myapp-cip-service --port=80 --target-port=80 --type=NodePort
NodePort service is expose to external

kubectl get nodes


kubectl expose deployment/<deployment-name> --name=myapp-lb-service --port=80 --target-port=80 --type=LoadBalancer
kubectl get service


kubectl edit deployment <deployment-name>
kubectl rollout status deployment <deployment-name>

kubectl config view

kubectl config get-contexts

kubectl config current-context

kubectl config use-context <context-name>

kubectl get events

kubectl delete -f filename.yaml

kubectl delete pods, services -l [label-key]=[label-val]

kubectl delete pods --all

kubectl delete deployment <deployment-name>

kubectl delete namespace <namespace-name>
kubectl get namespace

kubectl get node

kubectl describe nodes | grep Allocated -A 5

kubectl get pods -o wide | grep <node-name>

## Pod

kubectl get pods

kubectl describe pod <pod-name>
kubectl describe pod -l label=value

kubectl get pods
kubectl logs <pod-name>
kubectl logs -f <pod-name>

kubectl edit pod <pod-name>

kubectl get pod <pod-name> -o yaml  > my_pod.yaml

kubectl describe pod <pod-name>


## Deployment
kubectl get deployments

kubectl get deployment myhelloworld -o yaml

kubectl get deployments
kubectl scale deployment myhelloworld --replicas=2
kubectl get deployments

kubectl rollout status deployment/myhelloworld

kubectl set image deployment/myhelloworld nginx=nginx:1.24.0
kubectl rollout status deployment/myhelloworld


## Secret
