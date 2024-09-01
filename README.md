# TP_DevOps_Kubernetes

# Créer un cluster k8s
```
minikube start
minikube status
```

# Déployer l'application (peut mettre plus de 3 minutes)
```
kubectl apply -f mysql-deployment.yaml
kubectl get pods
```

# Attendre que les pods soient en status "Ready"

# Vérifier que la base de donnée webapp est présente
```
kubectl run -it --rm --image=mysql --restart=Never mysql-client -- mysql -h mysql -proot
SHOW DATABASES;
exit
```

# Déployer l'application (peut mettre plus de 5 minutes)
```
kubectl apply -f api-deployment.yaml
kubectl get pods
minikube service api --url
```

# Attendre que les pods soient en status "Ready"

# Déployer l'application (peut mettre plus de 5 minutes)
remplace la valeur de REACT_APP_API_URL par l'url donné auparavant dans le fichier webapp-deployment.yaml (sans http://)
```
kubectl apply -f webapp-deployment.yaml
kubectl get pods
```

# Attendre que les pods soient en status "Ready"

# Tester l'application web
```
minikube service webapp
```

# Détruire le cluster k8s
```
minikube delete
```