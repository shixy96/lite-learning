## 面向对象设计原则

### Single Responsibility Principle

**单一职责原则**，每一个类应该专注于做一件事情。



### Liskov Substitution Principle

**里氏替换原则**，超类存在的地方，子类是可以替换的。



### Dependence Inversion Principle

**依赖倒置原则**，实现尽量依赖抽象，不依赖具体实现（可能改变的类）

- 变量不可以持有具体类的引用
- 不要让类派生自具体类
- 不要覆盖基类中已实现的方法

（<u>针对接口编程，不针对实现编程</u>）。



### Interface Segregation Principle

**接口隔离原则**，应当为客户端提供尽可能小的单独的接口，而不是提供大的总的接口（封装变化）。



### Law Of Demeter

**最少知识原则**，一个软件实体应当尽可能少的与其他实体发生相互作用（<u>交互对象之间的松耦合</u>, Facade）。

- 该对象本身

- 被当作方法的参数而传递进来的对象

- 此方法所创建或实例化的任何对象

- 对象的任何组件（like HAS-A）

  

### Open Close Principle

**开闭原则**，面向扩展开放，面向修改关闭。(Decorator)



### Composite/Aggregate Reuse Principle CARP

**组合/聚合复用原则**，<u>尽量使用合成/聚合达到复用，尽量少用继承</u>。原则： 一个类中有另一个类的对象。



## 面向对象设计模式

### Observer

观察者模式定义了对象之间一对多依赖，这样一来，当一个对象改变状态时，它的所有依赖者都会收到通知并自动更新。

- 封装变化

  在观察者模式中，会改变的是主题的状态，以及观察者的数目和类型。用这个模式，可以改变依赖于主题状态的对象，却不必改变主题。

- 针对接口编程

  主题与观察者都使用接口，观察者利用主题的接口向主题注册，而主题利用观察者的接口通知观察者。

- 组合复用

  观察者模式利用“组合”将许多观察者组合进主题中。对象之间的这种关系不是通过继承产生的，而是在运行时利用组合的方式产生的。

### Decorator

装饰者模式动态地将责任附加到对象上。若要拓展功能，装饰者提供了比继承更有弹性的替代方案。

- 装饰者和被装饰者有相同的超类型，可以用装饰者代替被装饰者。
- 可以用一个或多个装饰者包装一个对象。
- 装饰者可以在所委托被装饰者的行为之前或之后，加上自己的行为，以达到特定的目的。

特点

- 封装变化
- 多用组合，少用继承
- 针对接口编程，不针对实现编程
- 交互对象之间松耦合
- 对拓展开放，对修改关闭
- 会导致设计中出现许多小对象，过度使用会让程序变得复杂

### Factory

工厂方法模式定义了一个创建对象的接口，但由子类决定要实例化的类是哪一个。工厂方法让类把实例化推迟到子类。（继承）

抽象工厂模式提供一个接口，用于创建相关或依赖对象的家族，而不需要明确指定具体类。（组合）

### Singleton

单件模式确保一个类只有一个实例，并提供一个全局访问点。（java实现需要私有构造器，一个静态方法和一个静态变量，注意多线程影响和避免多个classloader）

### Command

命令模式将“请求”封装成对象，以便使用不同的请求、队列或者日志来参数化其他对象。命令模式也支持可撤销的操作。

命令模式将发出请求的对象和执行请求的对象解耦；在被解耦的两者之间时通过命令对象进行沟通的，命令对象封装了接收者和一个或一组动作。宏命令是命令的一终简单的延申，允许调用多个命令（通过数组或者其他方式将命令组合）。

### Adapter & Facade

适配器模式将一个类的接口，转换成客户期望的另一个接口，适配器让原本接口不兼容的类可以合作无间。

外观模式提供了一个统一的接口，用来访问子系统中的一群接口，让子系统更容易使用。

