Commentaires TP1
On a lancé docker run hello-world, le conteneur s’est exécuté et a affiché un message. Ensuite On a utilisé docker ps -a pour voir la liste des conteneurs et on a constaté qu’il s’est arrêté tout seul après l’exécution.

Commentaires TP2

On a lancé un serveur Nginx avec docker run -d -p 8080:80 --name montest nginx. On a vu que le conteneur tourne en arrière-plan et que le port 8080 de la machine est relié au port 80 du conteneur. En ouvrant http://localhost:8080, on voit la page d’accueil de Nginx. Avec docker logs montest, on voit les requêtes du serveur. Enfin, après docker stop et docker rm, le conteneur s’arrête et n’est plus accessible.

Commentaires TP3

On a relancé un conteneur Nginx avec docker run -d --name montest2 nginx. On a pu entrer dans le conteneur avec docker exec -it montest2 sh. À l’intérieur, on a exploré le système de fichiers avec ls, puis on est allé dans /usr/share/nginx/html pour voir les fichiers du site. Ensuite, on a quitté avec exit. Enfin, on a supprimé le conteneur avec docker rm -f montest2.

Commentaires TP4

On a créé un dossier avec un fichier index.html contenant un titre HTML. On a aussi créé un Dockerfile avec FROM nginx:alpine et COPY index.html /usr/share/nginx/html/index.html. On a observé que la commande docker build -t mon-site . permet de créer une image personnalisée à partir de ces fichiers. Ensuite, en lançant le conteneur avec docker run -d -p 8080:80 --name monsite mon-site, on voit notre propre page s’afficher dans le navigateur à la place de la page Nginx. Enfin, après suppression du conteneur avec docker rm -f monsite, le site n’est plus accessible.

Commentaires TP5

On a créé un fichier docker-compose.yml avec un service utilisant l’image nginx:alpine et le port 8080:80. On a observé que docker compose up -d permet de lancer automatiquement le conteneur sans écrire une longue commande. En ouvrant http://localhost:8080, on voit la page d’accueil de Nginx. Avec docker compose down, on arrête et on supprime .