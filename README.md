# Quiz Library

Application web de bibliothèque de quiz avec Laravel : des questions et leurs réponses, gérées par des utilisateurs connectés et consultables publiquement.

## Fonctionnalités

- Inscription, connexion, réinitialisation du mot de passe et vérification de l'e-mail
- Création, modification et suppression de questions
- Ajout, modification et suppression de réponses pour chaque question
- Page publique de quiz, accessible sans compte
- Tableau de bord pour les utilisateurs connectés
- Gestion du profil

## Technologies

- PHP 8.2 et Laravel 11
- Laravel Breeze pour l'authentification
- Eloquent (modèles `Question` et `Response`, avec leurs migrations)
- Blade pour les vues
- Tailwind CSS et Vite

## Routes principales

| Méthode | Route | Rôle |
|---|---|---|
| GET | `/public-quiz` | quiz public |
| GET | `/quiz` | liste des questions |
| POST, PUT, DELETE | `/quiz`, `/quiz/{question}` | créer, modifier, supprimer une question (connecté) |
| POST | `/quiz/{question}/responses` | ajouter une réponse (connecté) |
| PUT, DELETE | `/responses/{response}` | modifier, supprimer une réponse (connecté) |
| GET | `/dashboard` | tableau de bord (connecté) |

## Installation

Prérequis : PHP 8.2 ou plus, Composer, Node.js et une base de données.

```bash
git clone https://github.com/imene-be/quiz-library-laravel.git
cd quiz-library-laravel
composer install
npm install
cp .env.example .env
php artisan key:generate
```

Renseignez la connexion à votre base dans `.env`, puis :

```bash
php artisan migrate
npm run dev        # dans un terminal
php artisan serve  # dans un autre terminal
```

L'application est disponible sur [http://localhost:8000](http://localhost:8000).

---

Réalisé par [Imène Bentifraouine](https://imenebe.fr).
