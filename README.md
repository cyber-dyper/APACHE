# 🌐 **APACHE - Déploiement d'un Serveur Web Sécurisé** 🛠️

## 🎉 **Bienvenue sur ton premier projet Web !** 🚀

Dans ce projet, tu vas apprendre à monter un serveur **Apache** avec une **double interface réseau** pour créer un environnement **web sécurisé** et **optimisé**. 

---

## 🎯 **SCÉNARIO : Déploiement d'un Site Web Apache**

🛠️ **Objectif :**  
Mettre en place un **site web Apache** avec deux **interfaces réseau** : interne (intranet) et externe (extranet).

📂 **Ressources fournies :**  
Tu trouveras dans ce dépôt les fichiers des **deux virtual hosts (vhosts)** qui simulent l'arborescence des sources sur le serveur.

🔗 **Liens utiles :**  
- [Lien vers les fichiers VHost 1](#)  
- [Lien vers les fichiers VHost 2](#)  

---

## 🌐 **CONFIGURATION DU PROJET**

### 📡 **Réseau :**  
- **Intranet :** `192.168.100.0/24`  
- **Extranet :** `10.0.40.0/16`  

### 💻 **Système :**  
- Utilise une **distribution Debian minimale** (sans environnement de bureau) dédiée à un projet **serveur**.

---

## 🌍 **Service Web : Apache HTTPD**

1. **Installation du serveur Apache :**  
   - Utilise `apt install apache2` pour installer le serveur web.

2. **Création des Virtual Hosts :**  
   - 🟢 **Extranet :** `extranet.cyberdyper.com` (Public)  
   - 🔒 **Admin :** `admin.cyberdyper.com` (Privé)

3. **Arborescence des répertoires :**  
   - `/var/www/extranet.cyberdyper.com`  
   - `/var/www/admin.cyberdyper.com`  

4. **Configuration des ports d'écoute :**  
   - **Admin en HTTP :** `5501`  
   - **Admin en HTTPS :** `5502`  

5. **Sécurité HTTPS :**  
   - 🔑 **Générer un certificat auto-signé wildcard** pour les deux vhosts.  
   - 🔐 **Forcer le passage en HTTPS** pour toutes les requêtes entrantes HTTP.

6. **Gestion des logs :**  
   - 📄 Crée deux **fichiers de logs d'accès**, un pour chaque vhost.  
   - ⚠️ Utilise un **fichier commun** pour les erreurs.

---

## 📁 **Service FTP : Accès aux Fichiers**

1. **Accès sécurisé :**  
   - Les développeurs ont accès aux **codes sources** des deux vhosts.  
   - Les graphistes accèdent uniquement aux **images** des deux vhosts.  
   - ❌ **Refuser les connexions anonymes.**

2. **Gestion des utilisateurs et permissions :**  
   - 👨‍💻 Crée des **groupes Linux** pour gérer les droits d'accès.  
   - 👤 **Utilisateurs de test :** Un **développeur** et un **graphiste**.

3. **Cloisonnement du service FTP :**  
   - 🔒 Mets en place un **chroot** ou un **jail** pour sécuriser l'accès.  
   - 🛡️ **Accès FTP uniquement sur l'interface privée.**

---

## 🔥 **Filtrage & Sécurité : Netfilter & Fail2Ban**

1. **Configuration de Netfilter :**  
   - ⚙️ Autorise uniquement les **protocoles nécessaires** (HTTP, HTTPS, FTP privé).

2. **Protection Anti-DDoS :**  
   - Utilise des **modules de sécurité** contre les attaques **DDoS** et les **slow connections**.

3. **Fail2Ban : Sécuriser les accès**  
   - 🚫 Bloque **3 tentatives de connexion FTP échouées** d'affilée.  
   - 🚦 Limite à **3 requêtes malveillantes** sur un fichier de l'arborescence des sites, avec un **temps de bannissement** paramétrable.

---

## 📦 **LIVRABLES : Fichiers de Configuration à Fournir**

1. 🖥️ **Web :** Fichiers de configuration d'Apache (vhosts, SSL, logs).  
2. 📂 **FTP :** Configuration des accès utilisateurs, droits et sécurisation.  
3. 🔥 **Netfilter :** Script de configuration du pare-feu.  
4. 🚫 **Fail2Ban :** Règles et configuration de sécurité.

---

## 🎯 **Objectif final :**  
Créer un environnement web **sécurisé**, **fiable** et **performant**, tout en assurant une **gestion fine des accès** pour les développeurs et les graphistes. 

✨ **Bonne configuration !** 🚀 Si tu as des questions, n'hésite pas à les poser dans les issues du dépôt. 😊
