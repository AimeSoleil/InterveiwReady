#### 面向对象的特征有哪些方面?

> **封装(Encapsulation)：** 对象的属性和行为的代码封装在类中，属性用变量定义，行为用方法进行定义，方法可以直接访问同一个对象中的属性。实现持续内部的`高内聚，低耦合`。
> **继承(Inheritance)：** 指从已有的类中派生出若干个新类，是子类自动共享父类之间数据和方法的机制。
> **多态(Polymorphisn)：** 多态是指程序中定义的引用变量所指向的具体类型和通过该引用变量发出的方法调用在编程时并不确定，而是在程序运行期间才确定。增加了程序的灵活性和扩展性。
> **抽象(Abstract)：** 抽象是将一类对象的共同特征总结出来构造类的过程，包括数据抽象和行为抽象两方面。抽象只关注对象有哪些属性和行为，并不关注这些行为的细节是什么。

#### 面向对象有哪些限制？

> 通常不适用于解决小问题
> 需要紧密和大量的测试
> 需要更多的时间
> 实现前需要合适的计划
> 开发者需要一直思考如何从对象的角度去解决问题

#### 实现多态(Polymorphisn)的方式

> Java提供了编译时多态(静态绑定)和运行时多态(动态绑定)两种多态机制。前者是通过方法**重载**(overload)实现的，后者是通过方法的**覆盖**(override)实现的。

#### What is the meaning of “IS-A” and “HAS-A” relationship?

> **IS-A** relationship implies inheritance. A sub class object is said to have “IS-A” relationship with the super class or interface. If class A extends B then A “IS-A” B. It is transitive, that is, if class A extends B and class B extends C then A “IS-A” C. The “instanceof” operator in java determines the “IS-A” relationship.
> **HAS-A** When a class A has a member reference variable of type B then A “HAS-A” B. It is also known as Aggregation.

#### What is Association?

> **Association** is a relationship between two objects with multiplicity.

#### What is Aggregation?

> **Aggregation** is also known as “HAS-A” relationship. When class Car has a member reference variable of type Wheel then the relationship between the classes Car and Wheel is known as Aggregation. Aggregation can be understood as “whole to its parts” relationship.
> Car is the whole and Wheel is part. Wheel can exist without the Car. Aggregation is a weak association.

#### What is Composition?

> **Composition** is a special form of Aggregation where the part cannot exist without the whole. Composition is a strong Association. Composition relationship is represented like aggregation with one difference that the diamond shape is filled.

#### What is Dependency?

> When one class depends on another because it uses that at some point in time then this relationship is known as Dependency. One class depends on another if the independent class is a parameter variable or local variable of a method of the dependent class. A Dependency is drawn as a dotted line from the dependent class to the independent class with an open arrowhead pointing to the independent class.

#### What is the difference between Association and Dependency?

> The main difference between Association and Dependency is in case of Association one class has an attribute or member variable of the other class type but in case of Dependency a method takes an argument of the other class type or a method has a local variable of the other class type.

#### 接口与抽象类的区别

> 从**概念上来说**，抽象类是对整个类整体进行抽象，包括属性、行为，但是接口却是对类局部（行为）进行抽象。
> 从**设计的角度**来说，抽象类是一种模板式的设计；而接口是是一种行为规范。

#### 构造方法可否被重写?

> 构造方法不能被继承，因此不能重写，但能被重载。