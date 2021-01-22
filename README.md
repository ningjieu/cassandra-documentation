# cassandra-documentation
documentation

#开始
对新手友好的出发点
1.安装

2.配置

配置文件位置和安装方式相关:

tarball: 配置文件目录再tarball方式的安装位置
package: 配置文件目录为：/etc/cassandra
默认配置文件：cassandra.yaml,已经可以满足探索如何使用简单的单节点集群。然而，要做其他更多事情需要对更多配置。有些例子就需要非默认的配置，比如部署多节点集群，或者使用不在集群节点上运行的客户端。

cassandra.yaml: 主要的配置文件
cassandra-env.sh: 环境变量
cassandra-rackdc.properties OR cassandra-topology.properties: 设置rack和datacenter信息
logback.xml: 日志配置
jvm-*: 和服务端和客户端相关的一组配置文件
commitlog_archiving.properties: 为commitlog设置归档参数
两个样例配置文件位于目录./conf:

metrics-reporter-config-sample.yaml: 配置metrics-report收集的内容
cqlshrc.sample: how the CQL shell, cqlsh, can be configured
如要运行属性
再cassandra.yaml中配置yaml properties。 至少配置如下属性:

cluster_name: 集群名称。
seeds: 逗号分隔的ip地址种子节点。
storage_port: 检查7000端口未被防火墙拦截。
listen_address: listen address为一个节点的ip地址，允许它和集群的其它节点通信。默认为localhost。可以设置listen_interface让Cassandra知道使用那个接口，使用哪个地址。只设置两者中的一个，不要全部设置。
native_transport_port:  检查9042端口未被防火墙拦截, 以便客户端可以访问.
改变相关目录
以下yaml properties控制目录的位置:

data_file_directories:一个或多个目录，数据文件如SSTables的位置.
commitlog_directory: commitlog files位置.
saved_caches_directory: saved caches位置.
hints_directory: hints位置.
为了性能考虑, 如果有多磁盘, 考虑把commitlog和data放在不同磁盘.

环境变量
JVM级参数如heap size可以配置在cassandra-env.sh. 任何附加的JVM命令行参数可以放在JVM_OPTS变量;Cassandra启动时，会传递给JVM.

日志
默认logback.记录如下:

INFO level in system.log
DEBUG level in debug.log
When running in the foreground, it will also log at INFO level to the console. You can change logging properties by editing logback.xml or by running the nodetool setlogginglevel command.

#操作
操作者的港湾

#架构
架构总览

#工具
cqlsh, nodetool, ...

#数据模型
非关系型

#定位问题
疑难问题手册

#CQL
CQL参考文档

#开发
如何提升及打补丁

#常见问题
问题手册(有答案!)

#配置
配置
