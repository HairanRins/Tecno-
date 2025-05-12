# OpenAPI

**OpenAPI** (anciennement connu sous le nom de **Swagger**) est une **spécification** standardisée pour décrire des **API REST**. Elle permet de définir de manière claire, lisible par les humains et les machines, comment une API fonctionne : ses routes, les méthodes HTTP, les paramètres, les corps de requêtes, les réponses, etc.

---

## 🔧 Définition technique

OpenAPI est une spécification écrite généralement au format **YAML** ou **JSON** qui décrit l'ensemble des endpoints (routes), leurs paramètres, leurs types de réponse, les codes d'erreur, les schémas de données, etc.

---

## 🧩 Exemple simple (en YAML)

```yaml
openapi: 3.0.0
info:
  title: Exemple d'API
  version: 1.0.0
paths:
  /utilisateurs:
    get:
      summary: Liste des utilisateurs
      responses:
        '200':
          description: Succès
          content:
            application/json:
              schema:
                type: array
                items:
                  type: object
                  properties:
                    id:
                      type: integer
                    nom:
                      type: string
```

Ce fichier décrit une API avec une route `GET /utilisateurs` qui retourne une liste d’utilisateurs.

---

## 🎯 Cas d’usage (use cases)

1. **Documentation interactive automatique**

   * Génération de docs avec Swagger UI ou Redoc
   * Permet aux développeurs d’interagir avec l’API via une interface web

2. **Génération de code**

   * Client SDK (TypeScript, Python, etc.) ou serveur stub à partir du fichier OpenAPI

3. **Tests automatisés**

   * Outils comme Postman, Dredd ou Prism peuvent tester la conformité d'une API réelle à la spécification

4. **Validation des requêtes/réponses**

   * Middleware (ex : Express + openapi-validator) pour valider les entrées/sorties d’une API

5. **Interopérabilité**

   * Permet de standardiser les échanges entre services dans les architectures microservices

---

## 🚀 Outils et implémentations populaires

### 🔹 Génération de documentation

* **Swagger UI** : Interface web interactive générée à partir d’un fichier OpenAPI
* **Redoc** : Documentation statique ou interactive de belle qualité

### 🔹 Génération de code

* **OpenAPI Generator** : Génère des clients/serveurs (plus de 40 langages)
* **Swagger Codegen** : Ancien générateur, moins maintenu que OpenAPI Generator

### 🔹 Serveurs et middlewares

* **express-openapi-validator (Node.js)** : Middleware qui valide les routes et les schémas
* **Connexion (Python)** : Crée une API Flask ou FastAPI à partir d’un fichier OpenAPI
* **FastAPI (Python)** : Génère automatiquement une documentation OpenAPI

### 🔹 Tests

* **Dredd** : Teste si une API réelle correspond à sa description OpenAPI
* **Postman** : Import/export de specs OpenAPI pour créer des collections de tests

---

## 📌 Exemple concret d’utilisation

### Projet en microservices

1. Chaque microservice possède un fichier `openapi.yaml`
2. Un portail central (ex. avec Swagger UI) permet de visualiser toute l’architecture
3. Les équipes front-end génèrent les SDK client en TypeScript
4. Les tests CI/CD valident les APIs à l’aide de Dredd

---

