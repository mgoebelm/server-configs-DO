## 1 - PHP 7.1 - Instruções

- Instalar 

```
sudo add-apt-repository ppa:ondrej/php
sudo apt-get update
```

```
sudo apt-get install php7.1-fpm php7.1 php7.1-mbstring php7.1-mcrypt php7.1-mysql php7.1-xml php7.1-curl php7.1-gmp php7.1-gd php7.1-zip
```

- Ajustar configuração de segurança default do PHP

```
sudo nano /etc/php/7.1/fpm/php.ini
```
> Alterar para
>
> cgi.fix_pathinfo=0

>

> !! Observação !! cgi.fix_pathinfo=1  is an extremely insecure setting because it tells PHP to attempt to execute the closest file it can find if a PHP file does not match exactly. This basically would allow users to craft PHP requests in a way that would allow them to execute scripts that they shouldn't be allowed to execute.



- Configurar o pool principal (www)


```
sudo nano /etc/php/7.1/fpm/pool.d/www.conf
```

[Resumido www.conf](pool-www.conf.md)

[Completo www.conf](complete-pool-www.conf.md)


- Reiniciar serviço para atualizar as configurações

``` 
sudo service php7.1-fpm restart
```


<b>!!! Configuração PHP Completa !!!</b>


***

[Voltar à Página Inicial](../../README.md)