set  Random Password flow:
1,cd /etc/nginx
2,echo "" > .htpasswd
3,sudo sh -c "echo -n 'admin:' >> /etc/nginx/.htpasswd"
4,sudo sh -c "openssl passwd -apr1 >> /etc/nginx/.htpasswd"

======human-computer interaction=====
Password: 
Verifying - Password: 
[root@iZj6c5nu6jo58ryap26im7Z nginx]# cat .htpasswd
admin:$apr1$P8N3u5Q9$bt/HjzBaYvHS5PD.qG67q0

5,systemctl restart nginx
