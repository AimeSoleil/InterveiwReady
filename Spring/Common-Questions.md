
#### Setter injection versus constructor injection and the use of @Required

> <https://spring.io/blog/2007/07/11/setter-injection-versus-constructor-injection-and-the-use-of-required/>

##### 为什么更多人使用Setter注入而不是构造器注入？

1. 历史原因。在2003年，Spring第一次作为开源项目发布的时候，主要聚焦在Setter注入。原因在于，那时的开发团队认为Java中构造器不支持默认参数，同时不支持显式的参数名，会给开发者带来不清晰的语义。另外，由于Spring框架早起本身也使用Setter注入，导致很多第三方的应用，博客和文章也一直在提到Setter注入。
2. Spring框架是高度可配置的(Frameworks need to be a lot more configurable)。意味着这些配置都会包含很多Optional的字段，如果用构造器注入，会导致混乱和拥挤的构造器

基于上面的两个原因，构造器注入更适用于应用层，Setter注入更适用与框架层。因为在应用层，Optional的参数通常比较少，也不需要大量的配置。

##### 选择

> We usually advise people to use constructor injection for all mandatory collaborators and setter injection for all other properties.

> Or alternative, using the alternative mechanisms if you perfer setter injection
```Java
public class Service {

  private Collaborator collaborator;

  @Required
  public void setCollaborator(Collaborator c) {
    this.collaborator = c;
  }
}
```
> Or alternative, utilize the bean lifecycle,
```Java
public class Service implements InitializingBean {

  private Collaborator collaborator;

  public void setCollaborator(Collaborator c) {
    this.collaborator = c;
  }

  // from the InitializingBean interface
  public void afterPropertiesSet() {
    if (collaborator == null) {
      throw new IllegalStateException("Collaborator must be set in order for service to work");
    }
  }
}
```
