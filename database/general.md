## Résumé usage des bases de données


Le marché des bases de données est très diversifié, mêlant systèmes relationnels traditionnels (Oracle, MySQL, SQL Server, PostgreSQL) et solutions NoSQL (MongoDB, Redis, Cassandra, DynamoDB, Neo4j, Elasticsearch, Snowflake). Les systèmes relationnels restent dominants pour les applications transactionnelles et la cohérence forte, tandis que les NoSQL s’imposent pour la flexibilité de schéma, la scalabilité horizontale et les cas d’usage en temps réel ou analytiques. Les exemples suivants illustrent la structuration et l’écriture de schémas ou requêtes typiques pour chaque catégorie, facilitant le choix en fonction du contexte projet.

---

## 1. Classement des SGBD les plus populaires (Mai 2025)

### 1.1 Top 5 des systèmes relationnels

1. **Oracle** (Score 1226.57) – leader du classement DB-Engines, prisé pour les environnements critiques, la haute disponibilité et l’intégration cloud ([DB-Engines][1]).
2. **MySQL** (964.98) – largement utilisé dans les architectures LAMP pour les sites web et applications open-source ([DB-Engines][1]).
3. **Microsoft SQL Server** (774.89) – privilégié dans l’écosystème .NET, forte intégration BI et outils Microsoft ([DB-Engines][1]).
4. **PostgreSQL** (674.32) – base open-source très complète (JSONB, extensions, conformité SQL) en forte croissance (+28.77 points sur un an) ([DB-Engines][1], [Stack Overflow][2]).
5. **SQLite** (117.77) – base embarquée, légère, idéale pour mobile ou applications desktop sans serveur dédié ([DB-Engines][1]).

### 1.2 Top 5 des solutions NoSQL

1. **MongoDB** (402.51) – document-store pour données semi-structurées, forte adoption dans les applications web modernes ([DB-Engines][1]).
2. **Redis** (152.19) – store clé-valeur en mémoire, utilisé pour cache, sessions et files d’attente ([DB-Engines][1]).
3. **Cassandra** (108.05) – wide column store pour haut débit d’écriture et distribution géographique ([DB-Engines][1]).
4. **Amazon DynamoDB** (79.30) – service NoSQL managé d’AWS, scalabilité automatique et faible latence ([DB-Engines][1]).
5. **Neo4j** (47.91) – base de graphes pour naviguer et analyser des relations complexes (réseaux sociaux, recommandations) ([DB-Engines][1]).

### 1.3 Solutions analytiques et data-warehousing

* **Snowflake** (172.01) – entre dans le top 6, spécialisé cloud data-warehousing, forte montée ces derniers mois ([DB-Engines][3]).
* **Google BigQuery** (62.88) et **Azure Synapse** (14.22) – entrepôts analytiques managés, SQL on-demand, intégration ML ([DB-Engines][1]).

---

## 2. Comparaisons et cas d’usage

| Catégorie            | Avantages clés                                           | Cas d’usage typiques                                  |
| -------------------- | -------------------------------------------------------- | ----------------------------------------------------- |
| **Relationnel**      | ACID, joints complexes, transactions                     | Systèmes bancaires, ERP, CRM, e-commerce              |
| **Document-store**   | Schéma flexible, JSON, montée en charge rapide           | Applications web, gestion de contenu, IoT             |
| **Clé-valeur**       | Latence ultra-faible, simplicité                         | Cache, sessions, compteur en temps réel               |
| **Wide column**      | Écriture massive, répartition géographique               | Logs massifs, réseaux sociaux, messagerie             |
| **Graphes**          | Traversées de relations, algorithmes de graphes          | Recommandation, détection de fraudes, réseaux sociaux |
| **Data-warehousing** | Scalabilité cloud, requêtes analytiques à grande échelle | BI, rapports décisionnels, machine learning           |

---

## 3. Exemples de structuration et d’écriture

### 3.1 SQL relationnel (PostgreSQL)

