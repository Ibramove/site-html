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


