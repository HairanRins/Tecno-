# Socket et autres 

Un **socket** est un mécanisme de communication utilisé pour permettre l'échange de données entre deux entités (applications) via un réseau. C’est un peu comme une prise de courant : tu branches deux machines ensemble via leurs sockets pour qu’elles puissent discuter.

---

### **1. Qu’est-ce qu’un socket ?**
Un **socket** est une **interface** qui permet à un programme (souvent un serveur ou un client) d’envoyer et de recevoir des données via un réseau, que ce soit **en local** (localhost) ou **à distance** (Internet).

---

### **2. Types de sockets**
- **Socket TCP (Transmission Control Protocol)**  
  Communication fiable, orientée connexion (ex: site web, chat, etc.).
  
- **Socket UDP (User Datagram Protocol)**  
  Communication rapide, non fiable, sans connexion (ex: jeux en ligne, streaming en direct).

---

### **3. Vocabulaire et termes à connaître**

| Terme                     | Description |
|--------------------------|-------------|
| **Client**               | L’application qui initie la connexion (par exemple : un navigateur). |
| **Serveur**              | L’application qui attend les connexions entrantes. |
| **Port**                 | Un numéro (ex : 80 pour HTTP, 443 pour HTTPS) utilisé pour identifier un service spécifique sur une machine. |
| **Adresse IP**           | Adresse du périphérique sur le réseau. |
| **Bind**                 | Associer un socket à une IP et un port. |
| **Listen**               | Indiquer que le serveur attend des connexions entrantes. |
| **Accept**               | Accepter une connexion d’un client. |
| **Connect**              | Se connecter à un serveur distant. |
| **Send / Receive**       | Envoyer ou recevoir des données. |
| **Close**                | Fermer la connexion. |

---

### **4. Exemples simples**

#### **Exemple TCP en Python**

**Serveur (TCP):**
```python
import socket

server = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
server.bind(("localhost", 12345))
server.listen()

print("En attente de connexion...")
client_socket, addr = server.accept()
print(f"Connecté à {addr}")
client_socket.send(b"Salut client !")
client_socket.close()
```

**Client (TCP):**
```python
import socket

client = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
client.connect(("localhost", 12345))
message = client.recv(1024)
print("Reçu :", message.decode())
client.close()
```

---

#### **Exemple UDP (sans connexion)**
```python
# Serveur UDP
import socket

server = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
server.bind(("localhost", 12345))
data, addr = server.recvfrom(1024)
print("Reçu de", addr, ":", data.decode())
```

```python
# Client UDP
import socket

client = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
client.sendto(b"Hello serveur UDP", ("localhost", 12345))
```

---

### **5. Autres termes avancés à connaître**
- **WebSocket** : protocole basé sur TCP qui permet une communication bidirectionnelle en temps réel (ex: pour les chats, jeux en ligne).
- **REST API vs Socket** : REST = échanges ponctuels ; Socket = communication continue en temps réel.
- **Socket.IO** : bibliothèque (souvent avec Node.js) pour faciliter les WebSockets.
- **Latency / Ping** : temps que met une donnée à voyager entre client et serveur.
- **Timeout** : délai au-delà duquel une opération réseau échoue.

---