```sql
-- Création d'une table utilisateur
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(100) NOT NULL,
    profile JSONB,            -- stockage flexible
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Requête de sélection avec jointure
SELECT u.username, o.order_id, o.total
FROM users u
JOIN orders o ON u.id = o.user_id
WHERE o.created_at > NOW() - INTERVAL '30 days';
```

*PostgreSQL offre JSONB pour le semi-structuré tout en conservant la puissance SQL ([Stack Overflow][2]).*

### 3.2 Document-store (MongoDB)

```javascript
// Exemple de document utilisateur
db.users.insertOne({
  username: "alice",
  email: "alice@example.com",
  profile: { age: 30, interests: ["tech","art"] },
  created_at: new Date()
});

// Requête : trouver les utilisateurs aimant "tech"
db.users.find({ "profile.interests": "tech" });
```

*MongoDB est idéal pour les données évolutives et les structures non-uniformes ([GeeksforGeeks][4]).*

### 3.3 Clé-valeur (Redis)

```redis
# Stocker le nombre de visites d'une page
INCR page:home:visits

# Récupérer la valeur
GET page:home:visits
```

*Redis sert de cache de très haute performance pour alléger les bases principales ([DB-Engines][1]).*

### 3.4 Wide column store (Cassandra)

```cql
-- Création d’une table de logs
CREATE TABLE logs (
    service TEXT,
    log_time TIMESTAMP,
    message TEXT,
    PRIMARY KEY (service, log_time)
) WITH CLUSTERING ORDER BY (log_time DESC);

-- Insertion d’un log
INSERT INTO logs (service, log_time, message)
VALUES ('auth', toTimestamp(now()), 'User login succeeded');
```

*Cassandra scale horizontalement pour des volumes massifs d’écritures ([DB-Engines][1]).*

### 3.5 Graph database (Neo4j)

```cypher
// Création de nœuds et relation
CREATE (a:Person {name: 'Alice'}),
       (b:Person {name: 'Bob'}),
       (a)-[:FRIENDS_WITH]->(b);

// Requête : trouver les amis d’Alice
MATCH (a:Person {name: 'Alice'})-[:FRIENDS_WITH]->(friend)
RETURN friend.name;
```

*Neo4j excelle dans l’exploration de graphes pour recommandations ou détection de fraudes ([DB-Engines][1]).*

### 3.6 Data-warehousing SQL (Snowflake)

```sql
-- Création d'une table dans un entrepôt Snowflake
CREATE TABLE sales (
    sale_id INT,
    customer_id INT,
    amount FLOAT,
    sale_date DATE
);

-- Requête analytique
SELECT customer_id, SUM(amount) AS total_spent
FROM sales
WHERE sale_date BETWEEN '2025-01-01' AND '2025-03-31'
GROUP BY customer_id
ORDER BY total_spent DESC
LIMIT 10;
```

*Snowflake combine scalabilité cloud et simplicité pour l’analytique ([DB-Engines][3]).*

---

## 4. Conclusion et choix stratégique

* **Transactionnel et cohérence forte** : optez pour Oracle, PostgreSQL ou SQL Server.
* **Flexibilité schéma** : MongoDB ou Couchbase.
* **Cache/temps réel** : Redis, Memcached.
* **Volume massif et distribution** : Cassandra, DynamoDB.
* **Graphes** : Neo4j.
* **Analytique cloud** : Snowflake, BigQuery, Azure Synapse.

Le choix dépendra du besoin en cohérence, de la nature des données (structurées vs non struct.), du volume, et du modèle de déploiement (on-premise vs cloud managé).

[1]: https://db-engines.com/en/ranking "DB-Engines Ranking - popularity ranking of database management systems"
[2]: https://survey.stackoverflow.co/2024/?utm_source=chatgpt.com "2024 Stack Overflow Developer Survey"
[3]: https://db-engines.com/en/blog_post/110 "DB-Engines shares Q1 2025 database industry rankings and top climbers: Snowflake and PostgreSQL trending"
[4]: https://www.geeksforgeeks.org/top-databases-to-learn/?ref=asr7&utm_source=chatgpt.com "Top 7 Databases to Learn in 2025 | GeeksforGeeks"
