# 简介
这是一个分布式全栈即时通信系统服务端，实现了 注册、登录、重置密码、好友查找、好友添加、聊天等功能
服务端采用分布式设计，解耦各项服务，通过grpc实现服务间通信；采用docker技术容器化各项服务，消除环境兼容性问题，提升服务部署一致性；采用多CMakeLists.txt分层设计，实现代码层面的低耦合，利于后期扩展
技术栈：C++、Qt、CMake、Docker、Mysql、Redis、Git、多线程、网络编程、Asio、gRPC

# 快速开始
1. git clone git@github.com:diablorrr/server.git
2. git submodule update --init --recursive
3. 分别进入各个文件夹（GateServer、StatusServer、ChatServer、VarifyServer）构建docker镜像：docker build --network host --build-arg http_proxy=<代理的IP端口> https_proxy=<代理的IP端口>  -t <镜像名> .
4. 运行docker容器：docker run -d -name <容器名> -p <宿主机端口:容器端口> -v <宿主机路径:容器路径> <镜像名:版本号>
   注意：需要使用同一个ChatServer镜像创建两个ChatServer容器，通过 -v <宿主机路径:容器路径> 加载各自配置文件（配置文件在config文件夹中）；StatusServer、VarifyServer不需要使用 -p <宿主机端口:容器端口> 做端口映射，因为它们无需和外部交互
5. 进入 server文件夹，使用 docker-compose 一键启动：docker-compose up -d


# TODO
- [ ] 整理上传 分布式聊天项目客户端代码
