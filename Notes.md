## set  Random Password flow
* cd /etc/nginx
* echo "" > .htpasswd
* sudo sh -c "echo -n 'admin:' >> /etc/nginx/.htpasswd"
* sudo sh -c "openssl passwd -apr1 >> /etc/nginx/.htpasswd"
* systemctl restart nginx

## NOTICE(human-computer interaction)
* Password: 
* Verifying - Password: 
* [root@iZj6c5nu6jo58ryap26im7Z nginx]# cat .htpasswd
* admin:$apr1$P8N3u5Q9$bt/HjzBaYvHS5PD.qG67q0

## Nginx settings

The easiest way to configure a performant, secure, and stable NGINX server.

https://www.digitalocean.com/community/tools/nginx

## Nginx support WebSockets
```
proxy_set_header Upgrade $http_upgrade;
proxy_set_header Connection upgrade;
```


#### How to set init for Ngnix password?

1. set nginx_htpasswd: Ture
2. set init configure
```
init_application:
  nginx:
    username: "admin"
    password: "admin"
    commands: 
      - htpasswd -b /etc/nginx/.htpasswd admin $new_password
      - systemctl restart nginx
```
