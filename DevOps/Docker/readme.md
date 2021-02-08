# Docker

## 理论知识
### 虚拟化及其优势
虚拟化，是指通过虚拟化技术将一台计算机虚拟为多台逻辑计算机

每个逻辑计算机可运行不同的操作系统，并且应用程序都可以在相互独立的空间内运行而互不影响，从而显著提高计算机的工作效率

- [虚拟化，看这篇文章就够了](https://zhuanlan.51cto.com/art/201703/536043.htm)

### 如何完成物理资源虚拟化
使用Hypervisor（虚拟机监视器），分为两大类
- 第一类直接运行在物理机上，虚拟机运行在hypervisor上
- 第二类在物理机上安装正常的OS，再安装hypervisor生成和管理虚拟机

VMware、KVM、Xen、Virtual Box，都属于Hypervisor

- [虚拟化与云计算有什么区别](https://www.zhihu.com/question/22793847)

### 容器和虚拟机
容器和虚拟机的用途相似：都是将应用程序及其依赖项隔离到可以在任何地方运行的独立单元。此外，容器和VM消除了对物理硬件的需求，从而在能耗和成本效率方面允许更有效地使用计算资源

- 从虚拟化层面来看，传统虚拟化技术是对硬件资源的虚拟，容器技术则是对进程的虚拟，从而可提供更轻量级的虚拟化，实现进程和资源的隔离
- **从架构来看，Docker比虚拟化少了两层，取消了hypervisor层和GuestOS层，使用Docker Engine进行调度和隔离，所有应用共用主机操作系统，因此Docker较虚拟机更轻量级，在性能上优于虚拟化，接近裸机性能**
- 从应用场景来看，Docker和虚拟化则有各自擅长的领域，在软件开发、测试场景和生产运维场景中各有优劣

- [Docker容器与虚拟机区别](https://www.cnblogs.com/pangguoping/articles/5515286.html)

### 容器和镜像
简单来说，镜像是文件，容器是进程
- 容器是由镜像实例化而来
- docker 容器=镜像+可读层
- 容器是基于镜像创建的，即容器中的进程依赖于镜像中的文件

docker的镜像概念类似虚拟机的镜像。是一个只读的模板，一个独立的文件系统，包括运行容器所需的数据，可以用来创建新的容器。
docker容器类似虚拟机，可以执行包含启动，停止，删除等。每个容器间是相互隔离的。容器中会运行特定的运用，包含特定应用的代码及所需的依赖文件。

- [Docker中容器和镜像的关系](https://blog.csdn.net/qq_40722827/article/details/102827125)

### Docker优点
1. 保证了线上线下环境的一致性
2. 极大的简化了项目部署流程
3. 实现了沙盒机制，提高了安全性
4. 实现了模块化，提高了复用性
5. 实现了虚拟化，提高硬件利用率

- [docker在web开发中得使用流程是怎样的](https://www.zhihu.com/question/51134842)

### Docker和VM的区别
| 特性 | Docker | VM |
|------|--------|----|
| 启动速度 | 秒级 | 分钟级 |
| 磁盘使用 | MB | GB |
|   性能   | 接近原生 | 弱于原生 |
| 系统支持 | 成百上千 | 几十个 |
| 隔离性   | 安全隔离 | 完全隔离 |

- [docker容器与虚拟机有什么区别](http://qdcypf.com/q-551138.html)

## 使用Docker+GitLab CI/CD部署项目的通用流程
本地端：
1. 本地项目开发
2. 编写Dockerfile，docker-compose和.gitlab-ci文件，上传

GitLab CI：
1. GitLab runner首先build生成Docker镜像
2. GitLab runner run镜像来生成容器，并运行自动测试

GitLab CD：
1. 使用Ansible脚本来找到最新的镜像
2. 使用swarm来部署到目标环境中

## References
- [2020版-Docker最新超详细版教程通俗易懂](https://www.bilibili.com/video/BV1sK4y1s7Cj?from=search&seid=1518072086103692913)
