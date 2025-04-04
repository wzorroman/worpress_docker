# run the project
    $ docker-compose up -d

## check the service logs 
    $ docker-compose logs <service_name>

# You can now check that your certificates have been mounted to the webserver container with docker-compose exec:
    $ docker-compose exec webserver ls -la /etc/letsencrypt/live

# Remove all volumes
    $ docker compose down --volumes

# check status docker
    $ docker-compose ps
    
    Name                 Command               State                Ports              
    -------------------------------------------------------------------------------------
    certbot     certbot certonly --webroot ...   Up      443/tcp, 80/tcp                 
    db          docker-entrypoint.sh --def ...   Up      3306/tcp, 33060/tcp             
    webserver   nginx -g daemon off;             Up      0.0.0.0:80->80/tcp,:::80->80/tcp
    wordpress   docker-entrypoint.sh php-fpm     Up      9000/tcp

# show ip in local
    $ docker inspect webserver
    
