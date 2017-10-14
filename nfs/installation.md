## 1 - NFS - Network File System - Instruções

[Mais detalhes sobre NFS](https://www.digitalocean.com/community/tutorials/how-to-set-up-an-nfs-mount-on-ubuntu-16-04)

## On the Host

- Instalação

```
sudo apt-get update
sudo apt-get install nfs-kernel-server
```

- Criar pasta a ser compartilhada

```
sudo mkdir /var/nfs/fshared -p
sudo chown nobody:nogroup /var/nfs/fshared
```

- Configurar o servidor NFS

```
sudo nano /etc/exports
```

> \# Adicionar o ip de cada servidor que terá permissão para se conectar à pasta compartilhada
>
>```
>/var/nfs/fshared xxx.xxx.xxx.xxx(rw,sync,insecure_locks,insecure,no_root_squash) yyy.yyy.yyy.yyy(rw,sync,insecure_locks,insecure,no_root_squash) 
>```

``` 
sudo service nfs-kernel-server restart
```


> UFW - Liberar Firewall para cada servidor para a porta do NFS (2049)
>
> ```
> sudo ufw allow from xxx.xxx.xxx.xxx to any port nfs
> sudo ufw allow from yyy.yyy.yyy.yyy to any port nfs
> sudo ufw status
> ```

***

***


## On the Client

- Instalação

```
sudo apt-get update
sudo apt-get install nfs-common
```

- Criar pasta para receber o compartilhamento

``` 
sudo mkdir -p /var/client/fshared
sudo mount xxx.xxx.xxx.xxx:/var/nfs/fshared /var/client/fshared
```

- Verificar se foi montada com sucesso

``` 
df -h
```

- Desmontar a unidade

``` 
sudo umount /var/client/fshared
```

- Configurar para montagem automática ao inicializar o sistema

``` 
sudo nano /etc/fstab
``` 

> \# Adicionar ao final do arquivo
>
>``` 
>xxx.xxx.xxx.xxx:/var/nfs/fshared   /var/client/fshared   nfs4    _netdev,auto  0  0
>```


- Reiniciar o sistema

``` 
sudo reboot now
``` 

- Verificar se a pasta compartilhada foi montada com sucesso

``` 
df -h
```


***

[Voltar à Página Inicial](../README.md)