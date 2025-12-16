# Classroom Platform - Plateforme de Classe en Ligne

Plateforme de classe en ligne développée avec Django permettant aux étudiants de soumettre leurs devoirs et aux enseignants de les évaluer et retourner les résultats.

## 📋 Description

Dans l'ère actuelle de l'apprentissage en ligne, il est essentiel d'avoir une plateforme en ligne permettant aux étudiants de soumettre leurs devoirs, aux enseignants de les évaluer et de retourner les résultats. Classroom a été développé pour accomplir cette tâche en offrant une solution complète et intuitive pour la gestion des classes et des devoirs en ligne.

## 🎯 Objectifs du Projet

- **Faciliter la soumission de devoirs** : Interface simple pour les étudiants
- **Simplifier l'évaluation** : Outils pour les enseignants pour évaluer et noter
- **Améliorer la communication** : Échange entre étudiants et enseignants
- **Suivi des résultats** : Visualisation des notes et retours
- **Gestion des classes** : Organisation des cours et des étudiants

## 🚀 Fonctionnalités Principales

### Pour les Étudiants
- ✅ **Soumission de devoirs** : Upload de fichiers et soumission en ligne
- ✅ **Consultation des devoirs** : Voir les devoirs assignés
- ✅ **Suivi des résultats** : Consulter les notes et commentaires
- ✅ **Profil étudiant** : Gestion du profil personnel
- ✅ **Notifications** : Alertes pour les nouveaux devoirs et résultats

### Pour les Enseignants
- ✅ **Création de devoirs** : Assigner des devoirs aux classes
- ✅ **Évaluation** : Noter et commenter les devoirs soumis
- ✅ **Gestion des classes** : Créer et gérer les classes
- ✅ **Suivi des étudiants** : Voir les soumissions et progrès
- ✅ **Retour des résultats** : Envoyer les notes et commentaires

### Fonctionnalités Générales
- ✅ **Authentification** : Système de connexion sécurisé
- ✅ **Gestion des rôles** : Distinction entre étudiants et enseignants
- ✅ **Upload de fichiers** : Gestion des documents et fichiers
- ✅ **Interface moderne** : Design responsive avec Bootstrap

## 🛠️ Technologies Utilisées

### Backend
- **Django** - Framework web Python
- **Python** - Langage de programmation
- **Django ORM** - Gestion de base de données
- **SQLite** - Base de données (développement)
- **PostgreSQL** - Base de données (production, si déployé)

### Frontend
- **HTML5** - Structure des pages
- **CSS3** - Styles et design
- **Bootstrap** - Framework CSS responsive
- **jQuery** - Bibliothèque JavaScript
- **JavaScript** - Interactivité côté client

### Déploiement
- **Heroku** - Plateforme de déploiement (Procfile présent)
- **Gunicorn** - Serveur WSGI
- **GitHub Actions** - CI/CD (.github/workflows présent)

## 📁 Structure du Projet

```
ClassroomProject/
│
├── Classroom_project/         # Projet Django principal
│   ├── settings.py           # Configuration Django
│   ├── urls.py               # URLs principales
│   └── wsgi.py               # Configuration WSGI
│
├── base/                      # Application de base
│   ├── models.py             # Modèles de données
│   ├── views.py              # Vues
│   ├── forms.py              # Formulaires
│   └── templates/            # Templates HTML
│
├── assets/                    # Ressources statiques
│
├── static/                    # Fichiers statiques
│   ├── css/                  # Feuilles de style
│   ├── js/                   # Fichiers JavaScript
│   └── images/               # Images
│
├── staticfiles/               # Fichiers statiques collectés
│
├── .github/workflows/         # GitHub Actions CI/CD
│
├── manage.py                  # Script de gestion Django
├── requirements.txt           # Dépendances Python
├── Procfile                   # Configuration Heroku
├── runtime.txt                # Version Python pour Heroku
└── README.md                  # Documentation du projet
```

## 🚀 Installation et Configuration

### Prérequis

- **Python 3.8+** - Langage de programmation
- **pip** - Gestionnaire de paquets Python
- **Git** - Contrôle de version
- **Virtual Environment** (recommandé) - Environnement virtuel Python

### Installation

1. **Cloner le dépôt**
   ```bash
   git clone https://github.com/AmalChegdali/classroom-management-system.git
   cd classroom-management-system
   ```

2. **Créer un environnement virtuel**
   ```bash
   # Windows
   python -m venv venv
   venv\Scripts\activate
   
   # Linux/Mac
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Installer les dépendances**
   ```bash
   pip install -r requirements.txt
   ```

4. **Créer et configurer le fichier .env**
   ```bash
   # Créer un fichier .env à la racine du projet
   # Ajouter les variables suivantes :
   
   EMAIL_HOST = votre_email_host          # Ex: smtp.gmail.com
   EMAIL_PORT = votre_email_port          # Ex: 587
   EMAIL_HOST_USER = votre_email         # Votre adresse email
   EMAIL_HOST_PASSWORD = votre_mot_de_passe  # Mot de passe de l'email
   SECRET_KEY = votre_secret_key         # Clé secrète Django (générer une clé aléatoire)
   ```

5. **Appliquer les migrations**
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

6. **Créer un superutilisateur** (optionnel)
   ```bash
   python manage.py createsuperuser
   ```

7. **Collecter les fichiers statiques**
   ```bash
   python manage.py collectstatic
   ```

8. **Lancer le serveur de développement**
   ```bash
   python manage.py runserver
   ```

   L'application sera accessible sur `http://localhost:8000`

## 🔐 Configuration Email

Pour que les notifications par email fonctionnent, configurez votre fichier `.env` avec les paramètres de votre serveur email :

