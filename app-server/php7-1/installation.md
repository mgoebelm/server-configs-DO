## 1 - PHP 7.1 - Instruções

```
`sudo add-apt-repository ppa:ondrej/php`
sudo apt-get update
```

```
sudo apt-get install php7.1-fpm php7.1 php7.1-mbstring php7.1-mcrypt php7.1-mysql php7.1-xml php7.1-curl php7.1-gmp php7.1-gd php7.1-zip
```

```
sudo nano /etc/php/7.1/fpm/php.ini
```


Alterar o campo

`cgi.fix_pathinfo=0`


Configurar o pool principal (www)


```
sudo nano /etc/php/7.1/fpm/pool.d/www.conf
```

[Resumido www.conf](pool-www.conf.md)

[Completo www.conf](complete-pool-www.conf.md)


<b>!!! Configuração PHP Completa !!!</b>

[Voltar à Página Inicial](../../README.md)