# UML图简介
统一建模语言（UML，Unified Modeling Language）是一种开放的方法，用于说明、可视化、构建和编写一个正在开发的、面向对象的、软件密集系统的制品的开放方法。
UML 2.0共有10种图:

>- 表示系统静态结构的静态模型（包括类图、组合结构图、部署图）;
>- 表示系统动态结构的动态模型（包括用例图、序列图、对象图、协作图、状态图、活动图、组件图）

##UML中的各个图的功能作用：

###用例图(Use Case Diagram)

>描述角色以及角色与用例之间的连接关系。说明的是谁要使用系统，以及他们使用该系统可以做些什么。一个用例图包含了多个模型元素，如系统、参与者和用例，并且显示了这些元素之间的各种关系，如泛化、关联和依赖。


> **用例图所包含的元素：

> 1.**参与者（Actor）**

> 用一个小人表示。表示与应用程序或系统进行交互的用户、组织或者外部系统。

>![usecase_actor](../../images/uml/usecase_actor.jpg)

> 2.**用例（Use Case）**

>用椭圆表示。指外部可见的一个系统功能单元，用于对系统提供的服务进行描述。

>![usecase_usecase](../../images/uml/usecase_usecase.jpg)
> 3.**子系统（Subsystem）**

>用于展示系统的一部分功能。

>![usecase_subsystem](../../images/uml/usecase_subsystem.jpg)
> 4.**关系**

>关系类型有：关联、泛化、包含和扩展。

>| 关系类型 | 含义  | 符号表示 |
|:------------- |:---------------:| -------------: |
| 关联  | 参与者与用例之间的通信（消息发送方指向接收方）     | ![usecase_line_1](../../images/uml/usecase_line_1.jpg)  |
| 泛化  | 参与者间或用例间的继承关系（子指向父               | ![usecase_line_2](../../images/uml/usecase_line_2.jpg)  |
| 包含  | 用于将用例功能分解成较小的功能（指向分解出来的用例 | ![usecase_line_3](../../images/uml/usecase_line_3.jpg)  |
| 扩展  | 用例功能的延伸（指向扩展用例）                     | ![usecase_line_4](../../images/uml/usecase_line_4.jpg)  |


###类图（Class Diagram）

>类图是描述系统中的类，以及各个类之间的关系的静态视图。能够让我们在正确编写代码以前对系统有一个全面的认识。类图是一种模型类型，确切的说，是一种静态模型类型。类图表示类、接口和它们之间的协作关系。
>**类图的结构**

>![class_class](../../images/uml/class_class.jpg)

>类一般由三部分组成：

>- 类名：每个类都必须有一个名字，类名是一个字符串。
>- 类的属性：类的成员变量。一个类属性个数大于等于零。
>表示方法为：

>```
>可见性  名称:类型 [ = 缺省值 ]
>```
>**a.** “可见性”包括公有(public)、私有(private)和受保护(protected)三种，在类图中分别用符 号+、-和#表示。表示属性对于类外的元素是否可见。
>**b.** “名称”用一个字符串表示属性名。
>**c.** “类型”可以是基本数据类型，也可以是用户自定义类型,表示属性的数据类型。
>**d.** “缺省值”为可选项，即属性的初始值。

>- 类的操作：类的任意一个实例对象都可使用的类的成员方法。表示方法：

>```
>可见性  名称(参数列表) [ : 返回类型]
>```
>**a.**“可见性”的定义同属性。
>**b.**“名称”用字符串表示。
>**c.**“参数列表”表示方法的参数，其语法与属性的定义相似，参数个数是任意的，多个参数之间用逗号“，”隔开。
>**d.**“返回类型”是一个可选项，表示方法的返回值类型，依赖于具体的编程语言，可以是基本数据类型，也可以是用户自定义类型，还可以是空类型(void)，如果是构造方法，则无返回类型。

------------------
#### 类的六大关系

1.依赖(Dependency)

