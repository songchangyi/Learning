# 自定义镜像

创建Dockerfile，并自定义镜像信息
```
# Dockerfile文件中常用的内容
# from：指定当前自定义镜像的依赖环境
# copy：将相对路径下的内容复制到自定义镜像中
# workdir：声明镜像的默认工作目录
# cmd：需要执行的命令（在workdir下执行，cmd可以写多个，只以最后一个为准）
from daocloud.io/library/tomcat:8.5.15-jre8
copy ssm.war /usr/local/tomcat/webapps
```

```
docker build -t 镜像名称：[tag] . # 创建镜像
docker images # 查看镜像
```
