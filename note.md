# API (Application Programming Interface) 

* Une API, c'est comme un serveur au restaurant prenant et livrant vos commandes.

* Une API, c’est comme un serveur au restaurant : vous (l’application) commandez un plat (données), le serveur (API) le transmet au chef (système) et vous rapporte votre commande.

* Toujours tenté de créer et de concevoir une API : performante , simple et maintenable 

## Les principes fondamentaux de création et de conception d'API

* **1. Compréhension des besoins**

-  ***Définir les objectifs*** : Pourquoi créer cette API ? Quels services ou données doit-elle fournir ?
-  ***Identifier les utilisateurs*** : Quels types de clients (frontends, autres serveurs) utiliseront l'API ?
- ***Analyser les flux de données*** : Déterminer les entrées, sorties et transformations des données.

* **2. Types d'API**

- ***RESTful API*** : Basée sur HTTP avec des principes comme les ressources, les verbes HTTP (GET, POST, PUT, DELETE) et les statuts HTTP.
- ***GraphQL*** : Permet aux clients de spécifier les données exactes dont ils ont besoin via des requêtes et mutations.
- ***SOAP*** : Plus ancien, basé sur XML et des protocoles formels, adapté à des environnements sécurisés complexes.
- ***gRPC*** : Utilise Protobuf (Protocol Buffers : Format binaire, rapide, compact) pour les communications rapides entre services. 

* **3. Principes de conception**

- ***a) Utiliser les normes HTTP***

**// Verbes HTTP** : 

* `GET` : Récupérer des ressources.
* `POST` : Créer une nouvelle ressource.
* `PUT` : Modifier ou remplacer une ressource..
* `DELETE` : Supprimer une ressource.

**// Status HTTP** : 

* `200 OK` : Succès.
* `201 Created` : Ressource créée.
* `400 Bad Request` : Requête invalide.
* `404 Not Found` : Ressource introuvable.

- ***b) Conception basée sur les ressources***

* Les **ressources** sont identifiées par des URI (Uniform Resource Identifiers). Exemple : 
  - `/users` : Liste d'utilisateurs.
  - `/users/{id}` : Détails d'un utilisateur spécifique.

- ***c) Respecter les principes REST***

* **Stateless** : Chaque requête doit être autonome et contenir toutes les informations nécessaires.
* **Cacheable** : Les réponses doivent pouvoir être mises en cache si approprié.
* **Layered System** : Les interactions peuvent passer par des couches intermédiaires (proxy, load balancer).

- ***d) Sécurité***

* **Authentification** : Utiliser des protocoles comme OAuth 2.0, JWT pour sécuriser les API.
* **Chiffrement** : Toujours utiliser HTTPS pour protéger les données en transit.
* **Validation** : Vérifier et filtrer les entrées des utilisateurs pour éviter les attaques (ex. : injections SQL, XSS).

* **4. Outils et technologies courantes**

- *Frameworks Backend* : Express.js (Node.js), Flask (Python), Django, Spring Boot (Java), FastAPI.
- *Documentation* : Swagger / OpenAPI pour décrire l’API.
- *Test* : Postman, Insomnia pour tester les requêtes.

* **5. Étapes de création d'une API RESTful**

- a) **Planification :**
  
    // Créer un schéma de base pour les endpoints.
    // Définir les structures des données (JSON).

- b) **Création des routes :**
     
    // Associer chaque endpoint à un verbe HTTP.

- c) **Connexion à une base de données :**
     
    // Permettre la persistance des données avec des outils comme MySQL, MongoDB, ou PostgreSQL.

- d) **Mise en place des middlewares :**
     
    // Pour gérer la sécurité, le logging, et la validation des requêtes.

- e) **Tests :**
     
    // Tester manuellement avec des outils comme Postman ou automatiser les tests avec des frameworks comme Jest, Pytest, ou Mocha.

* **6. Bonnes pratiques**

- ***Simplicité et cohérence***: Garder une structure claire et logique.
- ***Pagination et filtres*** : Faciliter la gestion de grandes quantités de données.
- ***Versionnement*** : Ex. : ``/api/v1/users``.
- ***Documentation claire*** : S'assurer que les utilisateurs comprennent comment interagir avec l’API.



