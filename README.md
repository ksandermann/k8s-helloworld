# k8s-helloworld
kubernetes helloworld

## kubectl
1. get kubeconfig for cluster, copy to ~/.kube/config and verify with
 ```
 docker run --rm  \
    -v ~/.kube:/root/.kube \
    -v ${PWD}:/root/project \
    --env-file <(env | grep -i proxy) \
    ksandermann/cloud-toolbox:latest \
    kubectl version
 ```
1. inside the folder kubectl, change all occurrences of *changeme* to your name, i.e. *sandermann*
1. inside repository root folder, start the working environment with
 ```
 docker run -it --rm  \
    -v ~/.kube:/root/.kube \
    -v ${PWD}:/root/project \
    -w /root/project \
    ksandermann/cloud-toolbox:latest \
    /bin/zsh
 ```
1. deploy to k8s using ```kubectl apply -f ./kubectl```
1. watch your pods going online using *watch kubectl get pods -n k8s-workshop-2019-11-25*
1. visit helloworld-changeme.k8s-devops.cndp.cloud in your browser. Refresh the page after 5 minutes to see a valid lets-encrypt certificate has been generated

## helm
tbd




