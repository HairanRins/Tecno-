# Regex

Une explication claire de **regex** (ou **expressions régulières**) et des **concepts associés**, avec des **exemples** concrets pour bien comprendre.

---

## 🔍 C’est quoi une Regex ?

**Regex** (abréviation de *Regular Expression*, ou *expression régulière* en français) est une **chaîne de caractères spéciale** qui permet de **rechercher**, **valider**, ou **extraire** des motifs (*patterns*) dans du texte.

### 📌 À quoi ça sert ?
- Rechercher une séquence dans un texte (ex : une adresse email, un numéro de téléphone)
- Valider une entrée utilisateur (ex : mot de passe, email)
- Remplacer des parties d’un texte (ex : corriger une faute dans un document)
- Extraire des données (ex : extraire tous les hashtags d’un tweet)

---

## 🧱 Les Concepts de base

### 1. **Caractères normaux**
Ils sont interprétés littéralement.

```regex
chat
```
Cela cherche simplement le mot **"chat"**.

---

### 2. **Caractères spéciaux / Métacaractères**

| Métacaractère | Signification | Exemple |
|---------------|---------------|---------|
| `.`           | N'importe quel caractère sauf nouvelle ligne | `c.t` → correspond à `cat`, `cot`, `cut` |
| `^`           | Début de ligne | `^Hello` → trouve les lignes commençant par "Hello" |
| `$`           | Fin de ligne | `end$` → trouve les lignes qui se terminent par "end" |
| `*`           | 0 ou plusieurs répétitions | `a*` → "", "a", "aa", "aaa" |
| `+`           | 1 ou plusieurs répétitions | `a+` → "a", "aa", mais pas "" |
| `?`           | 0 ou 1 fois | `colou?r` → "color" ou "colour" |
| `[]`          | Classe de caractères | `[aeiou]` → une voyelle |
| `[^]`         | Négation d’une classe | `[^0-9]` → tout sauf un chiffre |
| `{n}`         | Exactement n répétitions | `a{3}` → "aaa" |
| `{n,}`        | Au moins n fois | `a{2,}` → "aa", "aaa", etc. |
| `{n,m}`       | Entre n et m fois | `a{2,4}` → "aa", "aaa", "aaaa" |
| `|`           | OU logique | `chat|chien` → "chat" ou "chien" |
| `()`          | Regroupement | `(ab)+` → "ab", "abab", etc. |

---

### 3. **Classes de caractères pré-définies**

| Classe | Signification | Exemple |
|--------|---------------|---------|
| `\d`   | Chiffre (0-9) | `\d+` → "123", "42" |
| `\D`   | Non-chiffre   | `\D+` → "abc", "$%" |
| `\w`   | Lettre, chiffre, ou `_` | `\w+` → "word_123" |
| `\W`   | Tout sauf `\w` | `\W+` → " !?" |
| `\s`   | Espace blanc (espace, tabulation, saut de ligne) | `\s+` |
| `\S`   | Tout sauf un espace | `\S+` |

---

## 🧪 Exemples pratiques

### ✅ 1. Vérifier une adresse email
```regex
^[\w.-]+@[\w.-]+\.\w{2,}$
```
- `^` → début
- `[\w.-]+` → lettres, chiffres, `.` ou `-`
- `@` → le symbole arrobase
- `[\w.-]+` → nom de domaine
- `\.` → point
- `\w{2,}` → extension (au moins 2 lettres)
- `$` → fin

➡️ Correspond à : `contact@mail.com`, `john.doe@exemple.fr`

---

### ✅ 2. Trouver tous les hashtags dans une phrase
```regex
#\w+
```
➡️ Trouve : `#regex`, `#coding`, `#ChatGPT`

---

### ✅ 3. Valider un mot de passe fort
Exemple : Au moins 8 caractères, avec au moins une majuscule, une minuscule, un chiffre et un caractère spécial

```regex
^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$
```

---

## ⚠️ Astuces
- Utilise des sites comme [regex101.com](https://regex101.com) pour tester tes expressions régulières.
- Attention au langage utilisé (Python, JavaScript, etc.) car certains détails peuvent varier.

---
