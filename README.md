# kubernetes


    | Kind          | Version      |
    |---------------|--------------|
    | POD           | v1           |
    | Service       | v1           |
    | ReplicaSet    | apps/v1      |
    | Deployment    | apps/v1      |

----------------------------------------------------------------------
membuat pod redis dengan cara declarative

POD

apiVersion: v1
kind: Pod
metadata:
  name: myapp-pod
  labels:
    app: myapp
    type: front-end
spec:
  containers:
    - name: nginx-containers
      image: nginx
    
----------------------------------------------------------------------
kubectl get pods
kubectl describe pod myapp-pod
kubectl apply -f pod.yaml

membuat pod redis dengan cara imperative
kubectl run redis --image=redis123 --dry-run=client -o yaml > redis.yaml
kubectl create -f redis.yaml
