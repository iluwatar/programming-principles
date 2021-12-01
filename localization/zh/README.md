# Programming Principles <!-- omit in toc -->

软件开发中有一些通用的法则和原则来指导架构师、程序员和任何需要设计软件的人。 这个页面列出了很多这些原则，虽然还远未完成。 这个页面 [programming-principles repository by Lars Kappert](https://github.com/webpro/programming-principles) 分叉而来, 他完成了收集材料的大部分工作。

## 目录 <!-- omit in toc -->

- [KISS](#kiss)
- [YAGNI](#yagni)
- [做可能有效的最简单的事情](#做可能有效的最简单的事情)
- [关注点分离](#关注点分离)
- [保持干燥](#保持干燥)
- [为维护者编码](#为维护者编码)
- [避免过早优化](#避免过早优化)
- [最小化耦合](#最小化耦合)
- [迪米特法则](#迪米特法则)
- [组合优于继承](#组合优于继承)
- [正交性](#正交性)
- [健壮性原则](#健壮性原则)
- [控制反转](#控制反转)
- [最大化凝聚力](#最大化凝聚力)
- [里氏替换原则](#里氏替换原则)
- [开闭原则](#开闭原则)
- [单一职责](#单一职责)
- [隐藏实现细节](#隐藏实现细节)
- [Curly定律](#Curly定律)
- [封装变化](#封装变化)
- [接口隔离](#接口隔离)
- [童子军规则](#童子军规则)
- [命令查询分离](#命令查询分离)
- [Murphy定律](#Murphy定律)
- [Brooks定律](#Brooks定律)
- [Linus定律](#Linus定律)

## KISS

大多数系统保持简单的时候效果最好而不是保持复杂。

原因

- 更少的代码需要更少的时间来编写，错误更少，并且更容易修改。
- 简单是终极的哲学。
- 似乎达到完美不是当没有什么可以添加的时候，而是当没有什么可以带走的时候。

参考资源

- [KISS principle](https://en.wikipedia.org/wiki/KISS_principle)
- [Keep It Simple Stupid (KISS)](http://principles-wiki.net/principles:keep_it_simple_stupid)

## YAGNI

YAGNI 代表 "you aren't gonna need it":除非有必要，否则不要实施某事。

- 在当前迭代中努力完成新功能

- 它导致代码膨胀； 软件变得更大更复杂。

如何达到

- 总是在你真正需要它们的时候实现它们，而不是在你预见到你需要它们的时候。

参考资源

- [You Arent Gonna Need It](http://c2.com/xp/YouArentGonnaNeedIt.html)
- [You’re NOT gonna need it!](https://ronjeffries.com/xprog/articles/practices/pracnotneed/)
- [You aren't gonna need it](https://en.wikipedia.org/wiki/You_aren%27t_gonna_need_it)

## 做可能有效的最简单的事情

做可能有效的最简单的事情

原因

- 如果我们只针对真正的问题进行研究，解决问题和实际进展的冲突就会最大化。

如何达到

- 问问自己：“最简单的可行方法是什么？”

参考资源

- [Do The Simplest Thing That Could Possibly Work](http://c2.com/xp/DoTheSimplestThingThatCouldPossiblyWork.html)

## 关注点分离

关注点分离是一种将计算机程序分成不同部分的设计原则，以便每个部分解决一个单独的关注点。 例如，应用程序的业务逻辑是一个关注点，而用户界面是另一个关注点。 更改用户界面不需要更改业务逻辑，反之亦然。

引用 [Edsger W. Dijkstra](https://en.wikipedia.org/wiki/Edsger_W._Dijkstra)
(1974):

> 这就是我有时所说的“关注点分离”，即使不是完全可能的，也是我所知道的有效组织一个人的想法的唯一可用技术。 这就是我所说的“把注意力集中在某个方面”的意思：这并不意味着忽略其他方面，只是公正地看待这样一个事实，从这个方面的角度来看，另一个是无关紧要的。

原因

- 简化软件应用程序的开发和维护。
- 当关注点被很好地分离时，各个部分可以重复使用，也可以独立开发和更新。

如何达到

- 将程序功能分解为尽可能少重叠的单独模块。

参考资源

- [Separation of Concerns](https://en.wikipedia.org/wiki/Separation_of_concerns)

## 保持干燥

每一条知识都必须在系统内有一个单一的、明确的、权威的表示。

程序中每一个重要的功能都应该在源代码的一个地方实现。 当相似的功能由不同的代码段执行时，通过抽象出不同的部分将它们组合成一个通常是有益的。

原因

- 重复代码（无意或有意的重复）会导致维护噩梦、不良分解和逻辑矛盾。
- 系统中任何单个元素的修改都不需要更改其他逻辑上不相关的元素。
- 此外，逻辑上相关的元素都可预测且一致地变化，因此保持同步。

如何达到

- 将业务规则、长表达式、if 语句、数学公式、元数据等放在一处。
- 确定系统中使用的每个单一、确定性来源，然后使用该来源生成该知识的适用实例（代码、文档、测试等）。
- 应用 三次法则
  [Rule of three](<https://en.wikipedia.org/wiki/Rule_of_three_(computer_programming)>).

参考资源

- [Dont Repeat Yourself](http://wiki.c2.com/?DontRepeatYourself)
- [Don't repeat yourself](https://en.wikipedia.org/wiki/Don't_repeat_yourself)
- [DRY Principle: Its Benefit and Cost with Examples](https://thevaluable.dev/dry-principle-cost-benefit-example/)

相关资源

- [Abstraction principle](<https://en.wikipedia.org/wiki/Abstraction_principle_(computer_programming)>)
- [Once And Only Once](http://wiki.c2.com/?OnceAndOnlyOnce) is a subset of DRY
  (also referred to as the goal of refactoring).
- [Single Source of Truth](https://en.wikipedia.org/wiki/Single_Source_of_Truth)
- A violation of DRY is [WET](http://thedailywtf.com/articles/The-WET-Cart)
  (Write Everything Twice)
- [Be careful with the code metric "duplicated lines"](https://rachelcarmena.github.io/2018/02/27/duplication-you-are-welcome.html)

## 为维护者编码

原因

- 维护是迄今为止任何项目中最昂贵的阶段。

如何达到

- 成为维护者

- 保持编码，就像有一个知道你住哪的暴力精神病患者

- 在编写代码时，一定要把维护代码的人当成一个暴力分子

  并知道你住哪儿的变态。

- 总是以这样一种方式编码和注释，如果有人比你小几级
  
  拿到代码后，他们会乐于阅读并从中学习。
  
- [Don't make me think](http://www.sensible.com/dmmt.html).

- 使用
  [Principle of Least Astonishment](https://en.wikipedia.org/wiki/Principle_of_least_astonishment).

参考资源

- [Code For The Maintainer](http://wiki.c2.com/?CodeForTheMaintainer)
- [The Noble Art of Maintenance Programming](https://blog.codinghorror.com/the-noble-art-of-maintenance-programming/)

## 避免过早优化

引用 [Donald Knuth](https://en.wikiquote.org/wiki/Donald_Knuth):

> 程序员会浪费大量的时间去思考或担心，
>
> 他们程序中非关键部分的速度，以及这些尝试
>
> 在调试和调试时，效率实际上有很强的负面影响。比如说，我们应该忘记小的效率提升
>
> 大约97%的情况下都是这样:过早优化是万恶之源。然而,我们
>
> 我们不应该错过这关键的3%的机会。

了解什么是“过早”和什么不是“过早”当然是至关重要的。

原因

- 预先不知道瓶颈在哪里。
- 优化后，可能更难阅读和维护。

如何达到

- [Make It Work Make It Right Make It Fast](http://wiki.c2.com/?MakeItWorkMakeItRightMakeItFast)
- 在需要之前不要进行优化，只有在分析后发现瓶颈才能优化。

参考资源

- [Program optimization](https://en.wikipedia.org/wiki/Program_optimization)
- [Premature Optimization](http://wiki.c2.com/?PrematureOptimization)

## 最小化耦合

模块/组件之间的耦合是它们相互依赖的程度； 低耦合更好。 换句话说，耦合是代码单元“B”在对代码单元“A”进行未知更改后“中断”的概率。

原因

- 一个模块的变化通常会导致其他模块变化的连锁反应。
- 由于模块间依赖性的增加，模块的组装可能需要更多的努力或时间。
- 特定模块可能更难重用和/或测试，因为必须包含相关模块。
- 开发人员可能害怕更改代码，因为他们不确定什么可能会受到影响。

如何达到

- 消除、最小化和降低必要关系的复杂性。
- 通过隐藏实现细节，减少了耦合。
- 使用 [Law of Demeter](#law-of-demeter).

参考资源

- [Coupling](<https://en.wikipedia.org/wiki/Coupling_(computer_programming)>)
- [Coupling And Cohesion](http://wiki.c2.com/?CouplingAndCohesion)

## 迪米特法则

不要和陌生人说话。

原因

- 它通常紧耦合
- 它可能会透露太多的实现细节

如何达到

一个对象的方法只能调用下列方法：

1. 对象自己本身的方法。
2. 方法参数对象的方法。
3. 在方法中创建的任何对象。
4. 对象的任何直接属性/字段。

参考资源

- [Law of Demeter](https://en.wikipedia.org/wiki/Law_of_Demeter)
- [The Law of Demeter Is Not A Dot Counting Exercise](https://haacked.com/archive/2009/07/14/law-of-demeter-dot-counting.aspx/)

## 组合优于继承

原因

- 类之间低耦合。
- 使用继承，子类很容易做出假设，并破坏里氏替换原则。

如何达到

- 测试 里氏替换原则（可替代性）以决定何时继承
- 当有“has a”（或“uses a”）关系时组合，当“是一个”时继承。

参考资源

- [Favor Composition Over Inheritance](https://blogs.msdn.microsoft.com/thalesc/2012/09/05/favor-composition-over-inheritance/)

## 正交性

> 正交性的基本思想是，概念上不相关的事物在系统中不应相关。

来源: [Be Orthogonal](https://www.artima.com/intv/dry3.html)

> 它与简单性有关； 设计越正交，异常就越少。 这使得使用编程语言学习、阅读和编写程序变得更加容易。 正交特征的含义与上下文无关； 关键参数是对称性和一致性。

来源:
[Orthogonality](<https://en.wikipedia.org/wiki/Orthogonality_(programming)>)

## 健壮性原则

> 在你所做的事情上要保守，在接受别人的事情上要开明

协作服务依赖彼此的接口。通常接口需要不断发展导致其他端接收到不确定的数据。如何接受的数据没有严格遵循规格书，幼稚的实现会拒绝合作。然而老练的实现会仍然正常工作就算数据不能识别。

原因

- 为了能够发展服务，您需要确保提供商可以进行更改以支持新需求，同时将对其现有客户的破坏降至最低。

如何达到

- 向其他机器（或同一机器上的其他程序）发送命令或数据的代码应该完全符合规范，但接收输入的代码应该接受不符合规范的输入，只要意思明确

参考资源

- [Robustness Principle in Wikipedia](https://en.wikipedia.org/wiki/Robustness_principle)
- [Tolerant Reader](https://martinfowler.com/bliki/TolerantReader.html)

## 控制反转

控制反转也被称为好莱坞原则，“不要打电话给我们，我们会打电话给你”。 它是一种设计原则，其中计算机程序的自定义编写部分从通用框架接收控制流。 控制反转具有很强的含义，即可重用代码和特定于问题的代码是独立开发的，即使它们在应用程序中一起运行。

原因

- 控制反转用于增加程序的模块化并使其可扩展。
- 将任务的执行与实现分离。
- 将模块集中在其设计的任务上。
- 将模块从关于其他系统如何做他们所做的假设中解放出来，而是依赖于契约。
- 防止更换模块时产生副作用。

如何达到

- 使用工厂模式
- 使用服务定位器模式
- 使用依赖注入
- 使用上下文查找
- 使用模板方法模式
- 使用策略模式

参考资源

- [Inversion of Control in Wikipedia](https://en.wikipedia.org/wiki/Inversion_of_control)
- [Inversion of Control Containers and the Dependency Injection pattern](https://www.martinfowler.com/articles/injection.html)

## 最大化凝聚力

单个模块/组件的凝聚力是其职责形成一个有意义的单元的程度； 内聚力越高越好。

原因

- 理解模块的难度增加。
- 维护系统的难度增加，因为领域中的逻辑更改会影响多个模块，并且因为一个模块的更改需要相关模块的更改。
- 重用模块的难度增加，因为大多数应用程序不需要模块提供的随机操作集

如何达到

- 共享单一职责的组相关功能（例如在一个类中）。

参考资源

- [Cohesion](<https://en.wikipedia.org/wiki/Cohesion_(computer_science)>)
- [Coupling And Cohesion](http://wiki.c2.com/?CouplingAndCohesion)

## 里氏替换原则

LSP 是关于对象的预期行为：

> 程序中的对象应该可以用它们的子类型的实例替换，而不会改变该程序的正确性。

参考资源

- [Liskov substitution principle](https://en.wikipedia.org/wiki/Liskov_substitution_principle)
- [Liskov Substitution Principle](http://www.blackwasp.co.uk/lsp.aspx)

## 开闭原则

软件实体（例如类）应该对扩展开放，但对修改关闭。也就是说实体可以在不改变其源码的情况下修改行为。

原因

- 通过最小化对现有代码的更改来提高可维护性和稳定性。

- 编写可以扩展的类（而不是可以修改的类）。
- 只暴露需要改变的活动部分，隐藏其他一切。

参考资源

- [Open Closed Principle](https://en.wikipedia.org/wiki/Open/closed_principle)
- [The Open Closed Principle](https://blog.cleancoder.com/uncle-bob/2014/05/12/TheOpenClosedPrinciple.html)

## 单一职责

一个类不该有多个改变它的理由。

更长的版本：每个类都应该有一个单一的职责，并且这个职责应该完全由类封装。 责任可以定义为改变的理由，所以一个类或模块应该有一个，而且只有一个，改变的理由。

原因

- 可维护性: 改动只应该在一个模块或一个类中。

如何达到

- 应用 [Curly's Law](#curlys-law).

参考资源

- [单一职责](https://en.wikipedia.org/wiki/Single_responsibility_principle)

## 隐藏实现细节

软件模块通过提供接口来隐藏信息（即实现细节），不要泄露任何不必要的信息。

原因

- 当实现改变时，使用接口的客户不需要改变调用。

如何达到

- 最小化类和成员的访问性。
- 不要公开暴露成员数据。
- 避免将私有实现细节放入类的接口中。
- 减少耦合以隐藏更多实现细节。

参考资源

- [信息隐藏](https://en.wikipedia.org/wiki/Information_hiding)

## Curly定律

Curly 定律是关于为任何特定代码段选择一个明确定义的目标：做一件事。

- [Curly's Law: Do One Thing](https://blog.codinghorror.com/curlys-law-do-one-thing/)
- [The Rule of One or Curly’s Law](http://grsmentor.com/blog/the-rule-of-one-or-curlys-law/)

## 封装变化

一个好的设计会识别出最有可能改变的热点并将它们封装在 API 之后。当预期的更改发生时，修改会保留在本地。

原因

- 发生变化时最小化所需的修改

如何达到

- 将变化封装到API中
- 将变化分离到自己的模块中

参考资源

- [Encapsulate the Concept that Varies](http://principles-wiki.net/principles:encapsulate_the_concept_that_varies)
- [Encapsulate What Varies](https://blogs.msdn.microsoft.com/steverowe/2007/12/26/encapsulate-what-varies/)
- [Information hiding](https://en.wikipedia.org/wiki/Information_hiding)

## 接口隔离

将胖接口减少为多个更小、更具体的客户端特定接口。 一个接口应该更依赖于调用它的代码而不是实现它的代码。

原因

- 如果一个类实现了不需要的方法，调用者需要知道该类的方法实现。 例如，如果一个类实现了一个方法但只是声明抛出，那么调用者会知道这个方法实际上不应该被调用。

如何达到

- 避免胖接口。类不应该实现违背单一职责的方法。
  [Single responsibility principle](#single-responsibility-principle).

参考资源

- [接口隔离原则](https://en.wikipedia.org/wiki/Interface_segregation_principle)

## 童子军规则

美国童子军有一个简单的规则，我们可以将其应用于我们的职业：“让露营地比你发现它的时候更干净”。 童子军规则规定表明，我们应该始终让代码比我们发现它的时候更干净。

原因

- 对现有代码库进行更改时，代码质量往往会下降，从而积累技术债务。 遵循童子军规则，我们应该注意每次提交的质量。 技术债务通过不断的重构来抵抗，无论多么小。

如何达到

- 确保每次提交不会降低代码库质量。
- 任何时候有人看到一些不那么清晰的代码，他们都应该抓住机会立即修复它。

参考资源

- [Opportunistic Refactoring](https://martinfowler.com/bliki/OpportunisticRefactoring.html)

## 命令查询分离

命令查询分离原则表明每个方法要么执行一个动作要么执行一个查询并返回数据给调用者。提问不应该修改回答者。

使用这个原则程序员可以更有信心的编码。查询方法可以用在任何地方以及任何次序因为他们不会修改状态。而命令方法就需要更加小心了。

原因

- 通过将方法明确地分离为查询和命令，程序员可以更加自信地进行编码，而无需知道每个方法的实现细节。

如何达到

- 将每个方法实现为查询方法或命令方法
- 将命名约定应用于暗示该方法是查询方法还是命令方法

参考资源

- [Command Query Separation in Wikipedia](https://en.wikipedia.org/wiki/Command%E2%80%93query_separation)
- [Command Query Separation by Martin Fowler](https://martinfowler.com/bliki/CommandQuerySeparation.html)

## Murphy定律

> 任何可能出错的事情都会出错。

似乎是一个普遍规律，即使有最小的可能出错，它最终也会出错。 当我们考虑概率和无限量的试验时，这是完全有道理的。 该规律也适用于软件开发。

参考资源

- [Murphy's law in Wikipedia](https://en.wikipedia.org/wiki/Murphy%27s_law)

## Brooks定律

> 为接近末期的软件项目添加人力会使其更容易延期。

该定律与软件项目管理有关，由 Fred Brooks 在其著名的《The Mythical Man-Month》一书中介绍。 定律的本质是，将新开发人员添加到软件项目中并不会立即提高他们的工作效率，相反，由于沟通开销，其他团队成员会花费时间。

参考资源

- [Brooks's law in Wikipedia](https://en.wikipedia.org/wiki/Brooks%27s_law)

## Linus定律

> 如果有足够的眼球，所有的bug都是浅薄的。

该法律源自 Eric S. Raymond 的《大教堂和集市》一书，以芬兰著名的 Linux 操作系统发明者 Linus Torvalds 的名字命名。 这基本上是对软件审查过程的一种赞美，其中多个开发人员在接受和合并之前检查代码段。

参考资源

- [Linus's law in Wikipedia](https://en.wikipedia.org/wiki/Linus%27s_law
