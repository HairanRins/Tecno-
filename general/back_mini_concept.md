# Mini Backend concept

Voici une liste des **petits (mais importants) concepts** en développement **backend**, utiles pour bien structurer et maintenir ton application :

---

### ⚙️ 1. **Architecture**
- **MVC (Model-View-Controller)** ou **Clean Architecture**
- **Layered architecture** : controller → service → repository
- **Microservices vs Monolithes**

---

### 🔐 2. **Sécurité**
- **Authentification** : JWT, OAuth2, Sessions
- **Autorisation** : Rôles, permissions
- **Validation des données** : éviter l’injection SQL, XSS
- **Hashing des mots de passe** : Bcrypt, Argon2

---

### 🧱 3. **APIs**
- **REST** : conventions HTTP, stateless, ressources
- **GraphQL** : requêtes dynamiques
- **WebSockets** : pour du temps réel
- **API versioning** : pour ne pas casser les clients

---

### 🧮 4. **Base de données**
- **SQL vs NoSQL** : PostgreSQL, MySQL vs MongoDB, Redis
- **ORM / ODM** : Sequelize, TypeORM, Prisma, Mongoose
- **Transactions** : ACID
- **Indexation** : pour les performances

---

### 🧰 5. **Outils et pratiques**
- **Logging** : Winston, Pino
- **Monitoring** : Prometheus, Grafana
- **Tests** : Unitaires (Jest), d’intégration, e2e
- **CI/CD** : GitHub Actions, GitLab CI

---

### 🚀 6. **Performance**
- **Caching** : Redis, en-têtes HTTP
- **Pagination** : éviter de charger tout en mémoire
- **Load balancing** : répartir les requêtes
- **Throttling / Rate limiting** : éviter les abus

---

### 📦 7. **Gestion des erreurs**
- **Middleware d’erreurs** : centraliser le traitement
- **Codes HTTP** : bien les utiliser (200, 400, 401, 403, 500...)
- **Try / catch** + logs utiles

---

### 🧩 8. **Middleware**
- Fonctions intermédiaires pour logger, parser, authentifier...
- Ex : `express.json()`, `cors()`, `helmet()`

---

### 📁 9. **Gestion des fichiers**
- Upload (Multer), lecture (fs), stockage local ou cloud (S3)
- Sécurité des fichiers uploadés (vérif MIME type, taille...)

---

### 🛠 10. **DevOps / Déploiement**
- Docker, Docker Compose
- Environnements (dev, staging, prod)
- Variables d’environnement (`dotenv`)

---
