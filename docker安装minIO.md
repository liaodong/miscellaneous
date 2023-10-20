# docker 安装minio服务
- 1、MinIO 是在 Apache License v2.0 下发布的对象存储服务器。 它与 Amazon S3 云存储服务兼容。 它最适合存储非结构化数据，如照片，视频，日志文件，备份和容器/ VM 映像。 对象的大小可以从几 KB 到最大 5TB。
- 2、MinIO 服务器足够轻，可以与应用程序堆栈捆绑在一起，类似于 NodeJS，Redis 和 MySQL
- 3 一种高性能的分布式对象存储服务器，用于大型数据基础设施。它是机器学习和其他大数据工作负载下Hadoop HDFS 的理想 s3 兼容替代品
## 1、拉取docker镜像
	docker pull minio/minio
## 2、启动与安装镜像
	docker run -it -p 9000:9000 -p 9090:9090  --name minio -e "MINIO_ROOT_USER=admin" -e "MINIO_ROOT_PASSWORD=Techown1" -d minio/minio server /data  --console-address ":9000" --address ":9090"
9000 console端口  
9090 api端口  
MINIO_ROOT_USER  管理台账号  
MINIO_ROOT_PASSWORD 管理台密码  
/data  数据存储目录  
## 3、浏览器登录
	http://192.168.100:9000
