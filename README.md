## Dockerized laravel app using docker and docker-compose

### Install required dependencies (*inside laravel project folder*)

``docker run --rm -v $(pwd):/app composer install``

### 1. create a copy of the default *.env.example* file

``cp .env.example .env``

### 2. spin up container

``docker-compose up -d``

### 3. check container running or not 

``docker ps``

### 4. configure laravel container 

``docker-compose exec app nano .env``

### 5. generate a key and copy 

``docker-compose exec app php artisan key:generate``

### 6. to cache these setting into a file

``docker-compose exec app php artisan config:cache``

### 7. give permission inside to container to folder (if required otherwise not)

``docker-compose exec app chown -R www-data:www-data /var/www/storage``

