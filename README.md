# filament-employees
employee-laravel9-filament
1. Create project
    composer create-project laravel/laravel:^9.0 your-project-name
2. Install Breeze
    composer require laravel/breeze --dev
    php artisan breeze:install
    npm i
    npm run dev
3. Create Database
    php artisan migrate
4. Install Filament
    composer require filament/filament
    php artisan make:filament-user
    
