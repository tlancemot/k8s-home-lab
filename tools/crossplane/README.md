# Crossplane

## Installation

On récupère le repo helm `stable` 

    helm repo add crossplane-stable https://charts.crossplane.io/stable
    helm repo update

On installe Crossplane sur le namespace `crossplane`

    helm install crossplane \
    --namespace crossplane-system \
    --create-namespace crossplane-stable/crossplane 


## Contrôle

On vérifie que les 2 pods sont bien démarrés : 

    kubectl get pods -n crossplane-system