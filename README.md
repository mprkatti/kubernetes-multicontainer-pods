# kubernetes-multicontainer-pods
The artifacts here attempt to illustrate the concept of multi container pods that solve common problems related to kubernetes pod design and deployment. It is an illustration of the following patterns:

- Sidecar Pattern
- Ambassador Pattern

How to run:
SideCar
- clone the repo 
- Bring up minikube cluster on the laptop
- under the 'sidecar' directoy execute
  kubectl create -f ft-svc.yaml
  kubectl create -f sidecar-app-demo.yaml
- wait for the pods to come to 'Ready' state.
- exec into all three pods to see FTP transfers happening end-end

Ambassador:
- under the 'ambassador' directory execute
  kubectl create configmap nginx-config -n myns --from-file nginx_default.conf
  kubectl create -f ambassador.yaml
- exec into the main-app pod and execute the following curl commands:

  curl 127.0.0.1 
  
  curl 127.0.0.1/todos
  
  curl 127.0.0.1/todos/200
  
  

  
