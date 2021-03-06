# DDD精粹

领域驱动设计 Domain Driven Design

如果你希望打磨软件匠艺并提高项目的成功率，如果你迫切期望创造软件来帮助企业把业务竞争力提升到新高度，如果你期望实现出来的软件既能正确地对业务需求建模又可以采用最先进的软件架构进行扩展，那么就来学习并掌握领域驱动设计（DDD）吧。它可以帮你实现这些目标并带来更多收获。

***在项目中成功应用DDD的最重要的手段之一就是聘请优秀的员工。在这方面，优秀人才和中上水平的开发人员根本无法替代。DDD是开发软件的先进理念和技术，中上水平的乃至是非常优秀的开发人员才能运用好它。雇用技能匹配和自我激励的合适人选的重要性永远不能低估。***

## 基本概念
### 战略设计
DDD的战略设计工具可以帮助你和你的团队做出最有竞争力的软件设计选择和业务整合决策。你的组织将从这些明确反映其核心业务竞争力的软件模型中获得最大的收益。
#### 限界上下文（BoundedContext）
限界上下文的战略设计模式来分离领域模型。发展一套领域模型的通用语言（UbiquitousLanguage）。通过协作而产生的语言会变得统一、流行、并遍布于团队的日常口头交流和软件模型之中。
#### 子域（Subdomain）
通过子域处理遗留系统中无边界的复杂性，改进新项目上的成果。
#### 上下文映射图（Context map）
同时定义了两个进行集成的限界上下文之间的团队间关系及技术实现方式。
### 战术设计
DDD的战术实施工具可以帮助你和你的团队设计出实用的软件，它能对业务独一无二的运作方式进行精准地建模。
#### 聚合（Aggregate）
将若干实体和值对象以恰当的大小聚集在一起。
#### 领域事件（Domain Events）
既可以让你明确地建立模型，也可把模型内部发生的事情分享给需要知道这一切的系统。
## 限界上下文
### 问题空间（ProblemSpace）
问题空间是在给定项目的约束条件下进行高级战略分析与设计各个步骤的地方。
### 解决方案空间（SolutionSpace）
解决方案空间就是真正实施解决方案的地方，这些解决方案在问题空间讨论中被识别为核心域。
#### 核心域（CoreDomain）
当限界上下文被当作组织的关键战略举措进行开发时，即被称为核心域。
+ 只有经过“仅限核心”的严格过滤之后保留下来的概念，才能成为拥有限界上下文的团队的通用语言的一部>分。限界上下文的边界强调其内部的严谨性。
+ 我们不要将核心域局限在名词上。相反，应当使用一组具体场景来表达核心域，这些场景描述了领域模型应>该做的事情。
+ 你可能想知道如何把书面场景转换成某种可以用来验证领域模型是否符合团队需求说明的产出物。可以采用一种被称为实例化需求[Specification]的技术，它也被称为行为驱动开发[BDD]。
#### 子域（Sub Domain）
+ 敏捷项目管理核心即一个清晰的限界上下文，也是一个清晰的子域。
+ 子域是整个业务领域的一部分。你可以认为子域代表的是一个单一的、有逻辑的领域模型。
+ 子域可以用来逻辑地拆分整个业务领域，这样才能理解存在于大型复杂项目中的问题空间。
+ 子域可以作为讨论问题空间的工具。当使用DDD时，限界上下文应该与子域一一对应（1:1）。也就是说，如果存在一个限界上下文，那么它的目标就应该是对应且只对应一个子域模型。这样可以使限界上下文清晰并且始终专注于核心战略举措。
##### 核心域（Sub Domain）
它是一个唯一的、定义明确的领域模型，要对它进行战略投资，并在一个明确的限界上下文中投入大量资源去精心打磨通用语言。
##### 支撑子域（Supporting Subdomain）
这类建模场景提倡的是“定制开发”，因为找不到现成的解决方案。
##### 通用子域（Generic Subdomain）
通用子域的解决方案可以采购现成的，也可以采用外包的方式，抑或是由内部团队实现，但我们不用为其分配与核心域同样优质的研发资源，甚至都不如支撑子域。
## 映射的种类
### 合作关系（Partnership）
关系存在于两个团队之间。每个团队各自负责一个限界上下文。两个团队通过互相依赖的一套目标联合起来形成合作关系。
### 共享内核（SharedKernel）
用上图中两个限界上下文的交集表示，它描述了这样一种关系：两个（或更多）团队之间共享着一个小规模但却通用的模型。团队必须就要共享的模型元素达成一致。有可能它们当中只有一个团队会维护、构建及测试共享模型的代码。
### 客户—供应商（Customer-Supplier）
描述的是两个限界上下文之间和两个独立团队之间的一种关系：供应商位于上游（图中的U），客户位于下游（图中的D）。支配这种关系的是供应商，因为它必须提供客户需要的东西。
### 跟随者（Conformist）
关系存在于上游团队和下游团队之间，上游团队没有任何动机满足下游团队的具体需求。由于各种原因，下游团队也无法投入资源去翻译上游模型的通用语言来适应自己的特定需求，因此只能顺应上游的模型。
### 防腐层（AnticorruptionLayer）
最具防御性的上下文映射关系，下游团队在其通用语言（模型）和位于它上游的通用语言（模型）之间创建了一个翻译层。防腐层隔离了下游模型与上游模型，并完成两者之间的翻译。所以，这也是一种集成的方式。*但凡有可能，你就应该尝试在下游模型和上游集成模型之间创建一个防腐层，这样才可以在你这端的集成中创造出特别适合业务需求的模型概念，并将外部概念完全地隔离。*
### 开放式主机服务（OpenHostService）
定义一套协议或接口，让限界上下文可以被当作一组服务访问。该协议是“开放的”，所有需要与限界上下文进行集成的客户端都可以相对轻松地使用它。通过应用程序编程接口（API）提供的服务都有详细的文档。
### 已发布语言（PublishedLanguage）
一种有着丰富文档的信息交换语言，可以被许多消费方的限界上下文简单地使用和翻译。*这种已发布语言可以用XML Schema、JSON Schema或更佳的序列化格式定义。*
### 各行其道（SeparateWay）
使用各种通用语言来与一个或多个限界上下文集成这样的方式不能产生显著的回报。也许你所寻求的功能并不能由任何一种通用语言提供。在这种情况下，只能在限界上下文中创造属于自己的特殊解决方案，并放弃针对这种特殊情况的集成。
### 大泥球（BigBallofMud）
必须与一个或多个这样的大泥球系统集成，请尝试针对每个这样的遗留系统创建一个防腐层，保护自己的模型免受污染，否则会陷入难以理解的泥潭。*不管怎样，别“讲”这种语言！*
## 善用上下文映射
+ RPC的主要问题是，无论是使用SOAP或是其他方法，它都缺乏健壮性。如果网络出现问题或者托管SOAP API的系统出现问题，那么看似简单的过程调用将完全失败，只会留下错误的结果。
+ 造成RESTful HTTP失败的原因通常和许多造成RPC失败的原因一样——网络或服务提供商故障，还有意外延迟。
+ 使用REST常犯的设计错误是直接把模型中的聚合暴露成资源。服务端模型一旦发生变化，资源也会随之一起改变，这样会把跟随者关系强加给每个客户端。应该根据客户端驱动的用例设计出“合成”的资源。而不是直接给出实际的领域模型。
+ 在使用异步消息机制进行集成时，很多工作都是通过客户端限界上下文订阅由它自己或另一个限界上下文发布的领域事件（DomainEvents）来完成的。使用消息机制是最健壮的集成方法之一，因为可以消除那些和阻塞（同步）形式（如RPC和REST）有关的暂时性耦合。
+ 通常情况下，领域事件由限界上下文中的聚合（Aggregate）发布，许多对它感兴趣的订阅方限界上下文都可以消费。当订阅方限界上下文收到领域事件时，将依据其类型和值进行一些操作。一般它会导致在消费方限界上下文中新聚合的创建或者现有聚合的修改。
+ 在使用消息进行集成的所有用例中，整体解决方案的质量很大程度上将取决于所选消息机制的质量。消息机制应支持至少一次投递[Reactive]来保证所有消息最终都会被收到。这也意味着订阅方限界上下文必须实现成幂等接收者（Idempotent Receiver）[Reactive]。
## 运用聚合进行战术设计
+ 一个实体模型就是一个独立的事物。每个实体都拥有一个唯一的标识符，可以将它的个体性和所有其他类型相同+ 或者不同的实体区分开。
+ 一个值对象，或者更简单地说，值（Value），是对一个不变的概念整体所建立的模型。它没有唯一标识符，而+ 是由值类型封装的属性对比来决定相等性。
+ 每个聚合的根实体（RootEntity）控制着所有聚集在其中的其他元素。
+ 每个聚合都会形成保证事务一致性的边界。这意味着在一个单独的聚合中，在控制被提交给数据库的事务时，它+ 的所有组成部分必须根据业务规则保持一致。
+ 聚合设计的一条普遍规则：只能在一次事务中修改一个聚合实例并提交。
## 聚合设计的四条基本规则
+ 在聚合边界内保护业务规则不变性。
+ 聚合要设计得小巧。
+ 只能通过标识符引用其他聚合。
+ 使用最终一致性更新其他聚合。
## 建立聚合模型
贫血领域模型（AnemicDomain Model）就是一个令人讨厌的巨大诱惑。
+ 第一件必须做的事情是为聚合根实体创建一个类。每一个聚合根实体都必须拥有全局唯一的标识符。
+ 接下来要记录在查找聚合时必须用到的内在属性或者字段。
+ 最后，会添加一些复杂的行为。
### 慎重选择抽象级别
+ 不要被这个诱人的、实现高度抽象的陷阱所吸引，而要根据团队精练过的领域专家的心智模型，脚踏实地地对通用语言进行建模。
### 大小适中的聚合
+ 将重点先放在聚合设计的规则二上：“聚合要设计得小巧”。每个聚合一开始创建时只允许包含一个实体，并且它将作为聚合根。千万不要尝试在边界内放入两个实体。这样的机会很快就会出现。用你认为和单个聚合根关联最紧密的字段/属性填充每个实体。这里有一个重要的技巧是定义出每个用来识别和查找聚合的字段/属性，以及任何其他用于构造聚合并使之处于有效初始状态的内在属性。
+ 现在将重点放在聚合设计的规则一上：“聚合边界内保护业务不变性规则”。为每个聚合和它的一致性规则制作一个清单，还要记录所有这些基于响应的更新的时间范围。
+ 现在询问领域专家，每个基于响应的更新可以等待多长时间。答案会是两种：（a）即时发生；（b）在n秒/分/小时/天之内发生。一种可行的寻找正确的业务阈值的方法是，先抛出一个夸张到显然无法接受的时间范围（比如几周或几个月）。业务专家很可能会据此提出一个可接受的时间范围作为回应。
+ 对每一个即时发生的时间范围（3a），应该坚定地考虑把这两个实体合并到同一个聚合的边界之内。例如，聚合A1和聚合A2实际上将合并成一个新的聚合A[1， 2]。现在之前定义的聚合A1和聚合A2将不复存在。只剩下唯一的聚合A[1，2]。
+ 对于每一个在给定等待时间（3b）内更新的响应聚合，将使用聚合设计的规则四来更新它们：“利用最终一致性更新其他聚合”。
### 可测试的单元
还应该将聚合封装设计得合理，让它们更适合单元测试。
## 运用领域事件进行战术设计
领域事件是一条记录，记录着在限界上下文（BoundedContext）中发生的对业务产生重要影响的事情。
### 设计、实现并运用领域事件
+ 一般都要表达领域事件发生的日期和时间。必须重视领域事件类型的命名。
+ 使用的词语应该体现出模型的通用语言（Ubiquitous Language）。
+ 领域事件类型的名称应该是对过去发生的事情的陈述，即动词的过去式。
+ 只是按照因果顺序保存领域事件并不能保证这些事件会以同样的顺序到达其他的分布式节点。因此，识别出正确因果关系的重任就落到了消费事件的限界上下文肩上。因果关系可以由领域事件类型本身表明，或者由和领域事件关联在一起的元数据表示，比如一个序列标识符或者因果标识符。序列标识符或者因果标识符可以表示导致领域事件发生的原因事件，如果原因事件尚未出现，消费者必须等它到达后才能处理先前到达的（结果）事件。某些情况下，可以忽略潜在的领域事件，这些事件已经被后续事件的关联动作取代，这种情况下因果关系具有可消除的影响。
+ 命令和领域事件的不同在于，某些情况下不恰当的命令可以被拒绝，比如某些资源（产品、资金等）的供应和可用性或者其他业务层面的验证导致的情况。所以，命令可能被拒绝，而领域事件是历史事实，必须无条件地接受。尽管如此，为了响应基于时间的领域事件，应用可能需要生成一条或多条命令，来执行一些动作。
### 事件溯源
事件溯源（Event Sourcing）可以描述为，对所有发生在聚合实例上的领域事件进行持久化，把它们当作对聚合实例变化的记录。你存储的是发生在聚合上的所有独立事件，而不是把聚合状态作为一个整体进行持久化。
+ 一个聚合实例上发生的所有领域事件，按照它们原本发生的顺序，组成了该实例的事件流。
+ 每个发生在指定聚合实例上的领域事件都是由命令引起的。
+ 事件存储就是一个顺序存储集合或者一张表，所有领域事件都被追加到其中。由于事件存储只允许追加记录，从而使得存储进程非常快，所以可以规划在核心域上使用事件溯源，来达到高吞吐量、低延迟和高伸缩性。
+ 使用事件溯源最大的优势之一就是它在独立事件这个级别保存了核心域中发生的一切。
## 加速和管理工具
### 事件风暴
事件风暴（EventStorming）是一种快速的设计技术，让领域专家和开发人员都可以参与到这个快节奏的学习过程中。它聚焦于业务和业务流程，而非名词概念和数据。
+ 通过创建一系列写在便利贴上的领域事件，快速梳理出业务流程。
+ 创建导致每个领域事件发生的命令。
+ 把命令和领域事件通过实体/聚合关联起来，命令在实体/聚合上执行并产生领域事件的结果。
+ 在建模平面上画出边界和表示事件流动的箭头连线。
+ 识别用户执行操作所需的各种视图（View），以及不同用户的关键角色。
