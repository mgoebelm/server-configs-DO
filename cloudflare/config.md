## 1 - Cloudflare - Settings

#### DNS Records
```
A - fatalmodel.com - xxx.xxx.xxx.xxx (Load Balancer IP)
CNAME - www - ftmdl.com - Automatic TTL
CNAME - fm-static-1 - ftmdl.com
```

#### Crypto
```
SSL Flexible
Automatic HTTPS Rewrites 
```

#### Page Rules
```
http://ftmdl.com/* 
- Always Use HTTPS
```
```
fm-static-1.ftmdl.com/* 
- Browser Cache TTL: a year, 
- Always Online: On, 
- Cache Level: Cache Everything, 
- Edge Cache TTL: a month
```


***

[Voltar à Página Inicial](../README.md)