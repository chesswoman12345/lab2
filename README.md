# Lab 2 : Rooting
## Étape 1 : Rooter l'AVD

![](https://github.com/user-attachments/assets/7f8ee7c1-8e73-48c7-a433-2c39ba3043bb)

![](https://github.com/user-attachments/assets/c85c3f25-7c89-4643-9ebf-9e4c91e10177)

![](https://github.com/user-attachments/assets/8bbd1d24-c69e-4bce-8239-5063b282c957)

## Étape 2 : Fiche périmètre (5 lignes)

* **Application & Version :** Vida 1.0 (Beta)
* **Support de test :** AVD (Android Virtual Device) / Device labo
* **Objectif technique :** Comprendre le fonctionnement du rooting et évaluer ses impacts sécuritaires.
* **Nature des données & Réseau :** Utilisation exclusive de données fictives sur un réseau de test isolé.
* **Importance stratégique :** Ce document fait office de contrat définissant les limites de l'audit pour protéger le testeur et le propriétaire, garantissant ainsi la fiabilité et la conformité de l'analyse.

## Étape 3 : Démarrer un AVD propre
hmmmmmmm

## Étape 4 : Installer et lancer l'app de test
![](https://github.com/user-attachments/assets/0587e99e-3d02-4064-94bf-fe83c05f3824)
6
Étape 5 : Définir 3 scénarios simples

## Étape 6 : Lire Android Security (6 lignes max)

Le programme de sécurité d'Android repose sur une architecture multicouche alliant protection des données et ouverture aux développeurs. Cette stratégie s'appuie sur des mécanismes natifs tels que le sandboxing, le chiffrement et le Verified Boot pour garantir l'intégrité du système. La plateforme assure une défense proactive via des bulletins de sécurité réguliers et des standards rigoureux appliqués au matériel comme au réseau. Enfin, des outils de diagnostic avancés permettent de neutraliser les vulnérabilités avant toute exploitation malveillante.

## Étape 7 : Verified Boot (idée générale + check AVD)

![](https://github.com/user-attachments/assets/02d27b25-a7b1-40ff-b26f-f7b10db1b144)



## Étape 9 : Définir le rooting (4 phrases)

Le rooting est une action qui compromet les piliers de la sécurité d'Android (le sandboxing, le modèle de permissions et l'intégrité système) en accordant des privilèges totaux sur l'ensemble de la structure logicielle (la "forteresse numérique").

En d'autres termes, il s'agit de s'octroyer des droits d'accès illimités qui permettent de contourner les barrières de protection natives conçues pour isoler les applications et protéger les données sensibles.

## Étape 10 : Intérêt labo (Environnement non opérationnel)

L'utilisation d'un laboratoire non opérationnel (AVD) permet d'isoler les tests de sécurité dans un environnement virtuel étanche, évitant ainsi tout risque de corruption sur un appareil physique personnel. Cette approche offre une flexibilité totale pour manipuler les privilèges root et simuler des attaques complexes sans compromettre de données réelles ou de composants matériels coûteux.

---

## Étape 11 : Matrice de Risques (8 risques)

1. **Élévation de privilèges :** Un attaquant obtient les droits root pour contourner les restrictions logicielles natives.
2. **Exfiltration de données :** Accès non autorisé aux bases de données SQLite ou aux fichiers de préférences partagées.
3. **Capture de flux réseau :** Interception de données sensibles transmises sans chiffrement TLS robuste.
4. **Ingénierie inverse :** Décompilation de l'APK permettant l'analyse du code source et des secrets enfouis.
5. **Modification de l'intégrité :** Altération du binaire de l'application pour injecter un comportement malveillant.
6. **Fuite de logs :** Exposition d'informations sensibles (tokens, identifiants) via les journaux système Logcat.
7. **Contournement de l'authentification :** Manipulation de la mémoire vive pour forcer l'accès à des sessions actives.
8. **Rupture de la chaîne de confiance :** Désactivation du Verified Boot facilitant l'installation de firmwares compromis.

---

## Étape 12 : Mesures Défensives (8 mesures)

1. **Obscurcissement du code :** Utiliser ProGuard ou R8 pour rendre la rétro-ingénierie complexe et illisible.
2. **Détection du Root :** Implémenter des bibliothèques comme RootBeer pour bloquer l'exécution sur les appareils compromis.
3. **Chiffrement au repos :** Chiffrer systématiquement les données locales avec SQLCipher ou l'API Jetpack Security.
4. **Certificate Pinning :** Restreindre les connexions réseau aux seuls serveurs possédant un certificat prédéfini.
5. **Validation des entrées :** Assainir rigoureusement toutes les données entrantes pour prévenir les injections.
6. **Nettoyage des logs :** Désactiver tous les journaux de débogage sensibles avant la mise en production.
7. **Utilisation du TEE :** Stocker les clés cryptographiques dans le Trusted Execution Environment du processeur.
8. **Vérification d'intégrité :** Utiliser l'API Play Integrity pour s'assurer que l'application n'a pas été modifiée.



---

## Étape 13 : OWASP MASVS (2 exigences)

* **MASVS-STORAGE-1 :** L'application doit stocker les données sensibles de manière sécurisée, en utilisant les mécanismes de stockage fournis par le système d'exploitation.
* **MASVS-RESILIENCE-1 :** L'application doit être capable de détecter si elle s'exécute sur un appareil rooté ou dont l'intégrité est compromise.

---

## Étape 14 : OWASP MASTG (2 idées de tests)

* **MSTG-STORAGE-01 :** Examiner le répertoire de données de l'application (`/data/data/com.example.app`) après utilisation pour vérifier la présence de fichiers en clair.
* **MSTG-NETWORK-03 :** Effectuer une interception de trafic via un proxy (Burp Suite) pour vérifier si l'application valide correctement la chaîne de certificats SSL/TLS

## Étape 16 : Fiche Environnement (Traçabilité)

### 📋 Informations Générales
* **Auteur :** RAZAN ZOUIN
* **Date :** 13 Février 2026
* **Support :** Émulateur Android (AVD) "emu64xa"
* **Modèle Émulé :** Pixel 6 (x86_64)
* **Système :** Android 15 (VanillaIceCream) | API Level 35
* **Application :** DIVA (Damn Insecure and Vulnerable App)

---

### 🔍 Synthèse des Observations
* **Accès Privilégié :** Obtention confirmée des droits root (**uid=0**).
* **État d'Intégrité :** Verified Boot en état "**orange**" (indiquant une rupture de la chaîne de confiance).
* **Vulnérabilité Majeure :** Exposition d'identifiants critiques (`Secret123!`) stockés en clair dans les *Shared Preferences*.

---

### 📸 Galerie des Preuves
1.  **Lancement :** Initialisation de l'application (Image 7).
2.  **Privilèges :** Confirmation du mode root via console (Images 2-3).
3.  **Sécurité Système :** Rapport d'état du Verified Boot (Image 13).
4.  **Exfiltration :** Lecture technique des données sensibles (Images 9-10-12).

---

### 🧹 État de Sortie & Limites
* **Périmètre :** Tests restreints à un environnement virtualisé ; absence de protections matérielles de type **TEE** ou **StrongBox**.
* **Nettoyage :** Réinitialisation complète (Wipe Data) de l'AVD effectuée. Aucune donnée fictive ne subsiste sur le support.


## Étape 17 : Remise à zéro AVD (obligatoire fin de séance)
![](https://github.com/user-attachments/assets/3f2b143a-56ab-4dcc-a677-eaafe270e184)

![](https://github.com/user-attachments/assets/e61b4186-895b-4d1b-80c6-02735dede0d7)

Étape 18 : Remise à zéro device labo (si utilisé)
no need
20
Étape 19 : Livrables (1–2 pages)

21
Étape 20 : Checklist finale

22
Ressources supplémentaires pour débutants
Étape 1 : Rooter l'AVD
