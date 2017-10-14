## 1 - UFW ( Firewall ) - Instruções

[Mais detalhes sobre UFW](https://www.digitalocean.com/community/tutorials/how-to-setup-a-firewall-with-ufw-on-an-ubuntu-and-debian-cloud-server)


**Instalar UFW  ( Firewall )**

``` 
sudo apt-get install ufw
```

Confirmar se IPV6 está habilitado

```
sudo nano /etc/default/ufw
```
> IPV6=yes

Configurações Default - bloqueia todas entradas e libera saídas
``` 
sudo ufw default deny incoming
sudo ufw default allow outgoing
```

Libera acesso SSH e Nginx
``` 
sudo ufw allow ssh
sudo ufw status
sudo ufw enable
``` 


[Voltar à Página Inicial](../../README.md)