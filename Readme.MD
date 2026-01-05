## Understanding Argo CD



## Installation

    On our bastion host:- 

    kubectl create namespace argocd

    kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

    After this we have to go to the service and change the clusterIP to the LoadBalancer or use the below command to change the service type to LoadBalancer

    kubectl patch svc argocd-server -n argocd -p '{"spec": {"type": "LoadBalancer"}}'

    curl -sSL -o argocd-linux-amd64 https://github.com/argoproj/argo-cd/releases/latest/download/argocd-linux-amd64
    sudo install -m 555 argocd-linux-amd64 /usr/local/bin/argocd
    rm argocd-linux-amd64      >>> this command is for argocd CLI

    Now, in AWS console, check for the loadbalancer and hit it in a browser and we will see the ArgoCD UI

    argocd admin initial-password -n argocd

    take the password and login to the UI and the username is admin

    



