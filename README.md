## Dockerized laravel app using docker and docker-compose

### spin up container

``docker-compose up -d``

### check container running or not 

``docker ps``

### generate a key and copy 

``docker-compose exec app php artisan key:generate``

### to cache these setting into a file

``docker-compose exec app php artisan config:cache``

### give permission inside to container to folder

``docker-compose exec app chown -R www-data:www-data /var/www/storage``
