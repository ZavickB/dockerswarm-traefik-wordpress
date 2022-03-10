# dockerswarm-traefik-wordpress

- Créer 1 machine virtuelle sous Ubuntu
- Passer en connexion en accès par pont
- Mettre une IP fixe 
- Dupliquer 2 fois la VM et changer changer leurs IP
- Créer un réseau scopé sur le swarm `docker network create --driver=overlay traefik-public`

### Mise en place de docker Swarm

- Lancer la commande `docker swarm init` sur la 1ere VM ('manager')
- Récupérer la réponse et l'éxécuter sur les deux autres VM ('worker1' et 'worker2')

### Mise en place des services

- Cloner le projet dans un dossier sur 'manager' et s'y rendre
- Lancer la commande `docker stack deploy traefik --compose-file docker-compose.yml` sur 'manager'

### Situation

J'ai suivi la documentation sur docker swarm.

Je vois les services présents avec `docker service ls` en revanche sur chacun des services il est indiqué dans la cellule "REPLICAS" : "0/x" ..
