# Application Laravel

## Création

```sh
curl -s https://laravel.build/example-app | bash
```

## Récupérer une application Laravel
-  Cloner le repository de GitHub
    ```sh
    git clone git@github.com:info-telecom-strasbourg/nom-application.git
    ```
- Se déplacer dans l'application
    ```sh
    cd nom-application
    ```
- Installer `sail` dans l'application (long)
  ```sh
  composer require laravel/sail --dev
  ```
- Créer le `.env`
  ```
  cp .env.example .env
  ```
- Génération de la clé d'application
  ```
  sail artisan key:generate
  ```

- Création de l'alias (**Cet alias est permanent**)
    ```sh
    sudo echo '\nalias sail='bash vendor/bin/sail' >> ~/.bashrc && source ~/.bashrc
    ```
    Vous pouvez également utiliser la commande
    ```sh
    alias sail='bash vendor/bin/sail
    ```
    Qui créera un alias dans le terminal courant (**Vous devrez l'utiliser pour chaque nouveau terminal**)

## Lancer l'application

Il faut lancer les conteneurs pour pouvoir visualiser le site, phpMyAdmin :

- Start les conteneurs :
  ```sh
  ./vendor/bin/sail up
  ```
  Ou avec alias
  ```sh
  sail up -d
  ```
  
  *Cette commande est longue la première fois.*

- Stop les conteneurs : 
  ```sh
  sail down
  ```

## Visualiser l'application

- Website : http://localhost
- PhpMyAdmin : http://localhost:8181
- MailHog : http://localhost:8025

## Important
Les commandes `php artisan` doivent **ABSOLUMENT** être remplacé par `sail artisan`.

<br>

`php artisan` : execute la commande localement<br>
`sail artisan`: execute la commande dans Laravel Sail (dans notre conteneur)