### Exemple pour Gmail :
```env
EMAIL_HOST = smtp.gmail.com
EMAIL_PORT = 587
EMAIL_HOST_USER = votre_email@gmail.com
EMAIL_HOST_PASSWORD = votre_mot_de_passe_app
EMAIL_USE_TLS = True
```

**Note** : Pour Gmail, vous devrez peut-être utiliser un "Mot de passe d'application" au lieu de votre mot de passe habituel.

## 🐳 Déploiement sur Heroku

Le projet est configuré pour être déployé sur Heroku :

1. **Installer Heroku CLI**
   ```bash
   # Télécharger depuis https://devcenter.heroku.com/articles/heroku-cli
   ```

2. **Se connecter à Heroku**
   ```bash
   heroku login
   ```

3. **Créer une application Heroku**
   ```bash
   heroku create nom-de-votre-app
   ```

4. **Configurer les variables d'environnement**
   ```bash
   heroku config:set SECRET_KEY=votre-secret-key
   heroku config:set EMAIL_HOST=smtp.gmail.com
   heroku config:set EMAIL_PORT=587
   heroku config:set EMAIL_HOST_USER=votre_email@gmail.com
   heroku config:set EMAIL_HOST_PASSWORD=votre_mot_de_passe
   heroku config:set DEBUG=False
   ```

5. **Déployer**
   ```bash
   git push heroku main
   ```

6. **Exécuter les migrations**
   ```bash
   heroku run python manage.py migrate
   heroku run python manage.py createsuperuser
   ```

## 🧪 Tests

```bash
# Exécuter tous les tests
python manage.py test

# Tester une application spécifique
python manage.py test base
```

## 📊 Fonctionnalités Avancées

- **Upload de fichiers** : Gestion des devoirs et documents
- **Notifications email** : Alertes par email pour les nouvelles soumissions
- **Interface responsive** : Design adaptatif avec Bootstrap
- **Gestion des rôles** : Système de permissions étudiants/enseignants
- **Recherche** : Recherche de devoirs et classes

## 🔒 Sécurité

- Authentification sécurisée avec Django
- Protection CSRF pour les formulaires
- Validation des fichiers uploadés
- Protection contre les injections SQL
- Gestion des permissions et rôles

## 📚 Utilisation

### Pour les Étudiants

1. **S'inscrire/Se connecter** : Créer un compte étudiant
2. **Rejoindre une classe** : Utiliser le code de classe fourni par l'enseignant
3. **Voir les devoirs** : Consulter les devoirs assignés
4. **Soumettre un devoir** : Uploader le fichier et soumettre
5. **Consulter les résultats** : Voir les notes et commentaires

### Pour les Enseignants

1. **Créer un compte enseignant** : S'inscrire en tant qu'enseignant
2. **Créer une classe** : Créer une nouvelle classe et obtenir le code
3. **Assigner des devoirs** : Créer et assigner des devoirs aux étudiants
4. **Évaluer les soumissions** : Noter et commenter les devoirs
5. **Retourner les résultats** : Envoyer les notes aux étudiants

## 🤝 Contribution

Les contributions sont les bienvenues ! Pour contribuer :

1. Fork le projet
2. Créez votre branche (`git checkout -b feature/AmazingFeature`)
3. Committez vos changements (`git commit -m 'Add some AmazingFeature'`)
4. Push vers la branche (`git push origin feature/AmazingFeature`)
5. Ouvrez une Pull Request

## 📄 Licence

Ce projet est sous licence personnelle. Tous droits réservés.

## 👥 Contributeurs

- **Amal Chegdali** - Développement et maintenance

-----------------------------------
<h2 align='center'>
Interface 
</h2>
<p align="center">
  <img src ="./assets/1.png" width = 500px>
</p>
<p align="center">
  <img src ="./assets/2.png" width = 500px>
</p>
<p align="center">
  <img src ="./assets/3.png" width = 500px>
</p>
<p align="center">
  <img src ="./assets/4.png" width = 500px>
</p>

-----------------------------------

###             Tech stack
`Backend` : Django <br>
`Database` : SQLite <br>
`Frontend` : CSS, HTML, Bootstrap, jQuery  <br>

-----------------------------------

- Tous les contributeurs qui ont participé au projet
- Bibliothèques open-source utilisées

## 📚 Ressources

- [Documentation Django](https://docs.djangoproject.com/)
- [Tutoriel Django](https://docs.djangoproject.com/en/stable/intro/tutorial01/)
- [Bootstrap Documentation](https://getbootstrap.com/docs/)
- [Déploiement Heroku](https://devcenter.heroku.com/articles/django-app-configuration)

## 🗺️ Roadmap

- [ ] Amélioration de l'interface utilisateur
- [ ] Ajout de tests unitaires et d'intégration
- [ ] Support de plusieurs types de fichiers
- [ ] Intégration de vidéos et médias
- [ ] Chat en temps réel entre étudiants et enseignants
- [ ] Tableaux de bord analytiques
- [ ] Export des notes en PDF/Excel
- [ ] Application mobile (React Native ou Flutter)
- [ ] Intégration avec Google Classroom
- [ ] Système de quiz intégré

## ⚠️ Notes Importantes

- Assurez-vous de configurer correctement les variables d'environnement dans `.env`
- Pour la production, utilisez PostgreSQL au lieu de SQLite
- Configurez `SECRET_KEY` et `DEBUG` correctement pour la production
- Assurez-vous que `ALLOWED_HOSTS` est correctement configuré
- Le fichier `.env` ne doit jamais être commité (utilisez `.gitignore`)

---

⭐ Si ce projet vous a été utile, n'hésitez pas à lui donner une étoile !

-----------------------------------
