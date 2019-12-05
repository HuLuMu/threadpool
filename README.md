# threadpool

## 功能介绍

1. 线程池在执行任务过程中，如何抛出了运行时异常，能不能再次执行该任务？
任务失败可重试
2. 如何统计任务的排队时间、执行时间？如何记录一个任务的处理时间。任务的处理时间等于排队时间加上处理时间
3. 线程池参数如何配置才合理？
    - core pool size 小于 max pool size时，需要等到任务队列满时，才会创建工作线程数到 max pool size。能不能优先创建工作线程数到max pool size后，再有任务提交过来排队入队列？
    - 线程池任务队列的长度设置成多大合适？统计任务的执行时间、设置任务响应时间，应用利特尔法则计算出合理的任务队列长度，然后动态调整任务的队列长度。
    - 
4. 支持优先级任务队列。
5. 更灵活的任务拒绝策略。如果采用有界的LinkedBlockingQueue，任务队列满时会导致任务拒绝；若采用无界队列LinkedTransferQueue，任务一直堆积又导致内存OOM或者不能及时处理任务。那么，能不能为任务定义一个属性(force execution)，强制执行的任务一定能入队列成功从而不会被拒绝？


## How To
mvn install 到本地仓库,然后项目中导入依赖即可
```html
    <dependency>
      <groupId>com.yy.textml.threadpool</groupId>
      <artifactId>threadpool-spring-boot-starter</artifactId>
      <version>1.0.0-SNAPSHOT</version>
    </dependency>
```

## Reference
ElasticSearch 6.x 线程池模块