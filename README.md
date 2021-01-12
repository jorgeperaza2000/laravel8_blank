# TEMPLATE LARAVEL 8 + DOCKER
# Requirements
- docker and docker-compose installed
- user not root, with provileges root

# Instalación

### Preparando entorno
###### Domain for applications
- nano /etc/hosts

    #Add the following line
     
    127.0.0.1 your_domain.local

###### Create folder and clone repository
- mkdir new_project && cd new_project 
- git clone https://github.com/jorgeperaza2000/laravel8_blank.git .
###### Editing configurations files
- nano docker-compose/nginx/vhost.conf

	#Search and replace
    
    server_name your_domain.local;

  
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

###### Start docker-compose 
- docker-compose up -d (for stop use docker-compose down)
###### Install laravel vendors 
- docker-compose exec app composer install
###### Generate laravel Api Key 
- docker-compose exec app php artisan key:generate
###### Run migrations
- docker-compose exec app php artisan migrate
