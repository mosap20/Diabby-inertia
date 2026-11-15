# Diabby Inertia

Application Laravel et React reliés par Inertia pour enregistrer les mesures de glycémie, les repas et les activités. L’espace connecté regroupe ces données dans un tableau de bord et un calendrier. Les écrans de suivi incluent des graphiques et statistiques.

## Installation locale

Installez PHP 8.2 ou supérieur avec PDO SQLite, Composer, ainsi que Node.js 22 et npm. Depuis le dossier de l’application Laravel, exécutez les commandes suivantes. Si un fichier `.env` existe déjà, conservez-le et vérifiez que `DB_CONNECTION=sqlite`.

```sh
composer install
php -r "file_exists('.env') || copy('.env.example', '.env');"
php artisan key:generate
php -r "file_exists('database/database.sqlite') || touch('database/database.sqlite');"
php artisan migrate
npm ci
```

Dans un terminal, lancez `php artisan serve`. Dans un second terminal, lancez `npm run dev`. Ouvrez ensuite l’adresse indiquée par Artisan, généralement `http://127.0.0.1:8000`.

Pour compiler les ressources, utilisez `npm run build`. Après compilation, lancez les tests PHP avec `php artisan test`.

Les routes sont déclarées dans [routes/web.php](routes/web.php). Les contrôleurs se trouvent dans [app/Http/Controllers/](app/Http/Controllers/) et les écrans React dans [resources/js/](resources/js/).
