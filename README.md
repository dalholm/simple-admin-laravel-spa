<a href="https://packagist.org/packages/dalholm/laravel-spa-starter-kit"><img src="https://poser.pugx.org/dalholm/laravel-spa-starter-kit/d/total.svg" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/dalholm/laravel-spa-starter-kit"><img src="https://poser.pugx.org/dalholm/laravel-spa-starter-kit/v/stable.svg" alt="Latest Stable Version"></a>

# Update
Use [Laravel, sanctum, SPA](https://github.com/dalholm/larabue-simple-laravel-sanctum-spa-admin) repo instead!!

# Laravel Vuejs SPA Starter Kit
This project is a simple lightweight SPA admin template based on laravel and vuejs. It's quick to get started.

<p align="center">
<img src="https://i.imgur.com/UiPZozv.png">
</p>

## Features

- Laravel 5.7 
- Vue + VueRouter + Vuex + VueI18n + ESlint
- Pages with dynamic import and custom layouts
- Login, register and password reset
- Authentication with JWT
- Socialite integration
- Bootstrap 4 + Font Awesome 5

## Installation
- run `composer create-project dalholm/laravel-spa-starter-kit`
- Edit `.env` and set your database connection details
-  run `php artisan key:generate` and `php artisan jwt:secret`
- `php artisan migrate`
- `npm install` or `yarn`

## Usage

#### Development

```bash
# build and watch
npm run watch

# serve with hot reloading
npm run hot
```

#### Production

```bash
npm run production
```

#### Thanks
This repo was based on [cretueusebiu/laravel-vue-spa](https://github.com/cretueusebiu/laravel-vue-spa)
