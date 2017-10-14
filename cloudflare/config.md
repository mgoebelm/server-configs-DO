## 1 - Cloudflare - Settings

#### DNS Records
```
A - fatalmodel.com - xxx.xxx.xxx.xxx (Load Balancer IP)
CNAME - www - fatalmodel.com - Automatic TTL
CNAME - fm-static-1 - fatalmodel.com
```

#### Crypto
```
SSL Flexible
Automatic HTTPS Rewrites 
```

#### Page Rules
```
http://fatalmodel.com/* 
- Always Use HTTPS
```
```
fm-static-1.fatalmodel.com/* 
- Browser Cache TTL: a year, 
- Always Online: On, 
- Cache Level: Cache Everything, 
- Edge Cache TTL: a month
```