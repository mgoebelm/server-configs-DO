## 1 - Redis - Instruções


### Instalação

```
sudo apt-get udpate 
sudo apt-get install redis-server
```

:D

****

Alguns parâmetros a serem observados, mas vale a pena a leitura completa do arquivo

``` 
sudo nano /etc/redis/redis.conf
```

> \# ip da rede privada do servidor
>
> bind xxx.xxx.xxx.xxx
>
> port 6379
> 
> tcp-backlog 65535
> 
