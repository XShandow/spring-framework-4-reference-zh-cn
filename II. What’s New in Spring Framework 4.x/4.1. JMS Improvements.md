## 4.1JMSImprovements

Spring 4.1 introduces a much simpler infrastructure[to register JMS listener endpoints](https://docs.spring.io/spring/docs/current/spring-framework-reference/htmlsingle/#jms-annotated)by annotating bean methods with[`@JmsListener`](http://docs.spring.io/spring-framework/docs/4.3.11.RELEASE/javadoc-api/org/springframework/jms/annotation/JmsListener.html). The XML namespace has been enhanced to support this new style \(`jms:annotation-driven`\), and it is also possible to fully configure the infrastructure using Java config \([`@EnableJms`](http://docs.spring.io/spring-framework/docs/4.3.11.RELEASE/javadoc-api/org/springframework/jms/annotation/EnableJms.html),`JmsListenerContainerFactory`\). It is also possible to register listener endpoints programmatically using[`JmsListenerConfigurer`](http://docs.spring.io/spring-framework/docs/4.3.11.RELEASE/javadoc-api/org/springframework/jms/annotation/JmsListenerConfigurer.html).  
Spring 4.1 引入了一个更简单的基础架构，使用 @JmsListener注解bean 方法来注册 JMS 监听端点。XML 命名空间已经通过增强来支持这种新的方式（jms:annotation-driven），它也可以完全通过Java配置\( @EnableJms, JmsListenerContainerFactory\)来配置架构。也可以使用 JmsListenerConfigurer注解来注册监听端点。

Spring 4.1 also aligns its JMS support to allow you to benefit from the`spring-messaging`abstraction introduced in 4.0, that is:  
Spring 4.1 还调整了 JMS 的支持，使得你可以从spring-messaging在 Spring4.0 引入的抽象获益，即：

* Message listener endpoints can have a more flexible signature and benefit from standard messaging annotations such as
  `@Payload`,`@Header`,`@Headers`, and`@SendTo`. It is also possible to use a standard`Message`in lieu of`javax.jms.Message`as method argument.
* 消息监听端点可以有更为灵活的签名，并且可以从标准的消息注解获益，例如@Payload、@Header、@Headers和@SendTo注解。另外，也可以使用一个标准的消息，以代替javax.jms.Message作为方法参数。
* A new[`JmsMessageOperations`](http://docs.spring.io/spring-framework/docs/4.3.11.RELEASE/javadoc-api/org/springframework/jms/core/JmsMessageOperations.html)interface is available and permits`JmsTemplate`like operations using the`Message`abstraction.
* 一个新的可用 JmsMessageOperations接口和允许操作使用Message抽象的JmsTemplate。

Finally, Spring 4.1 provides additional miscellaneous improvements:  
最后，Spring 4.1提供了其他各种各样的改进：

* Synchronous request-reply operations support in`JmsTemplate`
* JmsTemplate中的同步请求-答复操作支持
* Listener priority can be specified per`<jms:listener/>`element
* 监听器的优先权可以指定每个元素
* Recovery options for the message listener container are configurable using a[`BackOff`](http://docs.spring.io/spring-framework/docs/4.3.11.RELEASE/javadoc-api/org/springframework/util/backoff/BackOff.html)implementation
* 消息侦听器容器恢复选项可以通过使用 BackOff 实现进行配置
* JMS 2.0 shared consumers are supported
* JMS 2.0消费者支持共享



