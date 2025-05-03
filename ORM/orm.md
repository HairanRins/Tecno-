Un **ORM** (Object-Relational Mapping) est une technique qui permet de transformer les données entre des systèmes incompatibles, en l'occurrence entre des bases de données relationnelles (SQL) et des objets dans les langages de programmation orientés objets (comme Java, Python, JavaScript, etc.). L'ORM permet aux développeurs de travailler avec des objets dans leur code au lieu de manipuler directement des requêtes SQL, ce qui simplifie la gestion des bases de données.

# ORM

### Comment ça fonctionne ?

Un ORM crée une correspondance entre les tables d'une base de données et les classes de ton programme. Chaque ligne de la table devient une instance d'un objet dans le code. Par exemple, une table `Users` pourrait être mappée à une classe `User`, où chaque colonne de la table correspond à un attribut de l'objet.

### Exemple concret en JavaScript (avec Sequelize pour Node.js)

**Table SQL:**

```sql
CREATE TABLE Users (
  id INT PRIMARY KEY,
  name VARCHAR(100),
  email VARCHAR(100)
);
```

**Classe ORM avec Sequelize:**

```javascript
const { Sequelize, DataTypes } = require('sequelize');
const sequelize = new Sequelize('sqlite::memory:');

const User = sequelize.define('User', {
  id: {
    type: DataTypes.INTEGER,
    primaryKey: true,
    autoIncrement: true
  },
  name: {
    type: DataTypes.STRING,
    allowNull: false
  },
  email: {
    type: DataTypes.STRING,
    allowNull: false
  }
});

(async () => {
  await sequelize.sync();  // Crée la table dans la base de données
  const user = await User.create({ name: 'Alice', email: 'alice@example.com' });
  console.log(user.id);  // Affiche l'id de l'utilisateur créé
})();
```

### Avantages de l'ORM

1. **Abstraction des requêtes SQL** : L'ORM permet de manipuler les données via des objets plutôt que d'écrire des requêtes SQL manuelles. Cela rend le code plus propre, plus lisible et moins sujet aux erreurs SQL.

2. **Portabilité** : L'ORM facilite le passage d'une base de données à une autre (par exemple, de MySQL à PostgreSQL) sans avoir à réécrire toutes les requêtes SQL.

3. **Gain de temps** : Les ORM offrent souvent des fonctions pour effectuer des opérations courantes comme la gestion des relations entre les tables (relations 1-1, 1-N, N-M), la pagination, les jointures, etc.

4. **Sécurité** : L'ORM aide à prévenir les attaques par injection SQL en échappant automatiquement les entrées utilisateur.

### Inconvénients de l'ORM

1. **Performance** : L'abstraction peut parfois entraîner une surcharge. Par exemple, dans des applications nécessitant des requêtes SQL très complexes ou spécifiques, l'ORM peut générer des requêtes inefficaces.

2. **Courbe d'apprentissage** : Bien que l'ORM simplifie les opérations, il peut introduire une abstraction supplémentaire, ce qui complique la gestion d'une base de données pour les développeurs qui ne connaissent pas les détails des ORM.

3. **Moins de contrôle** : Avec un ORM, le développeur a moins de contrôle sur la manière dont les requêtes sont générées. Cela peut poser problème pour des optimisations spécifiques ou des requêtes très complexes.

### Comparaison avec l'accès direct aux bases de données (SQL brut)

#### 1. **Gestion des Relations**

* **ORM** : Les ORM gèrent très bien les relations entre les entités. Par exemple, dans une relation `1-N` entre `Users` et `Orders`, l'ORM va automatiquement gérer les jointures et la récupération des données.

  ```javascript
  User.hasMany(Order);
  Order.belongsTo(User);
  ```

  Ensuite, tu peux facilement récupérer toutes les commandes d'un utilisateur :

  ```javascript
  const userWithOrders = await User.findByPk(1, { include: Order });
  ```

* **SQL brut** : Si tu devais gérer cette même relation avec du SQL brut, il te faudrait écrire une requête `JOIN` pour lier les tables.

  ```sql
  SELECT * FROM Users
  JOIN Orders ON Users.id = Orders.user_id
  WHERE Users.id = 1;
  ```

#### 2. **Performance**

* **ORM** : Les ORM peuvent parfois générer des requêtes moins optimisées. Par exemple, si tu récupères un grand nombre d'enregistrements avec des relations, cela pourrait entraîner des requêtes inutiles.

* **SQL brut** : Avec SQL brut, tu as un contrôle total sur la performance, et tu peux écrire des requêtes complexes optimisées, notamment en utilisant des indices ou des requêtes paginées.

#### 3. **Facilité de maintenance**

* **ORM** : Le code est généralement plus facile à maintenir grâce à son abstraction et à sa lisibilité. Par exemple, si tu veux changer la structure d'une table, tu n'as pas à parcourir tout ton code pour trouver toutes les requêtes SQL.

* **SQL brut** : Tu dois maintenir manuellement chaque requête SQL dans le code, ce qui peut devenir lourd à long terme, surtout si la structure de la base de données change fréquemment.

### Cas d'usage typiques des ORM

1. **Applications CRUD** : Pour des applications avec des opérations simples de création, lecture, mise à jour et suppression (comme une application de gestion des utilisateurs), un ORM est une excellente solution car il réduit considérablement la quantité de code nécessaire.

2. **Applications avec des modèles de données bien définis** : Les ORM sont adaptés aux applications où les modèles de données sont relativement statiques et bien définis, comme des systèmes de gestion de contenu (CMS), des boutiques en ligne, des applications de gestion d'inventaire, etc.

3. **Projets de prototypage rapide** : Lors de la création d'un prototype ou d'une application avec des fonctionnalités de base, un ORM permet de se concentrer rapidement sur la logique métier sans se soucier trop des détails de la base de données.

### Conclusion

Les ORM offrent une abstraction qui simplifie le travail avec les bases de données, surtout pour les applications avec des besoins relativement simples. Cependant, si ton projet nécessite des requêtes très optimisées ou complexes, ou si tu as un besoin de performance extrême, utiliser SQL brut ou un mixte des deux (SQL et ORM) pourrait être plus approprié.

