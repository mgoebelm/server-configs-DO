## 1 - Nginx - Instruções


```
sudo apt-get update
```


```
sudo apt-get install nginx
```


Acessar o endereço do site, deverá aparecer "Welcome to Nginx"


[Instalar PHP](../php7-1/installation.md)

Configurar o Nginx para trabalhar em conjunto com o PHP

```
sudo nano /etc/nginx/sites-available/default
```


<pre>
server {
    listen 80 default_server;
    listen [::]:80 default_server ipv6only=on;

    root <strong>/var/www/folder/public</strong>;
    index index.php index.html index.htm;

    server_name <span style="color:red">server_domain_name_or_IP</span>;

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
        fastcgi_pass 127.0.0.1;
        fastcgi_index index.php;
        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
        include fastcgi_params;
    }
}
</pre>


[Voltar à Página Inicial](../../README.md)