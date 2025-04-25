# Manipulation de fichiers

Le terme **"Blob"** revient souvent en dev, surtout quand tu manipules des fichiers, des images ou des données binaires. Voici un petit tour des concepts liés 👇

---

### 🔵 **Blob (Binary Large Object)**

Un **Blob** est un **objet de données binaires** brutes. En JavaScript (dans le navigateur), il est souvent utilisé pour représenter :
- des **fichiers** (ex: images, vidéos, audio, PDF, etc.)
- du **contenu généré dynamiquement** (ex: un fichier créé en JS)
  
Par exemple :
```js
const blob = new Blob(["Hello world!"], { type: "text/plain" });
```
Ici, on crée un fichier texte à la volée.

---

### 📥 **File**

C'est une classe JavaScript qui hérite de `Blob`, mais avec des **métadonnées** supplémentaires comme le nom du fichier.

```js
const file = new File(["Hello"], "greeting.txt", { type: "text/plain" });
```

> `File` = `Blob` + nom + type + date de dernière modification.

---

### 🧪 **FormData**

Permet d’envoyer des fichiers (ou autres champs) via `fetch()` ou `XMLHttpRequest`, souvent pour les formulaires `multipart/form-data`.

```js
const formData = new FormData();
formData.append("file", file);
```

---

### 🧠 **URL.createObjectURL(blob)**

Permet de **générer une URL temporaire** pour afficher un Blob dans le navigateur (ex: prévisualiser une image avant upload).

```js
const url = URL.createObjectURL(blob);
img.src = url;
```

---

### 🔄 **Blob vs Base64**

- **Blob** : données binaires (plus léger, plus rapide pour les fichiers)
- **Base64** : version encodée en texte (plus simple à manipuler dans certains cas, mais plus lourd)

---
