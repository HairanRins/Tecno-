# General Concepts

Voici une liste des **termes techniques courants sur le web**, notamment des concepts comme **socket**, avec leurs **explications**, **exemples** concrets et **cas d'utilisation**. C'est super utile à connaître si tu bosses sur des applis web ou mobiles !

---

## 🌐 1. **Socket**

### ➤ Définition :
Un **socket** est un point de communication permettant à deux machines (ou programmes) de communiquer entre elles, souvent en temps réel.

### ➤ Exemple :
Un **chat en temps réel** utilise des sockets pour envoyer/recevoir des messages sans recharger la page.

### ➤ Cas d'utilisation :
- Applis de messagerie (WhatsApp Web)
- Jeux en ligne
- Mises à jour en temps réel (ex : notifications, commentaires)

### ➤ Tech utilisée :
- **WebSocket** : protocole permettant une connexion bidirectionnelle persistante entre client et serveur.
- Ex. avec **Socket.IO** en Node.js :
```js
// Côté serveur
io.on('connection', (socket) => {
  socket.on('message', (data) => {
    io.emit('message', data);
  });
});

// Côté client
socket.emit('message', "Hello world!");
```

---

## 📡 2. **API (Application Programming Interface)**

### ➤ Définition :
Une **API** permet à différentes applications de **communiquer entre elles**.

### ➤ Exemple :
Une appli météo qui affiche la température actuelle en se connectant à une **API météo externe**.

### ➤ Cas d'utilisation :
- Applis web/mobile qui ont besoin de données externes
- Authentification via Google ou Facebook
- Applis de paiement (Stripe, PayPal)

---

## 📦 3. **REST & RESTful API**

### ➤ Définition :
Une **API REST** respecte des règles spécifiques basées sur le protocole HTTP. Elle utilise des **verbes HTTP** comme GET, POST, PUT, DELETE.

### ➤ Exemple :
- `GET /users` → récupérer tous les utilisateurs
- `POST /users` → créer un utilisateur

### ➤ Cas d'utilisation :
- Presque toutes les API web modernes
- Backends (ex. Node.js, Django, Laravel)

---

## 🔄 4. **CRUD**

### ➤ Définition :
Acronyme de **Create, Read, Update, Delete** — les 4 opérations de base sur une base de données.

### ➤ Exemple :
Sur une app de blog :
- Create : créer un article
- Read : afficher un article
- Update : modifier un article
- Delete : supprimer un article

---

## 🚦 5. **HTTP / HTTPS**

### ➤ Définition :
Protocole de communication utilisé entre les navigateurs et les serveurs web.

- **HTTP** : non sécurisé
- **HTTPS** : sécurisé via certificat SSL

### ➤ Exemple :
- `http://example.com`
- `https://example.com`

### ➤ Cas d'utilisation :
- Toute navigation web repose sur ces protocoles
- HTTPS est requis pour la sécurité (ex : e-commerce)

---

## ⚡ 6. **AJAX (Asynchronous JavaScript and XML)**

### ➤ Définition :
Technique permettant de **charger des données sans recharger la page**.

### ➤ Exemple :
Quand tu tapes une recherche sur Google, les résultats s'affichent sans recharger la page → c'est de l'AJAX.

### ➤ Cas d'utilisation :
- Recherche instantanée
- Filtres dynamiques
- Commentaires qui se chargent automatiquement

---

## 🧠 7. **JSON (JavaScript Object Notation)**

### ➤ Définition :
Format léger d’échange de données entre le client et le serveur.

### ➤ Exemple :
```json
{
  "name": "Alice",
  "age": 25
}
```

### ➤ Cas d'utilisation :
- Toutes les API modernes échangent les données en JSON
- Plus lisible et facile à parser que XML

---

## 🔐 8. **JWT (JSON Web Token)**

### ➤ Définition :
Un **jeton sécurisé** qui contient des infos (comme l’identifiant d’un utilisateur) utilisé pour l’authentification.

### ➤ Exemple :
Quand tu te connectes, le serveur te renvoie un JWT. Tu l’envoies à chaque requête pour prouver que tu es connecté.

---

## 🏁 9. **CORS (Cross-Origin Resource Sharing)**

### ➤ Définition :
Une **politique de sécurité** des navigateurs qui bloque les requêtes entre domaines différents sauf autorisation explicite.

### ➤ Exemple :
Ton frontend est sur `localhost:3000`, ton backend sur `localhost:5000` → tu dois activer CORS côté backend.

---

## 🏗️ 10. **CDN (Content Delivery Network)**

### ➤ Définition :
Un réseau de serveurs répartis géographiquement pour **accélérer la livraison de contenu** statique (images, JS, CSS…).

### ➤ Exemple :
- Cloudflare
- jsDelivr

### ➤ Cas d'utilisation :
- Sites à fort trafic
- Réduction de la latence

---


