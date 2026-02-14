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

Étape 10 : Intérêt labo (non opérationnel)

12
Étape 11 : Matrice de risques (8 risques, 1 phrase chacun)

13
Étape 12 : Mesures défensives (8 mesures, 1 phrase chacune)

14
Étape 13 : OWASP MASVS (2 exigences)

15
Étape 14 : OWASP MASTG (2 idées de tests)

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
