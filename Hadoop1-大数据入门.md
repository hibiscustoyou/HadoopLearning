# 大数据概论

## 大数据部门组织结构

1. 平台组
   + 搭建 Hadoop、Flume、Kafka、HBase、Spark 等框架平台
   + 集群性能监控
   + 集群性能调优
2. 数据仓库组
   + ETL 工程师：数据清洗
   + Hive 工程师：数据分析、数据仓库建模
3. 数据挖掘组
   + 算法工程师
   + 推荐系统工程师
   + 用户画像工程师
4. 报表开发组
   + JavaEE 工程师

# 从 Hadoop 框架讨论大数据生态

## 1. Hadoop 是什么

Hadoop：

1. 由 Apache 开发的分布式系统基础架构
2. 主要解决海量数据存储和海量数据的分析计算问题
3. Hadoop 通常指的是 Hadoop 生态圈

## 2. Hadoop 思想：

Google 在大数据方面的三篇论文：

+ GFS => HDFS：解决一般存储问题
+ MapReduce => MR：解决一般计算问题
+ BigTable => HBase：解决一般表示问题

## 3. Hadoop 组成

+ MapReduce => 数据计算
+ Yarn =>资源调度
+ HDFS =>数据存储

1. HDFS 架构

   | 节点                      | 描述                                                         |
   | ------------------------- | ------------------------------------------------------------ |
   | NameNodes（nn）           | 存储文件元数据（文件名、文件目录结构，文件属性）以及每个文件的块列表和块所在的 DataNodes 等。（存放文件数据索引） |
   | DataNodes（dn）           | 在本地文件系统存储文件块数据和块数据的校验和                 |
   | Secondary NameNode（2nn） | 监控 HDFS 状态的辅助后台程序，每隔一段时间获取 HDFS 元数据的快照 |

2. Yarn 架构

   ![Yarn 架构](D:\workshop\Hadoop\HadoopLearning\Hadoop1-大数据入门.assets\image-20200408225551389.png)

   **（1）ResourceManager（RM）主要作用：**

   		+ 处理客户端请求
   		+  监控 NodeManager
   		+ 启动或监控 ApplicationMaster
   		+ 资源分配与调度

   **（2）NodeManager（NM）作用：**

   + 管理单节点上资源
   + 处理来自 RM 的命令
   + 处理来自 AM 的命令

   **（3）ApplicationMaster（AM）作用：**

   + 负责数据切分
   + 为应用程序申请资源并分配给内部的任务
   + 任务的监控与容错

   **Container 作用：**

   是 Yarn 中资源的抽象，封装了某个节点的多维度资源（内存、CPU、磁盘、网络等）

3. MapReduce 架构 => 分为 Map 和 Reduce 两个阶段

   ![MapReduce 架构](D:\workshop\Hadoop\HadoopLearning\Hadoop1-大数据入门.assets\image-20200408230749016.png)

   + Map：并行处理输入数据
   + Reduce：对 Map 结果进行汇总

## 大数据技术生态体系

![大数据生态体系](D:\workshop\Hadoop\HadoopLearning\Hadoop1-大数据入门.assets\image-20200408231039917.png)