>对象之间最弱的一种关联方式，是临时性的关联。代码中一般指由局部变量、函数参数、返回值建立的对于其他对象的调用关系（使用与被使用关系，例如动物和氧气的依赖关系）。在类图使用带箭头的虚线表示，箭头从使用类指向被依赖的类。

2.关联（Association）
>管理关系一般是一个类知道另一个类的属性和方法，通常含有“知道”、“了解”的含义，这种关系比依赖更强，不存在依赖关系的偶然性、关系也不是临时性的，一般是长期性的，而且双方的关系一般是平等的。比如说：“渔民”需要知道“天气”的好坏来决定是否出海打鱼
对象之间一种引用关系，比如客户类与订单类之间的关系(通常含有“知道”、“了解”的含义)。在类图使用带箭头的实线表示，箭头从使用类指向被关联的类。可以是单向和双向。

3.继承（泛化, Generalization）

>子类与父类的关系(is-a关系），子类可以继承父类的属性或者方法，而其自身可以扩展其他的属性和方法。比如说：水星和火星都属于行星。在类图中使用带三角箭头的实线表示，箭头从子类指向父类。

4.实现（Realization）

>指定了两个实体之间的一份合同；即：一个实体定义一份合同，另外一个实体则保证履行该合同；比如：机房收费系统中管理员可以进行日、周账单的报表。类图中使用带三角箭头的虚线表示，箭头从实现类指向接口。

5.聚合（Aggregation）

>是关联关系中的一种，体现的是整体与部分的拥有关系，“has-a”关系，部分可以脱离整体而单独存在，如公司和员工的关系，公司包含员工，但如果公司倒闭，员工依然可以换公司。在类图使用空心的菱形表示，菱形从局部指向整体。

6.组合（Composition）

>关联关系的一种，但它是比聚合关系更强的关系，“contain-a”关系，同样体现的是整体和部分的关系，只不过此时的整体和部分是不可分离的，比如：人和大脑。


###序列图（Sequence Diagram）
>序列图是用来显示你的参与者如何以一系列顺序的步骤与系统的对象交互的模型。顺序图可以用来展示对象之间是如何进行交互的。顺序图将显示的重点放在消息序列上，即强调消息是如何在对象之间被发送和接收的。

>**时序图组成元素**

>1.对象(Object)

>- 时序图中的对象在交互中扮演的角色就是对象;
>- 对象的符号 : 时序图中的对象与对象图中的表示方法一样, 使用矩形将对象名称包含起来, 并且对象名称下有下划线;
>- 对象创建时机 : 对象可以在交互开始的时候创建, 也可以在交互过程中进行创建;
>- -- 处于顶部 : 如果对象的位置在时序图顶部, 说明在交互开始的时候对象就已经存在了;
>- -- 不在顶部 : 如果对象的位置不在顶部, 那么对象在交互过程中创建的;


>![sequence_1](../../images/uml/sequence_1.jpg)
>2.生命线(Lifeline)

>- 生命线 : 生命线是一条垂直的虚线, 这条虚线表示对象的存在, 在时序图中, 每个对象的底部都有生命线;
>- 生命线作用 : 生命线是一个时间线, 从时序图顶部一直到底部都存在, 其长度取决于交互的时间;
>- 对象的生命线 : 对象与生命线结合在一起就是对象的生命线, 这个概念包含对象图标 以及 对象下面的生命线图标 如上图;


>3.激活(Activation)

>- 激活(Activation) : 代表时序图中对象执行一项操作的时期, 激活期可以理解为语义中 {} 中的内容, 表示该对象被占用以完成某个任务;
>- 去激活(Deactivation) : 指对象处于空闲状态, 在等待消息激活这个对象;

>- 激活的表示 : 当对象处于激活时期, 生命线可以拓宽为矩形, 这个矩形条成为激活条;

>- 激活去激活的时机 :
>- -- 激活 : 对象激活是在激活条的顶部激活;
>- -- 去激活 : 激活条的底部去激活, 通常发生在一个消息离开对象生命线;

>![sequence_2](../../images/uml/sequence_2.jpg)

>4.消息(Message)

>- 消息概念 : 定义 交互 和 协作 中 交换信息 的类, 对 对象之间的 通信内容 建模;

>- 消息动作 :
>- -- 动作种类 : 消息允许在实体间传递信息 (传递参数), 允许实体请求其它服务, 对象之间通过 发送 和 接收 消息 进行通信;
>- -- 产生结果 : 消息可以触发操作, 唤起信号, 或使目标对象创建 或 销毁;

>- 消息的异步和同步通信 :
>- -- 异步通信 : 消息是信号的时候, 发送信号之后, 等待对方触发相应方法, 这是明确的 命名的 对象间的异步通信;
>- -- 同步通信 : 直接调用对象的方法, 执行方法返回结果, 这种具有返回控制机制的操作是同步通信;
>- 时序图和协作图中消息的区别 : 时序图中的消息强调顺序, 协作图中的消息强调交换消息的对象间的关系;
>- 消息类型 :
>- -- ![sequence_line_1](../../images/uml/sequence_line_1.jpg)  : 两个对象间绘制消息;
>- -- ![sequence_line_2](../../images/uml/sequence_line_2.jpg)  : 两个对象之间的过程调用;
>- -- ![sequence_line_3](../../images/uml/sequence_line_3.jpg)  : 两个对象之间的异步消息;
>- -- ![sequence_line_4](../../images/uml/sequence_line_4.jpg)  : 过程调用中返回的消息;
>- -- ![sequence_line_5](../../images/uml/sequence_line_5.jpg)  : 绘制反身消息;

###对象图（Object Diagram）

>与类图极为相似，它是类图的实例，对象图显示类的多个对象实例，而不是实际的类。它描述的不是类之间的关系，而是对象之间的关系。

###包图（Package Diagram）
>包图用于描述系统的分层结构，由包或类组成，表示包与包之间的关系。

###活动图（Activity Diagram）
>描述用例要求所要进行的活动，以及活动间的约束关系，有利于识别并行活动。能够演示出系统中哪些地方存在功能，以及这些功能和系统中其他组件的功能如何共同满足前面使用用例图建模的商务需求。

###状态图（State Machine Diagram）
>描述类的对象所有可能的状态，以及事件发生时状态的转移条件。可以捕获对象、子系统和系统的生命周期。他们可以告知一个对象可以拥有的状态，并且事件(如消息的接收、时间的流逝、错误、条件变为真等)会怎么随着时间的推移来影响这些状态。一个状态图应该连接到所有具有清晰的可标识状态和复杂行为的类；该图可以确定类的行为，以及该行为如何根据当前的状态变化，也可以展示哪些事件将会改变类的对象的状态。状态图是对类图的补充。

###协作图（Collaboration Diagram)
>和序列图相似，显示对象间的动态合作关系。可以看成是类图和顺序图的交集，协作图建模对象或者角色，以及它们彼此之间是如何通信的。如果强调时间和顺序，则使用序列图；如果强调上下级关系，则选择协作图；这两种图合称为交互图。

###构件图(Component Diagram)
>描述代码构件的物理结构以及各种构建之间的依赖关系。用来建模软件的组件及其相互之间的关系，这些图由构件标记符和构件之间的关系构成。在组件图中，构件是软件单个组成部分，它可以是一个文件，产品、可执行文件和脚本等。

###部署图(Deployment Diagram)

>是用来建模系统的物理部署。例如计算机和设备，以及它们之间是如何连接的。部署图的使用者是开发人员、系统集成人员和测试人员。部署图用于表示一组物理结点的集合及结点间的相互关系，从而建立了系统物理层面的模型。

一：这十种模型图各有侧重，

1. 用例图侧重描述用户需求，
2. 类图侧重描述系统具体实现；

二：描述的方面都不相同
```
1. 类图描述的是系统的结构;
2. 序列图描述的是系统的行为；
```
三：抽象的层次也不同，
```
1. 构件图描述系统的模块结构，抽象层次较高;
2. 类图是描述具体模块的结构，抽象层次一般;
3. 对象图描述了具体的模块实现，抽象层次较低。
```