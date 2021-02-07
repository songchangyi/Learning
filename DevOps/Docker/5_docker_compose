# Docker-compose

由来
- 运行一个镜像，需要添加大量的参数。可以通过docker-compose编写这些参数
- docker-compose可以帮助我们批量管理容器
- 只需要通过docker-compose.yml文件来维护

## 1 下载Docker-Compose
1. 在github官网进行下载
2. 将文件放置到特定目录下
3. 修改文件名称，更改执行权限
```
mv xxx docker-compose
chmod 777 docker-compose
```
4. 配置环境变量
```
mv docker-compose /use/local/bin
vi /etc/profile
  export PATH=$JAVA_HOME:/usr/local/bin:$PATH
source /etc/profile
```
5. 测试
在任意目录下输入docker-compose

## 2 编写docker-compose.yml
- yml文件以key: value方式来指定配置信息
- 多个配置信息以换行+缩进的方式来区分。不要使用制表符
```
version: '3.1'
services:
  mysql:            # 服务的名称
    restart: always # 代表跟着docker启动
    image: daocloud.io/library/mysql:5.7.4 # 指定镜像路径
    container_name: mysql # 指定容器名称
    ports:
      - 3306:3306 # 指定端口号的映射
    environment:
      MYSQL_ROOT_PASSWORD: root # 指定root用户登陆密码
      TZ: Asia/Shanghai
    volumns:
      - /opt/docker_mysql_tomcat/mysql_data:/var/lib/mysql # 映射数据卷
  tomcat:
    restart: always
    image: daocloud.io/library/tomcat:8.5.15
    container_name: tomcat
    ports:
      - 8080:8080
    environment:
      TZ: Asia/Shanghai
    volumns:
      -/opt/docker_mysql_tomcat/tomcat_webapps:/usr/local/tomcat/webapps
      -/opt/docker_mysql_tomcat/tomcat_logs:/usr/local/tomcat/logs
```

## 3 使用Docker-Compose管理容器
在使用docker-compose命令时，默认在当前目录下找docker-compose.yml文件
```
# 基于docker-compose命令启动管理的容器
docker-compose up -d
docker ps
# 关闭并删除容器
docker-compose down
# 开启或关闭已经存在的由docker-compose维护的容器
docker-compose start/stop/restart
# 查看由docker-compose维护的容器
docker-compose ps
# 查看日志
docker-compose logs -f
```

## 4 docker-compose配合Dockerfile使用
生成自定义镜像的同时启动当前镜像，并且由dokcer-compose去管理

docker-compose.yml
```
version: '3.1'
services:
  ssm:
    restart: always
    build: # 构建自定义镜像
      context: ../ # 指定Dockerfile的所在路径
      dockerfile: Dockerfile
    image: ssm:1.0.1
    container_name: ssm
    ports:
      - 8081:8080
    environment:
      TZ: Asia/Shanghai
```

Dockerfile
```
from daocloud.io/library/tomcat:8.5.15
copy ssm.war /usr/local/tomcat/webapps
```

```
docker-compose up -d # 直接启动基于docker-compose和Dockerfile构建的自定义镜像
docker-compose build # 重新构建镜像
docker-compose up -d --build # 运行前重新构建
```
