# APACHE
## Bienvenue sur ton premier projet Web !
### SCENARIO
Monter un site web Apache avec deux pattes réseaux : interne et externe.

À ta disposition, les fichiers des deux vhosts qui simulent l’arborescence des sources sur le serveur.

Liens 1
Liens 2

## CONFIGURATION
### Réseau :
Intranet sur le 192.168.100.0/24.
Extranet en 10.0.40.0/16, par exemple.

### Système :
Une distribution Debian en version minimale (pas d’environnement de bureau) pour projet serveur.

### Service Web :
Installation du serveur HTTPD d'Apache dans lequel tu créeras deux virtual hosts :
- extranet.cyberdyper.com ;
- admin.cyberdyper.com.

Les deux vhosts doivent avoir leur fichier source nommé différemment. Crée donc deux répertoires :
- /var/www/extranet.cyberdyper.com et ;
- admin.cyberdyper.com par exemple.

Le vhost extranet est publique, le vhost admin privée.
Le port d’écoute pour le vhost admin est en 5501 pour le HTTP et 5502 pour le HTTPS, par exemple.

Génère un certificat auto-signé wildcard pour les deux vhosts.
Les requêtes entrantes HTTP sont à forcée vers HTTPS pour les deux vhosts.
Crée deux fichiers de traces d’accès, un pour chaque vhost, et le même pour les erreurs. 

### Service FTP :
Les développeurs vont avoir besoin d’accéder aux répertoires des codes sources des deux vhosts.
Les graphistes doivent uniquement accéder aux répertoires des images des deux vhosts.
Il faut également refuser les connexions anonymes.

### Recommandations : 
- Créer des groupes Linux pour gérer ces droits et inventer deux comptes nominatifs de test : un pour un développeur et un pour un graphiste.
- Mise en place d’un cloisonnement via un chroot ou un jail sur ce service, pour bien le sécuriser.
- Le service FTP doit être uniquement accessible sur la patte privée.

### Filtrage :
Utilise netfilter pour ne laisser passer que le minimum de protocoles nécessaires.
Utiliser des modules contre les attaques DDoS ou slow connections.
Utilise Fail2Ban dans netfilter pour bloquer 35 mauvaises tentatives de connexion FTP d’affilée. 
Idem pour 3 requêtes sur un fichier de l’arborescence des sites (avec temps de ban en minutes).

## LES LIVRABLES
### Rassembler les fichiers de configuration des services;
1. Web
2. FTP
3. Netfilter
4. Fail2Ban

