FROM nginx:latest

# 镜像维护者
MAINTAINER Fat Puffer <dcpuffer@outlook.com>

ADD nginx.conf /etc/nginx/conf.d/

# sed是一个Linux编辑器吧，此命令的作用是查找文件/etc/nginx/nginx.conf中包含user的行，并将此行的nginx替换成root
RUN sed -i '/user/{s/nginx/root/}' /etc/nginx/nginx.conf

# 删除原有配置文件，创建静态资源文件夹和ssl证书保存文件夹
RUN rm /etc/nginx/conf.d/default.conf \
 && mkdir -p /usr/share/nginx/html/static \
 && mkdir -p /usr/share/nginx/html/media \
 && mkdir -p /usr/share/nginx/ssl

CMD ["nginx", "-g", "daemon off;"]
