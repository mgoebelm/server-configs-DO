## 1 - Mysql - Instruções

[Mais detalhes sobre Mysql](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-16-04)

```
sudo apt-get update
sudo apt-get install mysql-server
sudo mysql_secure_installation
```


> Recomendado instalar UFW ( Firewall ) e liberar somente o Mysql
>
> [Mais detalhes sobre UFW](../UFW/installation.md)



Configurações gerais do Mysql

```
sudo nano /etc/mysql/my.cnf
```

> \#preferencialmente ip da rede privada
> 
> bind-address            = xxx.xxx.xxx.xxx





