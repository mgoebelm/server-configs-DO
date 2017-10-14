## 1 - Load Balancer - Configurações

### Tag
```
app-online
```

#### Forwarding rules
```
HTTP on port 80  HTTP on port 80
HTTPS on port 443  HTTPS on port 443
```

#### Algorithm 
```
Least Connections
```

#### Health checks 
```
http://0.0.0.0:80/health-check
```

#### Sticky sessions 
```
Cookie name - DO-LB2
Cookie TTL - 300s (5 minutes)
```

#### SSL
```
No redirect
```


***

[Voltar à Página Inicial](../README.md)