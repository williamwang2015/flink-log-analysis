# flink-log-analysis
## 项目架构图
从0到1基于Flink实现一个实时的用户行为日志分析系统，基本架构图如下：

![](https://github.com/jiamx/flink-log-analysis/blob/master/%E6%97%A5%E5%BF%97%E6%9E%B6%E6%9E%84.png)

## 代码结构



首先会先搭建一个论坛平台，对论坛平台产生的用户点击日志进行分析。然后使用Flume日志收集系统对产生的Apache日志进行收集，并将其推送到Kafka。接着我们使用Flink对日志进行实时分析处理，将处理之后的结果写入MySQL供前端应用可视化展示。本文主要实现以下三个指标计算：

- 统计热门板块，即访问量最高的板块
- 统计热门文章，即访问量最高的帖子文章
- 统计不同客户端对版块和文章的总访问量
