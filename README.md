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
