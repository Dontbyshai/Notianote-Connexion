# 🪐 NotiaNote Connexion (Universal School Platforms Connector)

[![Website](https://img.shields.io/badge/Website-notianote.fr-8B5CF6?style=for-the-badge)](https://notianote.fr)
[![App Store](https://img.shields.io/badge/App_Store-iOS-007AFF?style=for-the-badge&logo=apple)](https://apps.apple.com/fr/app/notianote/id6758548199)
[![Play Store](https://img.shields.io/badge/Play_Store-Android-3DDC84?style=for-the-badge&logo=googleplay&logoColor=white)](https://play.google.com/store/apps/details?id=com.dontbyshai.notianote)

Bienvenue sur le dépôt officiel **NotiaNote Connexion** ! 

Ce projet héberge la logique de connexion (Drivers) universelle et publique utilisée par l'application **NotiaNote** pour s'interconnecter de manière transparente avec la quasi-totalité des plateformes scolaires et universitaires dans le monde.

---

## 📱 À propos de NotiaNote
**NotiaNote** est l'application mobile de référence pour les élèves et les parents d'élèves. Conçue avec un design moderne, premium et personnalisable, elle réunit au même endroit toutes les informations académiques indispensables :
* 📊 **Suivi des notes** avec statistiques avancées (évolution, moyennes de classe, répartition).
* 📅 **Emploi du temps interactif** dynamique.
* 📝 **Cahier de textes & Devoirs** pour ne jamais rien oublier.
* 💬 **Messagerie intégrée** avec les enseignants et les établissements.
* 🤖 **NotiaNote IA** : Un assistant intelligent pour vous aider dans vos révisions et devoirs.

🌐 **Découvrez notre site web officiel :** [notianote.fr](https://notianote.fr)

---

## 🛠️ Le Connecteur Universel (`NotiaNote-app-publique.js`)
Ce fichier contient la logique de connexion pure, **sans aucune interface graphique**, pour vous connecter à tous les services scolaires mondiaux :

### 🇫🇷 France & Europe Francophone
* **EcoleDirecte** — Authentification sécurisée API v3 avec gestion du Double Facteur (2FA).
* **Pronote** — Chiffrement et intégration avec les serveurs Pronote (France / International).
* **Skolengo & ENT** — Passerelle multi-ENT régionales (Skolengo, CAS, etc.).
* **Smartschool** (Belgique / Pays-Bas) — Session-based authentification et module Skore.

### 🇩🇪 Allemagne / Autriche / Europe Centrale
* **WebUntis** — Intégration via protocole Web Untis JSON-RPC API.

### 🇺🇸 USA & Canada (Amérique du Nord)
* **PowerSchool** — Connexion API REST officielle PowerSchool.
* **Infinite Campus** — Connecteur d'authentification Campus.
* **Edsby** — Gestion de session Edsby.
* **Skyward** — Jeton d'accès API Skyward.

### 🌍 International & Enseignement Supérieur
* **Moodle** — Connexion via l'API officielle mobile Moodle.
* **AppScho** — Intégration pour les Universités françaises et internationales (Sorbonne, SciencesPo, HEC, Sorbonne-Nouvelle, Université de Limoges, etc.).

---

## 🚀 Exemple d'intégration rapide (JavaScript)

```javascript
import NotiaNotePlatformsConnector from './NotiaNote-app-publique.js';

async function main() {
    try {
        // Connexion à EcoleDirecte
        const resultED = await NotiaNotePlatformsConnector.connectToPlatform('ecoledirecte', {
            username: 'mon_identifiant',
            password: 'mon_mot_de_passe'
        });
        console.log('Connexion EcoleDirecte réussie :', resultED.success);

        // Connexion à Smartschool (Belgique)
        const resultSmart = await NotiaNotePlatformsConnector.connectToPlatform('smartschool', {
            username: 'mon_login',
            password: 'mon_password',
            host: 'https://mon-ecole.smartschool.be'
        });
        console.log('Connexion Smartschool réussie :', resultSmart.success);
    } catch (error) {
        console.error('Erreur :', error);
    }
}
```

---

## 📄 Licence
Ce projet est sous licence **MIT**. Vous êtes libre de l'utiliser, de le modifier et de le distribuer, tant pour des projets open-source que commerciaux.

Propulsé par **Shai's Company**.
