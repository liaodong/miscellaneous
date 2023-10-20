# Docker 安装 redis cluster 3主3从服务器 单机

# 1、创建redis配置文件
## 在home 目录下创建 集群配置文件加
mkdir -p /docker/redisContainer/redis-cluster 
## 在创建目录中
cd /docker/redisContainer/redis-cluster 
## 创建模版件
vim redis-cluster.tmpl 

    #redis docker 集群  
    创建配置文件模版 redis-cluster.tmpl  
    ##节点端口  
    port ${PORT}  
	##cluster集群模式  
	cluster-enabled yes  
	##集群配置名  
	cluster-config-file nodes.conf  
	##超时时间  
	cluster-node-timeout 5000  
	##实际为各节点网卡分配ip 先用上网关ip代替  
	cluster-announce-ip 172.18.0.1  
	##节点映射端口  
	cluster-announce-port ${PORT}  
	##节点总线端  
	cluster-announce-bus-port 1${PORT}  
	##持久化模式  
	appendonly yes  
## 创建redis实例7000-7005配置文件  
	for port in `seq 7000 7005`; do \
	mkdir -p ./${port}/conf \
	&& PORT=${port} envsubst < ./redis-cluster.tmpl > ./${port}/conf/redis.conf \
	&& mkdir -p ./${port}/data; \
	done
# 2、创建redis容器
	for port in `seq 7000 7005`; do \
	docker run -d -ti -p ${port}:${port} -p 1${port}:1${port} \
	-v /docker/redisContainer/redis-cluster/${port}/conf/redis.conf:/usr/local/etc/redis/redis.conf:rw \
	-v /docker/redisContainer/redis-cluster/${port}/data:/data:rw \
	--restart always --name redis-${port}  \
	--sysctl net.core.somaxconn=1024 redis:5.0 redis-server /usr/local/etc/redis/redis.conf; \
	done
#注释：循环7000到7005创建以redis-7000 redis-7001 redis-7002 redis-7003 redis-7004 redis-7005的容器并运行
# 3、修改各个redis.conf配置cluster-announce-ip （对外IP） 
	##实际为各节点网卡分配ip 先用上网关ip代替  
	cluster-announce-ip 172.18.0.1
# 4、重启各个redis
	docker restart redis-7000 redis-7001 redis-7002 redis-7003 redis-7004 redis-7005
# 5、创建集群
	docker exec -it redis-7000 redis-cli --cluster create 172.28.22.165:7000 172.28.22.165:7001 172.28.22.165:7002 172.28.22.165:7003 172.28.22.165:7004 172.28.22.165:7005 --cluster-replicas 1

集群创建过程中 输入 “yes”
