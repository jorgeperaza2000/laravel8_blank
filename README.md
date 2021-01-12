INSTALL

- mkdir new_project
- cd new_project
- git clone https://github.com/jorgeperaza2000/laravel8_blank.git .
- nano docker-compose/nginx/vhost.conf
    #Search and replace 
    server_name your_domain.local;
- nano /etc/hosts
    #add the following line
    127.0.0.1 your_domain.local
- cp .env.example .env
- nano .env
    ...
    DB_CONNECTION=mysql
    DB_HOST=db
    DB_PORT=3306
    DB_DATABASE=your_database_name
    DB_USERNAME=your_user_name
    DB_PASSWORD=your_password
    ...
- docker-compose up -d
- docker-compose exec app composer install
- docker-compose exec app php artisan key:generate

- In your browser test your_domain.local
