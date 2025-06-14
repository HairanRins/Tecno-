# Les **bases et fondamentaux de Firebase**

---

## 🧱 **1. Qu’est-ce que Firebase ?**

**Firebase** est une **plateforme Backend-as-a-Service (BaaS)** développée par Google. Elle fournit des **services cloud prêts à l’emploi** pour créer des **applications web et mobiles** rapidement sans gérer un backend complexe.

---

## 🚀 **2. Les services principaux de Firebase**

### 2.1 🔥 Firestore / Realtime Database

* **Base de données NoSQL cloud**.
* Firestore est plus moderne et structuré par **collections** et **documents**.

**Exemple (Firestore) :**

```json
/users
  └── user123
        ├── name: "Alice"
        └── age: 25
```

### 2.2 🔐 Authentication

* Gère les **inscriptions** et **connexions**.
* Supporte : **email/mot de passe**, **Google**, **Facebook**, **Apple**, **anonyme**, etc.

**Exemple :**

```js
firebase.auth().createUserWithEmailAndPassword(email, password)
```

### 2.3 📦 Firebase Storage

* Pour **stocker des fichiers** (images, PDF, vidéos, etc.).
* Très utilisé avec les apps de chat, réseaux sociaux, etc.

**Exemple :**

```js
firebase.storage().ref('avatars/user123.jpg').put(file)
```

### 2.4 📩 Cloud Messaging (FCM)

* Envoie de **notifications push**.
* Compatible avec Android, iOS et le web.

### 2.5 ☁️ Firebase Functions

* **Code backend** sans serveur (Serverless).
* Exécuté sur des événements (ex : utilisateur inscrit, document modifié).

**Exemple :**

```js
exports.sendWelcomeEmail = functions.auth.user().onCreate((user) => {
  // envoyer un e-mail de bienvenue
});
```

---

## 🛠️ **3. Installation et configuration**

### Étapes :

1. Aller sur [https://console.firebase.google.com](https://console.firebase.google.com)
2. Créer un projet Firebase
3. Ajouter une app (Web, Android, iOS)
4. Copier les **informations de configuration** (clé API, etc.)

### Pour une app web :

```html
<script src="https://www.gstatic.com/firebasejs/10.0.0/firebase-app.js"></script>
<script>
  const firebaseConfig = {
    apiKey: "XXXX",
    authDomain: "XXXX.firebaseapp.com",
    projectId: "XXXX",
    storageBucket: "XXXX.appspot.com",
    messagingSenderId: "XXXX",
    appId: "XXXX"
  };
  firebase.initializeApp(firebaseConfig);
</script>
```

---

## 🧠 **4. Concepts fondamentaux**

### 🔄 Base NoSQL : clé-valeur imbriquée

* Pas de tables, mais des documents JSON.
* Structuration par `collections > documents`.

### 📡 Temps réel

* Realtime Database et Firestore permettent de **recevoir automatiquement les changements**.

**Exemple (écoute Firestore) :**

```js
firebase.firestore().collection('messages')
  .onSnapshot(snapshot => {
    snapshot.forEach(doc => console.log(doc.data()))
  })
```

### 🔐 Sécurité par règles

* Chaque service Firebase peut être **protégé par des règles**.

**Exemple de règles Firestore :**

```js
match /users/{userId} {
  allow read, write: if request.auth.uid == userId;
}
```

---

## 🎯 **5. Cas d’utilisation typiques**

| Cas                    | Services utilisés             |
| ---------------------- | ----------------------------- |
| App de chat            | Auth, Firestore, Storage, FCM |
| Réseau social          | Auth, Firestore, Storage      |
| App de suivi personnel | Firestore + Auth              |
| Dashboard admin        | Firestore + Functions         |

---

## 📌 **6. Avantages et limites**

### ✅ Avantages :

* Temps réel facile
* Backend prêt à l’emploi
* Intégration facile avec Flutter, React Native, etc.
* Gratuite pour les petits projets (plan Spark)

### ⚠️ Limites :

* Pas adapté à tous les projets très complexes
* Coût à surveiller sur les gros volumes
* Structure NoSQL peut nécessiter duplication de données

---

## 🧪 **7. Exemple simple d'une app : liste de tâches (ToDo)**

```js
// Ajouter une tâche
firebase.firestore().collection("todos").add({
  text: "Apprendre Firebase",
  done: false
})

// Écouter les tâches en temps réel
firebase.firestore().collection("todos").onSnapshot(snapshot => {
  snapshot.forEach(doc => {
    console.log(doc.id, doc.data())
  })
})
```

---

## 📚 **8. Ressources utiles**

* [Docs officielles Firebase](https://firebase.google.com/docs)
* [Exemples sur GitHub](https://github.com/firebase/)
* [Codelabs Firebase](https://firebase.google.com/codelabs)

---
