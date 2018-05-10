### Kubectl
Linux: https://storage.googleapis.com/kubernetes-release/release/v1.6.1/bin/linux/amd64/kubectl

MacOS: https://storage.googleapis.com/kubernetes-release/release/v1.6.1/bin/darwin/amd64/kubectl

Windows: 
https://github.com/eirslett/kubectl-windows/releases/download/v1.6.3/kubectl.exe

### Minikube
Project URL: https://github.com/kubernetes/minikube

Latest Release and download instructions: https://github.com/kubernetes/minikube/releases

VirtualBox: http://www.virtualbox.org

### Minikube on windows:
Download the latest minikube-version.exe

Rename the file to minikube.exe and put it in C:\minikube

Open a cmd (search for the app cmd or powershell)

Run: cd C:\minikube and enter minikube start

Test your cluster commands
Make sure your cluster is running, you can check with minikube status.

If your cluster is not running, enter minikube start first.


minikube start
kubectl get node
kubectl get pod
kubectl create -f helloworld.yml
kubectl port-forward nginx 9091:80
kubectl expose pod nginx --type:NodePort --name nginx-helloworld
minikube service nginxhelloworld-service --url
kubectl exec nginx -- ls -ltr
kubectl get pods --all-namespaces
kubectl run -i --tty busybox --image=busybox --restart=Never
    telnet 172.17.0.4 80
        GET /
 
kubectl delete pods 
kubectl create -f helloworld-replication-controller.yml
kubectl get replicationcontroller
kubectl get rc
kubectl get pods --selector=app=helloworld
kubectl describe rc helloworld-controller
kubectl scale --replicas=4 -f kubectl scale --replicas=3 rc/helloworld-controller
kubectl scale --replicas=3 rc/helloworld-controller


kubectl create -f helloworld-deployment.yml
kubectl get deployment
kubectl get deployments
kubectl get rs
kubectl describe deployment helloworld-deployment
kubectl describe rs <rs name>
kubectl describe pod <pod name>
kubectl rollout status deployment/helloworld-deployment
kubectl scale --replicas=5 deployment/helloworld-deployment
kubectl expose deployment helloworld-deployment --type=NodePort
kubectl set image deployment/helloworld-deployment nginx=nginx
kubectl rollout undo deployment/helloworld-deployment
kubectl edit deployment/helloworld-deployment
    in the spec add revisionHistoryLimit: 5
