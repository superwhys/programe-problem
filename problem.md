##  一、Python导包问题

```python
import os
import sys

BASE_DIR = os.path.dirname(os.path.dirname(os.path.abspath(__file__)))
sys.path.append(BASE_DIR)
```



## 二、查看磁盘空间

### 查看磁盘空间大小的命令：df

df命令用于查看磁盘分区上的磁盘空间，包括使用了多少，还剩多少，默认单位是KB

比如以下命令：

```properties
df -hl
```

-l或*--local：仅显示本地端的文件系统；*

### 查看文件和目录大小的命令：du

1，比如要看/data目录的总大小，可以用以下命令：

```haskell
du -sh /data
```

2，如果要看/data目录下各个子目录的大小，不包括子目录的子目录，可以用以下命令：

```properties
du -sh *
```



## 三、查看端口号情况

netstat  -anp  |grep  端口号



## 四、kafka

```shell
# 查看某个group消费情况
kafka-consumer-groups.bat --bootstrap-server localhost:9092 --describe --group auto_commit_topic_group

# 查看某个topic的offset
kafka-run-class.bat kafka.tools.GetOffsetShell --broker-list localhost:9092 --topic auto_commit_topic --time -1

# 查看所有topic
kafka-topics.bat --list --zookeeper localhost:9092

# 查看某个topic的情况
kafka-topics.bat --zookeeper localhost:2181 --describe --topic auto_commit_topic
```

