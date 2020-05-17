#### Spring中Bean是指什么

> 被Spring IOC容器初始化的Java对象。

#### Spring中Bean有哪几种作用域

> <https://docs.spring.io/spring/docs/5.3.0-SNAPSHOT/spring-framework-reference/core.html#beans-factory-scopes>

1. Singleton：意味着在Spring容器中只会有一个Bean实例被创建。任何对同名对象的请求和修改都会反应到唯一的实例上。默认的Bean作用域。
2. Prototype：每次调用都会产生一个新的实例。
3. Request：每次请求产生一个bean，在同一次请求中多次获取的bean是相同的。
4. Session：Session共享的Bean实例。
5. Application：Servlet共享的Bean实例。
6. Websocket：Websocket共享的Bean实例。

#### 如何定义Bean的Scope

`@Scope(value = "singleton")`

#### Singleton的Bean是线程安全的吗

> No, singleton beans are not thread-safe, as thread safety is about execution, whereas the singleton is a design pattern focusing on creation. Thread safety depends only on the bean implementation itself
