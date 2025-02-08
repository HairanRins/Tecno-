# Des termes et concepts techniques essentiels à maîtriser dans les domaines du **développement Backend**, des **bases de données**, de **Docker** et des **notions OPS**.

---

## **Développement Backend**
1. **API (Application Programming Interface)** – Interface permettant la communication entre différentes applications.
2. **REST (Representational State Transfer)** – Style d’architecture d’API basé sur HTTP.
3. **GraphQL** – Alternative à REST permettant aux clients de requêter uniquement les données nécessaires.
4. **Middleware** – Composant qui intercepte et traite les requêtes avant qu’elles atteignent l’application.
5. **ORM (Object-Relational Mapping)** – Outil qui permet d’interagir avec une base de données via des objets (ex: Sequelize, Hibernate, SQLAlchemy).
6. **JWT (JSON Web Token)** – Format de token sécurisé utilisé pour l’authentification et l’autorisation.
7. **OAuth2** – Protocole d’authentification sécurisé souvent utilisé pour les connexions avec des tiers.
8. **WebSocket** – Protocole permettant une communication bidirectionnelle en temps réel entre un client et un serveur.
9. **Load Balancer (Équilibreur de charge)** – Répartit le trafic réseau sur plusieurs serveurs pour améliorer la performance et la fiabilité.
10. **Microservices** – Architecture logicielle divisant une application en plusieurs services indépendants.
11. **Monolithe** – Architecture logicielle où toute l’application est regroupée dans un seul codebase.
12. **Rate Limiting** – Technique permettant de limiter le nombre de requêtes par utilisateur pour éviter les abus.
13. **Caching** – Stockage temporaire des données pour améliorer la rapidité des réponses (ex: Redis, Memcached).
14. **Reverse Proxy** – Serveur intermédiaire qui récupère les requêtes client avant de les envoyer aux serveurs backend (ex: Nginx).
15. **CQRS (Command Query Responsibility Segregation)** – Séparation des opérations de lecture et d’écriture pour optimiser les performances.

---

## **Bases de Données**
1. **SQL (Structured Query Language)** – Langage de requêtage pour les bases de données relationnelles.
2. **NoSQL** – Type de base de données non relationnelle (ex: MongoDB, Cassandra).
3. **ACID (Atomicity, Consistency, Isolation, Durability)** – Propriétés garantissant la fiabilité des transactions en bases de données relationnelles.
4. **BASE (Basically Available, Soft state, Eventually consistent)** – Principe utilisé par certaines bases NoSQL pour la scalabilité.
5. **Indexation** – Optimisation des bases de données pour accélérer les requêtes.
6. **Sharding** – Technique de partitionnement des bases de données pour la scalabilité.
7. **Replication** – Copie des données sur plusieurs serveurs pour améliorer la disponibilité.
8. **Transactions** – Groupe d’opérations SQL exécutées ensemble.
9. **Stored Procedures** – Scripts SQL stockés et exécutés dans la base de données.
10. **ORM (Object-Relational Mapping)** – Permet d’interagir avec une base via des objets au lieu d’écrire des requêtes SQL brutes.
11. **ETL (Extract, Transform, Load)** – Processus de migration et transformation des données entre systèmes.
12. **Schema Migration** – Processus de modification de la structure de la base de données sans perdre de données.

---

## **Docker et Conteneurisation**
1. **Dockerfile** – Fichier définissant l’image Docker à créer.
2. **Image Docker** – Modèle immuable d’un conteneur, basé sur un Dockerfile.
3. **Conteneur** – Instance isolée d’une application, basée sur une image Docker.
4. **Docker Compose** – Outil permettant d’orchestrer plusieurs conteneurs via un fichier `docker-compose.yml`.
5. **Docker Registry** – Dépôt pour stocker et partager des images Docker (ex: Docker Hub).
6. **Volume Docker** – Stockage persistant utilisé par les conteneurs.
7. **Bind Mounts** – Montage d’un dossier local dans un conteneur Docker.
8. **Entrypoint & CMD** – Commandes définissant le comportement d’un conteneur au démarrage.
9. **Networking Docker** – Gestion des réseaux entre les conteneurs.
10. **Build Context** – Dossier utilisé lors de la création d’une image Docker.
11. **Multi-stage Builds** – Technique pour optimiser les images Docker en réduisant leur taille.
12. **Overlay Network** – Réseau virtuel permettant la communication entre conteneurs sur plusieurs hôtes.

---

## **Notions OPS et DevOps**
1. **CI/CD (Continuous Integration / Continuous Deployment)** – Automatisation du test et du déploiement du code.
2. **Pipeline CI/CD** – Suite d’étapes automatisées pour construire, tester et déployer une application.
3. **Infrastructure as Code (IaC)** – Gestion de l’infrastructure via du code (ex: Terraform, Ansible).
4. **Kubernetes (K8s)** – Orchestrateur de conteneurs Docker.
5. **Helm** – Gestionnaire de packages pour Kubernetes.
6. **Load Balancing** – Répartition du trafic réseau pour éviter les surcharges de serveurs.
7. **Monitoring & Logging** – Surveillance des performances des systèmes et collecte des logs (ex: Prometheus, Grafana, ELK Stack).
8. **Scaling (Vertical & Horizontal)** – Techniques pour augmenter la capacité d’un système (vertical = plus de ressources, horizontal = plus de serveurs).
9. **Failover** – Basculer automatiquement vers un système de secours en cas de panne.
10. **Blue-Green Deployment** – Technique de déploiement avec deux environnements (un actif, un en attente).
11. **Canary Deployment** – Déploiement progressif d’une nouvelle version d’une application.
12. **Service Mesh** – Gestion avancée de la communication entre microservices (ex: Istio).
13. **Reverse Proxy & API Gateway** – Contrôle et sécurisation des requêtes (ex: Nginx, Traefik).
14. **Secrets Management** – Gestion sécurisée des clés API et mots de passe (ex: HashiCorp Vault).
15. **Observability** – Capacité à surveiller un système grâce à des logs, métriques et traces.
16. **Rolling Updates** – Déploiement progressif d’une mise à jour sans interrompre le service.

---

### **Conclusion**
La maîtrise de ces concepts est essentielle pour tout développeur Backend ou ingénieur DevOps. Selon votre niveau et vos besoins, vous pouvez approfondir chaque sujet en explorant des ressources spécifiques, des tutoriels et des documentations officielles. 
