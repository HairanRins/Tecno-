# PUT ou PATCH ? 

---

### 🔁 **PUT**
#### 🧠 Définition :
`PUT` remplace **entièrement** la ressource ciblée par la nouvelle version envoyée.

#### ✅ Avantages :
- **Clarté** : tu sais que tu remplaces toute la ressource.
- **Prévisibilité** : pas de confusion sur ce qui est modifié ou pas.
- **Idempotent** : faire plusieurs fois le même `PUT` ne change pas le résultat.

#### ❌ Inconvénients :
- **Moins efficace** si tu veux juste modifier un ou deux champs, car tu dois envoyer **toute** la ressource.
- **Risque de perte de données** si tu oublies un champ dans la requête : il est écrasé ou remis à `null`.

---

### 🩹 **PATCH**
#### 🧠 Définition :
`PATCH` applique une **modification partielle** à la ressource. Tu n’envoies que les champs à modifier.

#### ✅ Avantages :
- **Efficace** : tu ne mets à jour que les données nécessaires.
- **Flexible** : très utile pour des interfaces utilisateur avec édition par champ.
- **Moins de risque** de supprimer des champs accidentellement.

#### ❌ Inconvénients :
- **Moins clair** pour certains développeurs (on ne voit pas toujours l’état final).
- **Pas toujours idempotent** si la logique côté serveur est mal gérée.
- **Complexité serveur** : le backend doit gérer des cas de mise à jour partielle (valeurs par défaut, logique métier...).

---

### 👀 Exemple concret :

#### Ressource :
```json
{
  "id": 1,
  "name": "Alice",
  "email": "alice@example.com"
}
```

#### `PUT` :
```json
{
  "id": 1,
  "name": "Bob",
  "email": "bob@example.com"
}
```
👉 Tu dois tout envoyer, même les champs non modifiés.

#### `PATCH` :
```json
{
  "name": "Bob"
}
```
👉 Tu modifies uniquement ce que tu veux.

---

### 🔍 Résumé rapide

| Critère                  | PUT                  | PATCH                   |
|--------------------------|----------------------|--------------------------|
| Type de mise à jour      | Complète             | Partielle                |
| Efficacité (réseau)      | Moins efficace       | Plus efficace            |
| Risque d’écrasement      | Élevé si incomplet   | Faible                   |
| Simplicité de mise en œuvre | Simple             | Plus complexe côté backend |
| Idempotence              | Oui                  | Oui (mais peut varier)   |

---

👉 **En pratique** :
- Utilise **`PUT`** quand tu veux **remplacer une ressource entièrement**.
- Utilise **`PATCH`** quand tu veux **faire une modification partielle**, surtout si tu fais des updates fréquents de petits champs.
