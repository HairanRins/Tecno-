Le **Clean Code** est une approche qui vise à rendre le code plus lisible, maintenable et évolutif. En **JavaScript** et **TypeScript**, ainsi que dans leurs frameworks (comme React, Angular, NestJS, etc.), plusieurs principes peuvent être appliqués :

---

### **1. Nommer clairement les variables et fonctions**
✔ **Utiliser des noms explicites et significatifs**  
❌ Mauvais :  
```ts
function d(x, y) { return x * y; }
```
✔ Bon :  
```ts
function calculateArea(width: number, height: number): number {
  return width * height;
}
```

---

### **2. Découper en petites fonctions (Single Responsibility Principle - SRP)**
✔ **Une fonction doit faire une seule chose et bien la faire**  
❌ Mauvais :  
```ts
function processUserData(user) {
  validateUser(user);
  saveToDatabase(user);
  sendEmail(user);
}
```
✔ Bon :  
```ts
function validateUser(user) { /* validation logic */ }
function saveToDatabase(user) { /* save logic */ }
function sendEmail(user) { /* email logic */ }
```

---

### **3. Éviter les effets de bord et privilégier l’immutabilité**
✔ **Utiliser des fonctions pures et éviter de modifier les objets existants**  
❌ Mauvais : (mutation de l’objet original)  
```ts
function updateUser(user) {
  user.active = true;
  return user;
}
```
✔ Bon : (création d’un nouvel objet)  
```ts
function activateUser(user) {
  return { ...user, active: true };
}
```

---

### **4. Utiliser des types explicites en TypeScript**
✔ **Privilégier des types clairs pour éviter les erreurs**  
❌ Mauvais :  
```ts
function getFullName(user) {
  return user.first + " " + user.last;
}
```
✔ Bon :  
```ts
interface User {
  firstName: string;
  lastName: string;
}

function getFullName(user: User): string {
  return `${user.firstName} ${user.lastName}`;
}
```

---

### **5. Éviter le code dupliqué (DRY - Don't Repeat Yourself)**
✔ **Factoriser le code répétitif dans des fonctions ou des utilitaires**  
❌ Mauvais :  
```ts
const user1 = { name: "Alice", role: "admin" };
const user2 = { name: "Bob", role: "user" };

if (user1.role === "admin") { console.log("Accès autorisé"); }
if (user2.role === "admin") { console.log("Accès autorisé"); }
```
✔ Bon :  
```ts
function isAdmin(user) {
  return user.role === "admin";
}

if (isAdmin(user1)) console.log("Accès autorisé");
if (isAdmin(user2)) console.log("Accès autorisé");
```

---

### **6. Gérer les erreurs proprement**
✔ **Ne jamais ignorer les erreurs et utiliser `try/catch` ou des validations**  
❌ Mauvais :  
```ts
function getUser(id) {
  return database.findUser(id); // Erreur possible non gérée
}
```
✔ Bon :  
```ts
function getUser(id) {
  try {
    return database.findUser(id);
  } catch (error) {
    console.error("Erreur lors de la récupération de l’utilisateur :", error);
    return null;
  }
}
```

---

### **7. Respecter le principe Open/Closed (OCP)**
✔ **Le code doit être ouvert à l’extension mais fermé aux modifications**  
❌ Mauvais :  
```ts
function calculatePrice(product) {
  if (product.type === "food") return product.price * 0.9;
  if (product.type === "clothing") return product.price * 0.8;
}
```
✔ Bon :  
```ts
interface DiscountStrategy {
  calculate(price: number): number;
}

class FoodDiscount implements DiscountStrategy {
  calculate(price: number): number {
    return price * 0.9;
  }
}

class ClothingDiscount implements DiscountStrategy {
  calculate(price: number): number {
    return price * 0.8;
  }
}
```

---

### **8. Suivre une structure de projet cohérente (surtout en NestJS, Angular)**
✔ **Organiser le code en modules, services, contrôleurs**  
Exemple en **NestJS** :  
```
/src
  /users
    users.module.ts
    users.controller.ts
    users.service.ts
    users.repository.ts
```
Cela facilite la séparation des responsabilités et la maintenabilité.

---

### **9. Utiliser des outils pour automatiser le clean code**
✔ **Mettre en place des outils comme :**  
- **ESLint** (vérification de la qualité du code)  
- **Prettier** (formatage automatique)  
- **Jest** (tests unitaires)  

Exemple de configuration **ESLint + Prettier** en **TypeScript** :
```json
{
  "extends": ["eslint:recommended", "plugin:@typescript-eslint/recommended", "prettier"],
  "rules": {
    "no-console": "warn",
    "eqeqeq": "error"
  }
}
```

---

### **10. Tester son code**
✔ **Écrire des tests unitaires et d’intégration**  
Exemple avec **Jest** en **NestJS** :  
```ts
describe('UserService', () => {
  let service: UserService;

  beforeEach(() => {
    service = new UserService();
  });

  it('should create a user', () => {
    const user = service.createUser('Alice');
    expect(user.name).toBe('Alice');
  });
});
```

---

## 🚀 **Conclusion**
En appliquant ces principes de **Clean Code**, ton code en **JS/TS** sera plus :
✅ **Lisible**  
✅ **Facile à maintenir**  
✅ **Performant**  
✅ **Évolutif**  

Si tu bosses sur un projet précis, dis-moi, et je peux t'aider à appliquer ces principes sur ton code ! 😊
