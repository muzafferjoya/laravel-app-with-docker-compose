## Dockerized laravel app using docker and docker-compose

### Install required dependencies (*inside laravel project folder*)

```shdocker run --rm -v $(pwd):/app composer install```
### or
```sh
docker run --rm -v $(pwd):/app composer install--ignore-platform-reqs
``` 

### 1. create a copy of the default *.env.example* file

```sh
cp .env.example .env
```

### 2. spin up container

```sh
docker-compose up -d
```

### 3. check container running or not 

```sh
docker ps
```

### 4. configure laravel container 

```sh
docker-compose exec app vim .env
```

### 5. generate a key and copy 

```sh
docker-compose exec app php artisan key:generate
```

### 6. to cache these setting into a file

```sh
docker-compose exec app php artisan config:cache
```

### 7. give permission inside to container to folder (if required otherwise not)

```sh
docker-compose exec app chown -R www-data:www-data /var/www/storage
```

