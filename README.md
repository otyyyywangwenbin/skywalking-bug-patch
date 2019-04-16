### 补丁代码
补丁代码来自于 https://github.com/apache/incubator-skywalking/commit/93aeb4970da3f6f7492b0ade69455ba296466c15

### 打补丁
1. 将项目目录下的collector-libs的jar 复制到 skywalking的collector-libs目录下

> collector-libs目录下的`*.original`是未修改的skywalking5.0.0-GA的jar     

>  也可以自己重新编译源码 `mvn clean pakcage`, 将编译后的01-skywalking-patch-1970-1.0.0-SNAPSHOT.jar 复制到 skywalking的collector-libs目录下

### 校验
启动skywalking, 查看logs/skywalking-collector-server.log, 可以看到
```
2019-04-15 02:02:39,742 - org.apache.skywalking.apm.collector.analysis.segment.parser.provider.buffer.SegmentBufferManager -6973 [main] INFO  [] - ==========> SegmentBufferManager patch 1970
2019-04-15 02:02:39,742 - org.apache.skywalking.apm.collector.analysis.segment.parser.provider.buffer.SegmentBufferManager -6973 [main] INFO  [] - segment buffer initialize
2019-04-15 02:02:39,743 - org.apache.skywalking.apm.collector.analysis.segment.parser.provider.buffer.OffsetManager -6974 [main] INFO  [] - ==========> OffsetManager patch 1970
2019-04-15 02:02:39,745 - org.apache.skywalking.apm.collector.core.util.FileUtils -6976 [main] INFO  [] - ==========> FileUtils patch 1970
```
说明生效

