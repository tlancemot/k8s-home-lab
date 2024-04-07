# LAB
Cette arbo. est pour la configuration du cluster Kind 

Il va configurer un cluster avec : 
    
    Un Control Plane
    Deux workers
    Une exposition de port HTTP (80)
    Une exposition de port HTTPS (443)


# Configuration du cluster

Pour configurer le cluster il suffit d'executer : 

        kind create cluster --config=cluster-config.yml


On va y ajouer un ingress Nginx sur les ports exposés : 

        kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml



Notre cluster est prêt pour la suite! 

On supposera pour la suite que notre lab utilisera le suffix : `*.lab` (exemple : xxx.lab) 