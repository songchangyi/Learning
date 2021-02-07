# Docker应用

## 1 准备SSM工程

## 2 准备MySQL容器
```
docker pull mysql # 拉取MySQL镜像
docker run -d -p 3306:3306 --name mysql -e MYSQL_ROOT_PASSWORD=root daocloud.io/library/mysql:5.7.4
```

## 3 准备Tomcat容器
```
docker run -d -p 8080:8080 --name tomcat b8
docker cp 文件名称 容器id：容器内部路径
```

## 4 数据卷
数据卷：将宿主机的一个目录映射到容器的一个目录中。改变宿主机中操作目录的内容，容器内部的文件也会跟着改变
```
docker volume create 数据卷名称 # 创建数据卷，默认存放到/var/lib/docker/volumes/数据卷名称/_data
docker volumn inspect 数据卷名称 # 查看数据卷详细信息
docker volumn ls # 查看全部数据卷
docker volumn rm 数据卷名称 # 删除数据卷
docker run -v 数据卷名称：容器内部的路径 镜像id # 映射数据卷时，如果不存在将会自动创建在默认目录下
docker run -v 路径：容器内部的路径 镜像id # 也可以指定一个路径作为数据卷的存放位置。这个路径下是空的
```
