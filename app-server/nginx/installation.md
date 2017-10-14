## 1 - Nginx - Instruções

[Mais detalhes sobre Nginx](https://www.digitalocean.com/community/tutorials/como-instalar-o-nginx-no-ubuntu-16-04-pt)


***
>
> <b> !! IMPORTANTE !!</b>
> Todos servidores devem receber esta alteração para melhorar a performance geral do sistema
> 
> [Melhorar Performance do Sistema](../../sysctl.conf.md)
>
***


- Instalar


```
sudo apt-get update
```


```
sudo apt-get install nginx
```


Acessar o endereço do site, deverá aparecer "Welcome to Nginx"

<small><em>Uhuuuuuuulll  o/</em></small>

- Configurar nginx.conf

```
sudo nano /etc/nginx/nginx.conf
```

```
 user www-data www-data;

 worker_processes auto;
 
 pid /run/nginx.pid;

 events {
     worker_connections 4000;
     multi_accept on;
     use epoll;
 
 http {

     #cache informations about FDs, frequently accessed files
     #can boost performance, but you need to test those values
     open_file_cache max=200000 inactive=20s;
     open_file_cache_valid 30s;
     open_file_cache_min_uses 2;
     open_file_cache_errors on;

     #fastcgi params
     fastcgi_buffers 16 16k;
     fastcgi_buffer_size 32k;
     proxy_buffer_size   128k;
     proxy_buffers   4 256k;
     proxy_busy_buffers_size   256k;
      
     access_log off;
     sendfile on;
     tcp_nopush on;
     tcp_nodelay on;
     keepalive_timeout 15;
     types_hash_max_size 2048;
     server_tokens off;
```

.


> **Liberar Nginx no UFW  ( Firewall )**
> 
> ``` 
> sudo ufw status
> sudo ufw disable
> sudo ufw allow 'Nginx HTTP'
> sudo ufw status
> sudo ufw enable
> ``` 

[Mais detalhes sobre UFW](../ufw/installation.md)

**********

## [Instalar PHP](../php7-1/installation.md)

<small>tudo pronto? booraaaa!!!</small>

**********




- Configurar o Nginx para trabalhar em conjunto com o PHP


```
sudo nano /etc/nginx/sites-available/default
```


<pre>
server {
    listen 80 default_server;
    listen [::]:80 default_server ipv6only=on;

    root <strong>/var/www/folder/public</strong>;
    index index.php index.html index.htm;

    server_name <strong>server_domain_name_or_IP</strong>;

    location / {
        try_files $uri $uri/ =404;
    }

    error_page 404 /404.html;
    error_page 500 502 503 504 /50x.html;
    location = /50x.html {
        root /usr/share/nginx/html;
    }

    location ~ \.php$ {
        try_files $uri =404;
        fastcgi_split_path_info ^(.+\.php)(/.+)$;
        fastcgi_pass <strong>127.0.0.1</strong>;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}
</pre>


```
sudo service nginx restart
```

***

[Voltar à Página Inicial](../../README.md)