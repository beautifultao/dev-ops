# 将容器中的nginx.conf拷贝出来以方便修改挂载
docker container cp nginx:/etc/nginx/nginx.conf  D:\Projects\SpringBoot\dev-ops\nginx\conf
docker container cp nginx:/etc/nginx/conf.d/default.conf  D:\Projects\SpringBoot\dev-ops\nginx\conf\conf.d\default.conf
docker container cp nginx:/usr/share/nginx/html/index.html  D:\Projects\SpringBoot\dev-ops\nginx\html


docker run -d \
--name Nginx \
-p 80:80 \
-v D:/Projects/SpringBoot/dev-ops/nginx/logs:/var/log/nginx \
-v D:/Projects/SpringBoot/dev-ops/nginx/html:/usr/share/nginx/html \
-v D:/Projects/SpringBoot/dev-ops/nginx/conf/nginx.conf:/etc/nginx/nginx.conf \
-v D:/Projects/SpringBoot/dev-ops/nginx/conf/conf.d:/etc/nginx/conf.d \
-v D:/Projects/SpringBoot/dev-ops/nginx/ssl:/etc/nginx/ssl/ \
--privileged=true nginx:stable-perl
docker run -d --name nginx -p 80:80 -v D:/Projects/SpringBoot/dev-ops/nginx/logs:/var/log/nginx -v D:/Projects/SpringBoot/dev-ops/nginx/html:/usr/share/nginx/html -v D:/Projects/SpringBoot/dev-ops/nginx/conf/nginx.conf:/etc/nginx/nginx.conf -v D:/Projects/SpringBoot/dev-ops/nginx/conf/conf.d:/etc/nginx/conf.d -v D:/Projects/SpringBoot/dev-ops/nginx/ssl:/etc/nginx/ssl/ --privileged=true nginx:stable-perl

