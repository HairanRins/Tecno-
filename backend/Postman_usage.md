# Postman 

**Postman** est un outil populaire utilisé pour tester, développer et documenter des **API (interfaces de programmation d'application)**. Il fournit une interface graphique pour envoyer des requêtes HTTP à des serveurs web et examiner les réponses. Voici une vue d'ensemble des **fondamentaux de Postman** et quelques **exemples pratiques** :

---

## **1. Concepts fondamentaux**

### **a. Requêtes HTTP**

Postman permet d’envoyer tous les types de requêtes HTTP :

* `GET` : Récupérer des données
* `POST` : Envoyer des données
* `PUT` / `PATCH` : Mettre à jour des données
* `DELETE` : Supprimer des données

### **b. URL de l’API**

C’est l’adresse à laquelle la requête est envoyée (ex: `https://api.exemple.com/users`).

### **c. En-têtes (Headers)**

Utilisés pour envoyer des informations supplémentaires comme le type de contenu ou les tokens d'authentification.

### **d. Corps (Body)**

Utilisé dans les requêtes `POST`, `PUT`, etc., pour envoyer des données (JSON, formulaire, etc.).

### **e. Paramètres**

* **Query Params** (`?clé=valeur`) : pour ajouter des données à l’URL
* **Path Params** (`/users/:id`) : partie de l’URL remplacée dynamiquement
* **Variables d’environnement** : pour réutiliser des valeurs dynamiques (tokens, URLs, etc.)

---

## **2. Exemples d’utilisation**

### **Exemple 1 : Requête GET**

**But :** Obtenir la liste des utilisateurs

* **Méthode :** `GET`
* **URL :** `https://api.exemple.com/users`
* **Headers :**

  ```json
  {
    "Authorization": "Bearer <token>"
  }
  ```
* **Résultat :** Liste d'utilisateurs en JSON

---

### **Exemple 2 : Requête POST**

**But :** Créer un nouvel utilisateur

* **Méthode :** `POST`
* **URL :** `https://api.exemple.com/users`
* **Headers :**

  ```json
  {
    "Content-Type": "application/json"
  }
  ```
* **Body (raw / JSON) :**

  ```json
  {
    "name": "Alice",
    "email": "alice@example.com"
  }
  ```
* **Résultat :** Détail de l'utilisateur créé

---

### **Exemple 3 : Utilisation de variables**

* Définir une variable d’environnement `{{base_url}}` = `https://api.exemple.com`
* Utiliser dans l’URL : `{{base_url}}/users`

Cela permet de changer rapidement l’environnement (développement, test, production).

---

### **Exemple 4 : Tests automatisés**

Dans l'onglet **Tests**, ajouter :

```javascript
pm.test("Statut 200 OK", function () {
    pm.response.to.have.status(200);
});
```

Permet de valider automatiquement les réponses.

---

## **3. Autres fonctionnalités utiles**

* **Collections :** Grouper et organiser les requêtes liées à une API
* **Tests et scripts pre-request :** Ajouter de la logique personnalisée
* **Monitor :** Exécuter des requêtes à intervalles réguliers
* **Mock Server :** Simuler des réponses pour tester sans back-end

---

