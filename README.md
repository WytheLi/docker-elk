### 服务器准备
- s0: 192.168.3.125
- s1: 192.168.3.235

### 服务分布
s0: Filebeat、 Logstash、 Elasticsearch、 Kibana
s1: Filebeat

### Swarm集群管理工具
1、在s0服务器开始Swarm服务（主服务）
```shell
docker swarm init
```
> 保存加入集群的命令`docker swarm join --token SWMTKN-1-5fvug4drzimvwe6bhdn7duukp5147v4u8jyolcaucfqzvz3qmo-6mqhbj2wslwomcq0a44v71gdy 192.168.3.125:2377`

2、查看集群节点（主服务才能查看）
```shell
docker node ls
```

3、在s1执行加入集群命令
```shell
docker swarm join --token SWMTKN-1-5fvug4drzimvwe6bhdn7duukp5147v4u8jyolcaucfqzvz3qmo-6mqhbj2wslwomcq0a44v71gdy 192.168.3.125:2377
```

### 参考文档
- [ELK集群搭建系列教程——docker-compose一键式搭建](https://blog.csdn.net/yprufeng/article/details/115718441)
- [docker-compose撰写规范](https://docs.docker.com/compose/compose-file/)
