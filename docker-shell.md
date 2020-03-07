# docker 常识

##　docker shell
```
docker run 
    -d 后台运行
    -it 命令行的交互模式
    -p 端口映射　主机端口：容器端口
    -P 随机端口绑定
```
构造
* docker build -t dst:v1.0 ./base base文件夹下有dockerfile
* docker tag ubuntu:15.10 runoob/ubuntu:v3 将镜像ubuntu:15.10标记为 runoob/ubuntu:v3 镜像

启动：
* docker run -d -P {image-id/name} 
* docker exec -it {container-id/name} /bin/bash 进入容器

查看：
* docker images 查看所有镜像
* docker ps 查看所有容器
* docker ps -a  查看所有容器＋已经停止的容器
* docker stats {container-id} 查看容器使用状态
* docker history {image-id} 查看镜像的构建过程

监控
* docker stats -a 监控主机下所有的容器
* docker stats {container} 监控主机下的某个容器
* docker stats --no-stream {container}　

删除：
* docker rm {container-id}　删除容器
* docker rmi {image-id}　删除镜像
* docker rm $(docker ps -aq) 删除所有容器
* docker rmi $(docker images | grep "^<none>" | awk "{print $3}") 想要删除untagged images，也就是那些id为<None>的image的话可以用
* docker rmi $(docker images -q) 删除全部镜像


关闭：
* docker stop {container-id}
* docker start {container-id}
* docker kill {container-id}
* docker restart {container-id}
* docker stop $(docker ps -q) 停用全部容器


## docker-compose shell
* docker-compose ps 查看当前镜像下的文件
* docker-compose stop 停止当前文件夹下的容器
* docker-compose up -d　发布当前文件下的镜像
* docker-compose build 重新构建镜像
* docker-compose up --build -d  重新构建启动
* docker-compose up -d 构建启动

