# k8s-helloworld
kubernetes helloworld

## kubectl
1. get kubeconfig for cluster and verify with
 ```
 docker run --rm  \
    -v ~/.kube:/root/.kube \
    -v ${PWD}:/root/project \
    ksandermann/kubectl:v1.13.9 \
    kubectl cluster-info
 ```
1. inside the folder kubectl, change all occurrences of *changeme* to your name, i.e. *sandermann*
1. inside repository root folder, start the working environment with
 ```
 docker run -it --rm  \
    -v ~/.kube:/root/.kube \
    -v ${PWD}:/root/project \
    -w /root/project \
    ksandermann/cloud-toolbox:2019-09-19_02 \
    /bin/bash``
 ```
1. create k8s namespace using ```kubectl apply -f ./kubectl/namespace.yaml```
1. deploy to k8s using ```kubectl apply -f ./kubectl```
1. switch to new namespace using ksn *helloworld-changeme*
1. show your running pods using *kubectl get pods*
1. visit helloworld-changeme.k8s-devops.cndp.cloud in your browser. Refresh the page after 10 minutes to see a valid lets-encrypt certificate has been generated

## helm
tbd




