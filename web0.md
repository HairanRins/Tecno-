# 🌐 Concepts Web

1. [🌍 URL (Uniform Resource Locator)](#url-uniform-resource-locator)
2. [🔗 Protocole HTTP (Hypertext Transfer Protocol)](#protocole-http-hypertext-transfer-protocol)
3. [🔒 Protocole HTTPS (Hypertext Transfer Protocol Secure)](#protocole-https-hypertext-transfer-protocol-secure)
4. [🖥️ Client et Serveur](#client-et-serveur)
5. [📂 Concepts Liés](#concepts-liés)

---

### 🌍 URL (Uniform Resource Locator)
Une **URL** est l'adresse d'une ressource sur le web. Elle est composée de plusieurs parties qui identifient le protocole, le serveur et l'emplacement de la ressource.

```
https://www.example.com:443/recherche?q=chatons#section1
```

![Capture d’écran du 2024-11-13 15-50-37](https://github.com/user-attachments/assets/7cb122e6-767a-4a46-a8e7-8390bc706056)

💡 Exemple : Une URL dans le navigateur permet de récupérer et d'afficher une ressource, telle qu'une page web ou une image.

### 🔗 Protocole HTTP (Hypertext Transfer Protocol)
HTTP est le protocole principal utilisé pour transférer des données sur le web.
* Fonctionnement : Le client (navigateur) envoie une requête au serveur, qui retourne une ressource.
* Requêtes HTTP :
    * ``GET`` : Récupérer des données
    * ``POST`` : Envoyer des données
    * ``PUT`` : Mettre à jour des données
    * ``DELETE`` : Supprimer une ressource

Exemple : GET /index.html

🚀 Cas pratique : Lorsqu'un utilisateur tape une URL, une requête HTTP est envoyée pour afficher la page demandée.

### 🔒 Protocole HTTPS (Hypertext Transfer Protocol Secure)
HTTPS est la version sécurisée de HTTP, utilisée pour chiffrer les données échangées.
  * **Avantages de HTTPS** : Protège les données en empêchant leur interception.
  * **Usage** : Utilisé pour les transactions bancaires, sites de commerce, etc.

🔐 Exemple concret : Les sites de banque utilisent HTTPS pour protéger les informations des utilisateurs.

### 🖥️ Client et Serveur
Le modèle **client-serveur** est une architecture dans laquelle le client envoie des requêtes et le serveur fournit les réponses.

![Capture d’écran du 2024-11-13 15-57-47](https://github.com/user-attachments/assets/bcf8dbf9-3fa4-4a8e-afbb-701ea1b624e3)


### 📂 Concepts Liés
Quelques concepts essentiels pour bien comprendre le web :

  * **DNS** (Domain Name System) : Traduit les noms de domaine en adresses IP.
  * **Cookies 🍪** : Fichiers stockés par le client pour garder l'état (comme rester connecté).
  * **Cache 🗃️** : Mémoire temporaire pour stocker les ressources et charger plus rapidement.
  * **Sessions et JWT** : Utilisés pour garder l'état d'authentification entre les requêtes.

### 🔍 Exemple Global : Accéder à une URL sécurisée
Lorsque vous accédez à **https://www.example.com/recherche?q=chatons**, voici les étapes :
  1. Le **navigateur** envoie une requête HTTPS au serveur.
  2. Le **serveur** répond avec la page demandée.
  3. Le navigateur télécharge les images ou scripts additionnels si nécessaires.
  4. Le serveur envoie des cookies pour maintenir la session.

      
