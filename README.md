git init

git remote add origin https://github.com/<user>/site-html.git

git add .

git commit -m "Ajout site HTML"

git branch -M main

git push -u origin main


# Créer l'app depuis GitHub avec le builder HTTPD
oc new-app registry.access.redhat.com/ubi8/httpd-24~https://github.com/<user>/site-html.git --name=site-html

# Vérifier que ça tourne
oc get pods
oc get svc

# Exposer une route publique
oc expose service site-html

# Récupérer l'URL et tester
oc get route


Déploiement réussi Bienvenue sur ma page !

<img width="2985" height="732" alt="image" src="https://github.com/user-attachments/assets/ddb7a0fb-10c3-4085-8b0a-b75d6ff5d61f" />

