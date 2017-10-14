## 1 - Redis - Instruções


### Instalação

```
sudo apt-get update 
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
> requirepass my-ultra-s3cr3t-pa$$word-with-many#many-characters-and-variables
>
> maxmemory **7gb**
>
> maxmemory-policy volatile-lru


***

[Voltar à Página Inicial](../README.md)