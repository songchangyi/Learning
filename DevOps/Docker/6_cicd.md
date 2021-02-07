# Docker CI CD

## 1 引言
项目部署时
1. 通过maven编译打包
2. 将文件上传到指定服务器中
3. 将war包放到tomcat目录中
4. 将Tomcat和war包转成一个镜像，由docker-compose去运行容器

## 2 CI介绍
持续集成：提交到Git仓库中，将项目重新构建并测试
- 快速发现错误
- 防止代码偏离主分支

## 3 实现CI
1. 搭建Gitlab服务器
  - 创建一个全新的虚拟机，指定至少4G的运行内存
  - 安装docker和docker-compose
  - 使用docker-compose.yml文件去安装gitlab（修改了/etc/ssh/sshd_config端口并重启sshd服务）
2. 搭建Gitlab-Runner

## 4 整合项目入门测试
1. 创建maven工程
2. 编写.gitlab-ci.yml文件
3. 将maven工程推送到gitlab中
4. 可以在gitlab中查看到gitlab-ci.yml编写的内容

## 5 CD介绍
持续交付，持续部署

持续交付：将代码交付给专业的测试团队去测试
持续部署：将测试通过的代码发布到生产环境
