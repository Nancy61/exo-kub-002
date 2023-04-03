PETITE DESCRIPTION DU PROJET

Pour commencer:
Ce projet est un exemple de déploiement d'une application nodejs via kubernetes.

Pré-requis:
-Node.js v16.14.2.
-npm v8.6.0.
-docker desktop
-kubernetes
-git clone https://github.com/Nancy61/exo-kub-002

Comment j'ai envoyé l'image sur dockerhub:
J'ai exécuté les commandes suivantes:
    docker build -t exo2-kub . 
    docker run --name test-exo2kub -d -p 8080:8080 exo2-kub
    docker tag exo2-kub nancylence/exo2-kub
    docker push nancylence/exo2-kub

Comment j'ai envoyé le projet sur git:
1-Créer un nouveau repo public sur mon git
2-Ensuite j'ai exécuté les commandes suivantes sur mon terminal:
    git init
    git add .
    git remote add origin https://github.com/Nancy61/exo-kub-002.git
    git push -f origin main 

Comment déployer l'application:
1-Connectez-vous sur votre terminal en tant qu'administrateur.
2-Saisissez les commandes suivantes:
   2-1 kubectl create deployment exo1-deployment --image nancylence/exo2-kub
   2-2 kubectl get deployment #pour vérifier la création de votre déploiement.
    2-3 kubectl expose deployment exo1-deployment --port 80 --type LoadBalancer
    2-4 kubectl get svc   #pour vérifier la création de votre service
    2-5 minikube service exo1-deployment  #vérifier le déploiement sur votre localhost
    2-6 kubectl scale deployment/exo1-deployment --replicas 6
    2-7 kubectl get pods   #si vous souhaitez augmenter le nombre de vos pods

NB:
Si vous avez déjà déployé un site qui écoute sur le port 8080, pensez à le supprimer avant de déployer cette application avec la commande:
    - kubectl delete svc example-deployment
