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
    php artisan make:filament-user (lalu isi username dan password)
    - to change many times attemp login, change in this code 
    public function ensureIsNotRateLimited(): void
    {
        // 5 is default many times attemp login
        //if (! RateLimiter::tooManyAttempts($this->throttleKey(), 5)) {
          if (! RateLimiter::tooManyAttempts($this->throttleKey(), 3)) {
            return;
        }

        event(new Lockout($this));

        $seconds = RateLimiter::availableIn($this->throttleKey());

        throw ValidationException::withMessages([
            'email' => trans('auth.throttle', [
                'seconds' => $seconds,
                'minutes' => ceil($seconds / 60),
            ]),
        ]);
    }

5. Create model
    php artisan make:model Country (State, City, Department, Employee)
    
