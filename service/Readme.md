## service 
### docker 常用命令
- docker swarm init
- docker stack deploy -c docker-compose.yml stackName 运行单个服务堆栈
- docker service  显示运行的服务
- docker stack services stackName
- docker service ps stackName
- docker stack rm stackName 终止app
- docker swarm leave --force 移除swarm 