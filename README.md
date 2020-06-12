# docker-compose-deploy-django

## 部署：

##### 1. 首先需要安装docker和docker-compose
- 此处不赘述，自行百度

##### 2. 找到项目配置文件`settings.py`

- 修改`ALLOWED_HOSTS = ['宿主机的真实IP地址', 'localhost', '127.0.0.1']`
- 修改`DEBUG = False`

##### 3. 进入项目文件加docker_project

- 执行以下语句构建镜像

`
sudo docker-compose build
`

##### 4. 启动镜像构建容器

- 执行以下命令

`
sudo docker-compose up -d
`

##### 5. 查看容器名称
- 执行以下语句

`
sudo docker ps
`

##### 6. 执行Django命令并启动uwsgi服务器（根据web服务器的容器名）

- 执行以下命令

`
sudo docker exec -it docker_project_web_1 /bin/bash start.sh
`

##### 7. 浏览器进行访问

- 根据你的物理机真实ip访问`/admin`
