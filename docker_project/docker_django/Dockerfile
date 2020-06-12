FROM python:3.7.2

MAINTAINER Fat Puffer <dcpuffer@outlook.com>

 
# 在容器内/var/www/html/下创建docker_django文件夹
RUN mkdir -p /var/www/html/docker_django
 
# 设置容器内工作目录
WORKDIR /var/www/html/docker_django
 
# 将当前目录文件加入到容器工作目录中（. 表示当前宿主机目录）
ADD . /var/www/html/docker_django
 
# 利用 pip3 安装依赖
RUN pip3 install -r requirements.txt -i https://pypi.douban.com/simple 
# RUN pip3 install uwsgi -i https://pypi.douban.com/simple 
# RUN ln -s /usr/local/python3/bin/uwsgi /usr/bin/uwsgi

# Windows环境下编写的start.sh每行命令结尾有多余的\r字符，需移除。
RUN sed -i 's/\r//' ./start.sh
 
# 设置start.sh文件可执行权限
RUN chmod +x ./start.sh
