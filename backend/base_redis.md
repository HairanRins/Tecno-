# Redis

Un aperçu clair et structuré des **fondamentaux de Redis**, avec des **exemples concrets** et des **explications simples**.

---

## 🧠 Qu'est-ce que Redis ?

**Redis (REmote DIctionary Server)** est une **base de données NoSQL** en mémoire, souvent utilisée comme :

* Cache (rapide et temporaire)
* Message broker (ex. : pub/sub)
* Base de données clé-valeur persistante

> Redis est **extrêmement rapide** car il garde les données en mémoire (RAM), avec possibilité de persistance sur disque.

---

## 🧱 Fondamentaux de Redis

### 1. 🔑 Stockage clé-valeur (Key-Value Store)

Redis fonctionne comme un **dictionnaire géant** : on stocke des données sous forme de **clé : valeur**.

#### Exemple :

```bash
SET nom "Alice"
GET nom
```

**Résultat :** `"Alice"`

---

### 2. 🧾 Types de données de base

Redis supporte plusieurs **types de données** :

---

#### 2.1. **String** (chaîne de caractères)

```bash
SET compteur 10
INCR compteur   # incrémente de 1 → 11
DECR compteur   # décrémente de 1 → 10
```

---

#### 2.2. **Listes** (ordonnées, avec doublons)

```bash
LPUSH ma_liste "tâche1"
RPUSH ma_liste "tâche2"
LRANGE ma_liste 0 -1   # → ["tâche1", "tâche2"]
```

* `LPUSH` : ajoute à gauche
* `RPUSH` : ajoute à droite
* `LRANGE` : lit la liste

---

#### 2.3. **Sets** (ensembles non ordonnés, sans doublons)

```bash
SADD mes_tags "urgent"
SADD mes_tags "travail"
SMEMBERS mes_tags  # → {"urgent", "travail"}
```

---

#### 2.4. **Sorted Sets** (ensembles triés avec score)

```bash
ZADD classement 100 "Alice"
ZADD classement 200 "Bob"
ZRANGE classement 0 -1 WITHSCORES  # → [("Alice", 100), ("Bob", 200)]
```

---

#### 2.5. **Hash** (comme un objet/dictionnaire)

```bash
HSET utilisateur:1 nom "Alice" age 30
HGET utilisateur:1 nom    # → "Alice"
HGETALL utilisateur:1     # → {nom: "Alice", age: "30"}
```

---

### 3. 🕑 Expiration des clés (TTL)

Utile pour le caching.

```bash
SET session_token "abc123" EX 60
TTL session_token  # → 60, puis diminue
```

> `EX` définit une expiration en secondes.

---

### 4. 🔄 Pub/Sub (système de messages)

Un canal de communication entre émetteurs et abonnés.

#### Terminal 1 (abonné) :

```bash
SUBSCRIBE actu
```

#### Terminal 2 (éditeur) :

```bash
PUBLISH actu "Nouveautés Redis 7.0"
```

---

### 5. 🧰 Transactions (MULTI/EXEC)

```bash
MULTI
SET solde 100
DECR solde
EXEC
```

> Toutes les commandes entre `MULTI` et `EXEC` sont exécutées **en bloc**.

---

### 6. 💾 Persistance

Deux modes :

* **RDB (snapshot)** : copie périodique de la DB
* **AOF (Append Only File)** : journalisation des commandes

---

### 7. 🛠️ Commandes utiles

| Commande     | Description                               |
| ------------ | ----------------------------------------- |
| `KEYS *`     | Liste toutes les clés (attention en prod) |
| `DEL clé`    | Supprime une clé                          |
| `EXISTS clé` | Vérifie l'existence                       |
| `FLUSHDB`    | Vide la base courante                     |
| `FLUSHALL`   | Vide toutes les bases                     |

---

## ⚙️ Exemple d'application : compteur de vues

```bash
INCR page:vues
GET page:vues
```

Résultat :

```
1 → 2 → 3 ...
```

---

## 🚀 Installation rapide (Linux)

```bash
sudo apt update
sudo apt install redis-server
redis-cli       # pour lancer le client
```

---

## 📚 Cas d'usage fréquents

* **Caching** de requêtes lentes
* **Sessions utilisateurs**
* **Rate limiting** (limitation d’usage API)
* **File d’attente** (via `LIST`)
* **Classements temps réel** (via `ZSET`)
* **Chat en temps réel** (via `PUB/SUB`)

---
