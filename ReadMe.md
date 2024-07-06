# **M1 TP Kubernetes**
## Explications
L'archive n'est pas completement opérationnelle, voici les points ci-dessous : 
- Le déploiement 'front-deployement' est bien connecté au déploiement 'back-deployment'
- Le déploiement 'back-deployement' est bien connecté au déploiement 'db-deployment'

- Cependant les requêtes JS executés par le navigateur passent bien par le ingress mais semblent reset le chemin qui de ce fait est rejeté par l'api express du back-deployement.

# Instructions

To get started, execute the following **2 commands**:

```
kind create cluster --config .\cluster-config-v3.yml
kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/main/deploy/static/provider/kind/deploy.yaml
```

Then, to launch the application, execute the following commands in this order:

```
kubectl apply -f .\namespace.yml
kubectl create secret generic db-secret --from-env-file=secrets.properties --namespace=tp-namespace
kubectl apply -f .\ingress.yml
kubectl apply -f .\config-map.yml
kubectl apply -f .\volume.yml
kubectl apply -f .\deployments.yml
```
