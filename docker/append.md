## 容器的基本操作

#### 启动容器

`docker run IMAGE [COMMAND] [ARG...]`

- docker run ubuntu echo 'Hello World'
- docker run -i -t ubuntu /bin/bash
- -i --interactive=true | false 默认为false 打开容器标准输入(交互模式)的选项
- -t --tty=true | false 默认是false 创建伪tty终端的选项
- --name=自定义容器名 为即将创建的容器指定名称 默认自动创建一个名称

`docker start [-i] [NAME/ID]`
- 重新启动已经停止的容器

#### 查看容器

`docker ps [-a] [-l]`
- 默认显示正在运行中的容器
- -a 显示所有容器
- -l 显示最近一次使用的容器

`docker inspect [ID/NAME]`
- 查看指定容器的详细配置信息

#### 删除容器
`docker rm [NAME/ID]`
- 删除已经停止运行的容器

#### 查看容器状态

`docker logs [-f] [-t] [-tail] [ID/NAME]`
- 查看容器日志
- -f --follows=true | false 默认为false 跟踪日志变化的选项
- -t --timestamps=true | false 默认为false 在返回的日志结果上加上时间戳的选项
- --tail="all" 返回结尾多少数量的日志 默认为所有日志

`docker top [NAME/ID]`
- 查看容器内进程状态

#### 设置容器的端口映射

`-p --publish=[]`
- containerPort
	docker run -p 80 -i -t ubuntu /bin/bash
- hostPort:containerPort
	docker run -p 8080:80 -i -t ubuntu /bin/bash
- ip::containerPort
	docker run -p 0.0.0.0:80 -i -t ubuntu /bin/bash
- ip:hostPort:containerPort
	docker run -p 0.0.0.0:8080:80 -i -t ubuntu /bin/bash

## 守护式容器

#### 守护式容器
- 能够长期运行
- 没有交互式会话
- 适合运行应用程序和服务

#### 运行守护式容器

1.
	- docker run -i -t IMAGE /bin/bash
	- Ctrl+P Ctrl+Q
	- 退出运行在交互模式下的容器 让容器在后台运行

2.
	- docker attach [NAME/ID]
	- 进入正在运行中的容器的交互模式

3. 
	- docker run -d IMAGE [COMMAND] [ARG..]
	- 启动守护式容器

4. 
	- docker exec [-d] [-i] [-t] [NAME/ID] [COMMAND] [ARG..]
	- 在运行中的容器内启动新的进程

#### 停止守护式容器
1. 
	- docker stop [ID/NAME]
	- 向容器发送停止运行的信号 等容器停止后返回容器的唯一标识

2. 
	- docker kill [ID/NAME]
	- 立即停止正在运行中的容器


