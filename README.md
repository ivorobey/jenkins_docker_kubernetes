# Kubernetes cluster created using vagrant on virtualbox with jenkins that builds a docker image
1) Git for jenkins job https://github.com/ivorobey/docker-test


 'Setup cluster'
 
     vagrant up
     vagrant ssh master or I use (Lens to connect to the cluster (.kube/config)
 
 
 
 'First problem:' 
     kubectl get po --all-namespaces
     kube-flannel-ds-amd64... in Error or CrashloopBackoff status
     ip -4 addr show
     in kube-flanel fix iface=eth1


helm repo add jenkins https://charts.jenkins.io
helm repo update
helm upgrade --install myjenkins jenkins/jenkins --namespace jenkins

2)Second problem: pod ( pending status )
Persistent Volume Claim
I configure values.yaml for me persistance:false and (resource,adminpassword) 
helm upgrade --install myjenkins jenkins/jenkins --namespace jenkins -f values.yaml

Then configure jenkins (add screenshot)
 
