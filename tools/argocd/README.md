# ArgoCD

Nous allons installer argoCD sur notre cluster Kind afin de pouvoir faire du GitOps sur notre cluster et dans le but d'utiliser ArgoCD avec Crossplane plus tard


## Installation

On part sur de la conf de base pour notre infra de lab : 

    kubectl create namespace argocd
    kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml

On ne prends pas que la core non plus, on va utiliser l'UI et utiliser notre ingress Nginx pour exposer l'UI d'argoCD

On supposera que argoCD sera accessible à l'adresse suivante: argocd.lab

## Configuration

Une fois l'installation terminée nous allons appliquer une configuration pour permettre d'exposer l'UI d'ArgoCD sur l'ingress que nous avons configuré précedemment : 

    kubectl apply -f ingress-argocd.yml


## Connexion

Une fois la configuration ingress appliquer on peut se connecter sur :

    https://argocd.lab/

Le compte administrateur par défaut est : admin et le password est stocké dans un secret K8s : 
    kubectl -n argocd get secret argocd-initial-admin-secret -o jsonpath="{.data.password}" | base64 -d