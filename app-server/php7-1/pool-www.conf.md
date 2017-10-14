<pre>
[www]

;prefix = /path/to/pools/$pool

user = www-data
group = www-data

;listen = /run/php/php7.1-fpm.sock
listen = 127.0.0.1:9000

listen.backlog = 65536

listen.owner = www-data
listen.group = www-data
;listen.mode = 0660

;listen.acl_users =
;listen.acl_groups =

;listen.allowed_clients = 127.0.0.1

pm = dynamic

pm.max_children = 20

pm.start_servers = 5

pm.min_spare_servers = 2

pm.max_spare_servers = 5

pm.process_idle_timeout = 2s;

pm.max_requests = 5000
</pre>