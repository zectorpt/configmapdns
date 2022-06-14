# Pre requirement - A cluster
How to deploy a custom DNS with a configmap and test it

1 - Deploy a new pod to test the name

kubectl apply -f https://raw.githubusercontent.com/zectorpt/pods/master/ubuntuts.yaml

2 - Enter the POD and test the name:

kubectl exec -it ubuntuts -- /bin/bash

Wait 2 minutes to allow ping to be installed. Inside the pod ping the name:

ping example1.org

In another window deploy the configmap:

kubectl apply -f https://raw.githubusercontent.com/zectorpt/configmapdns/main/customdns.yaml

kubectl delete configmap --namespace kube-system coredns-custom

