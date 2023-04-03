PETITE DESCRIPTION DU PROJET

Pour commencer:
Ce projet est un exemple de déploiement d'une application nodejs via kubernetes.

Pré-requis:
-Node.js v16.14.2.
-npm v8.6.0.
-docker desktop
-kubernetes
-git clone https://github.com/Nancy61/exo-kub-002

Comment déployer l'application:
1-Connectez-vous sur votre terminal en tant qu'administrateur.
2-Saisissez les commandes suivantes:
   2-1 kubectl create deployment exo1-deployment --image nancylence/apptest
   2-2 kubectl get deployment #pour vérifier la création de votre déploiement.
    2-3 kubectl expose deployment exo1-deployment --port 80 --type LoadBalancer
    2-4 kubectl get svc   #pour vérifier la création de votre service
    2-5 minikube service exo1-deployment  #vérifier le déploiement sur votre localhost
    2-6 kubectl scale deployment/exo1-deployment --replicas 6
    2-7 kubectl get pods   #si vous souhaitez augmenter le nombre de vos pods

NB:
Si vous avez déjà déployé un site qui écoute sur le port 80, pensez à le supprimer avant de déployer cette application avec la commande:
    - kubectl delete svc example-deployment
