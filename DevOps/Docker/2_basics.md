# Docker基本操作

## 1 安装
[Install Docker](https://docs.docker.com/engine/install/ubuntu/)

启动Docker服务
```
systemctl start docker
```

设置开机自动启动
```
systemctl enable docker
```

测试
```
docker run hello-world
```

## 2 中央仓库
1. Docker官方的中央仓库：https://hub.docker.com/
2. 国内的镜像网站：hub.daocloud.io
3. 公司内采用私服的方式拉取镜像
  - 需要添加配置：/etc/docker/daemon.json
  - 重启两个服务

## 3 镜像的操作
拉取镜像到本地
```
docker pull daocloud.io/library/tomcat:8.5.15-jre8
```

查看全部本地的镜像
```
docker images
```

删除本地镜像
```
docker rmi eb27600d584e
```

镜像的导入导出
```
docker save -o /path/to/save/ image_id # 将本地的镜像导出
docker load -i image_file # 加载本地的镜像
docker tag image_id tomcat:8.5 # 修改镜像名称
```

## 4 容器的操作
1. 运行容器
```
docker run image_id|image_name # 简单版
docker run -d -p 宿主机端口：容器端口 --name 容器名称 image_id|image_name
# -d 代表后台运行容器
# -p 宿主机端口：容器端口：为了映射当前Linux的端口和容器端口
# --name 指定容器名称
```

2. 查看正在运行的容器
```
docker ps [-qa]
# -a 查看全部容器，包括没有运行的
# -p 只查看容器标识
```

3. 查看容器日志
```
docker logs -f 容器id
# -f：可以滚动查看日志最后几行
```

4. 进入到容器内部
```
docker exec -it 容器id bash
```

5. 删除容器（需要先停止）
```
docker stop 容器id
docker stop $(docker ps -qa) # 停止全部容器
docker rm 容器id
docker rm $(docker ps -qa) # 删除全部容器
```

6. 启动容器
```
docker start 容器id
```
