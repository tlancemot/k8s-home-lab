# Dashboard


## Installation

    kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml

## Création de l'utilisateur

    kubectl -n kubernetes-dashboard create token admin-user