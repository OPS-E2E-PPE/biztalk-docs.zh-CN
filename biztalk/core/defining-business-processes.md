---
title: 定义业务流程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e5e0fdfe-e298-4f32-a7c5-d081b926a206
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 098001041c47b096ab2c2079d4f830e96ed1e19f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65352398"
---
# <a name="defining-business-processes"></a>定义业务流程
交换不同系统之间的消息是解决问题的必要组成部分，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]地址。 但是，真正的目标是定义和执行的应用程序的业务流程。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]引擎使用业务流程来定义这些业务流程的逻辑。 若要创建和评估业务规则组，它使用业务规则引擎。 本部分介绍业务流程和业务规则引擎。  
  
## <a name="using-orchestrations"></a>使用业务流程  
 可以直接在 Microsoft Visual Basic 或 Microsoft Visual C# 等语言中实现自动化的业务流程的逻辑。 尚未在创建、 维护和管理复杂的业务流程的传统编程语言很难。 与其早期版本不同[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]采用不同的方法。 这样，业务经理或开发人员以图形方式定义业务流程。 执行此操作可构建直接在编程语言中，业务流程相比速度更快，它还使过程易于理解、 阐释和更改。 以这种方式构建的业务流程还可以更轻松地监视业务活动监视 (BAM) 技术利用了这一事实。  
  
 开发人员创建业务流程依赖于三个主要工具： 用于创建 XML 架构，BizTalk 映射器，用于定义这些架构与指定的业务逻辑的业务流程设计器之间的转换在 BizTalk 编辑器处理。 所有这些工具都托管在[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，为开发人员提供了一致的环境。 此部分介绍了这其中每个工具功能以及它们如何协同工作。  
  
### <a name="creating-schemas-the-biztalk-editor"></a>创建架构：在 BizTalk 编辑器  
 业务流程处理 XML 文档，其中每个符合特定 XML 架构。 在 BizTalk 编辑器开发人员可以定义这些架构，实质上是定义的结构和类型的文档的信息，请使用 XML 架构定义语言 (XSD)。  
  
 创建没有一些工具支持的原始 XSD 架构并不简单。 若要使这一必需步骤更易上手，BizTalk 编辑器使用户 — 可能是开发人员 — 通过在图形化层次结构中定义它的元素生成一个架构。 此外可以从文件或可访问 Web 服务导入现有的架构。 何种方式获得，但架构用作的基础 BizTalk 映射。  
  
### <a name="mapping-between-schemas-the-biztalk-mapper"></a>架构之间的映射：BizTalk 映射器  
 通常实现业务流程的业务流程接收一些文档，并发送其他人。 通常情况下，接收到文档中的信息的一部分被传输到发送的文档，可能是以某种方式转换。 例如，订单执行流程可能会接收订单某些数目的项，然后发回消息，指出顺序被拒绝，出于某种原因。 信息的顺序，例如请求标识符和数量排序，可以从复制中收到的订单消息的字段到拒绝消息中的字段。 BizTalk 映射器可以用于定义的转换，称为映射到另一个文档中。  
  
 ![架构之间的映射](../core/media/understandingbts-2010-mapper.gif "UnderstandingBTS_2010_Mapper")  
  
 该图中所示，为每个映射表示为定义这些架构中元素之间的关系的两个 XML 架构间的图形化相关。 World Wide Web 联合会 (W3C) 已定义为一种标准的方式来表达这些类型的 XML 架构间转换的可扩展样式表语言转换 (XSLT)，并因此在将映射[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]作为 XSLT 转换实现。  
  
 映射中定义的转换可以非常简单，如将复制到另一个文档中未更改的值。 使用的链接，BizTalk 映射器中显示为一条连接源架构中的相应元素与目标架构中的对应项表示此类的直接数据副本。 更复杂的转换也可使用 functoid。 Functoid 为一组可执行代码，可以定义 XML 架构之间的任意复杂映射，如上所示，BizTalk 映射器表示它为连接要转换的元素在行框。 上述某些转换相当常见，因为[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]包含许多内置 functoid。 这些内置 functoid 分为类别，包括以下各项：  
  
- 数学 functoid 用于执行如添加、 相乘，并将源文档中的字段的值以及将结果存储在目标文档中的字段中的操作。  
  
- 转换 functoid 将数值转换为其 ASCII 等效项，反之亦然。  
  
- 判断 functoid 可用于确定元素或属性是否应基于源文档中的指定值之间的逻辑比较目标文档中创建。 这些值可以比较相等，大于比/更少，且以其他方式。  
  
- 累计 functoid 计算平均值、 总和或其他源文档中的各字段的值，然后将结果存储在目标文档中的单个字段中。  
  
- 数据库 functoid，可以访问存储在数据库中的信息。  
  
  还有可能直接在 XSLT 或使用创建自定义 functoid。Visual C# 和 Visual Basic 等 NET 启用语言。 Functoid 也可以组合在序列中，级联到另一个输入一个输出。  
  
  有一种跨具有不同架构的文档定义文档的 XML 架构，以及映射信息的一种机制方法至关重要。 BizTalk 编辑器和 BizTalk 映射器解决这两个问题。 但是，定义架构和映射是仅过程的一部分。 您还必须指定将使用的架构和调用映射的业务逻辑。  
  
### <a name="defining-business-logic-the-orchestration-designer"></a>定义业务逻辑：业务流程设计器  
 业务流程是一组共同满足某些有用的业务需求的操作。 使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，开发人员可以使用业务流程设计器以图形方式定义这些操作。 而不是表示某些编程语言中的步骤，开发人员可以通过将连接在一起一系列形状按逻辑方式创建业务流程。 业务流程设计器中可用的形状包括：  
  
- 接收形状，供业务流程接收消息。 接收形状可以定义将接收的消息类型的筛选器，并且它还可以配置为新消息到达时启动业务流程的新实例。  
  
- 发送形状，供业务流程发送消息。  
  
- 端口形状，用于定义消息的传输方式。 端口形状的每个实例连接到发送或接收形状。 每个端口还具有的类型，用于定义以下内容类型的消息端口可接收;方向，如发送或接收;并确定如何发送或接收的例如一条消息，一个绑定指定特定的 URL 和其他信息。  
  
- 判定形状，表示允许业务流程执行不同任务根据布尔条件-if-then-else 语句。 表达式编辑器中，一部分的业务流程设计器中，可以用于指定此类条件语句。  
  
- 循环形状，它控制的重复执行操作，在特定条件为 true。  
  
- 构造消息形状，用于生成一条消息。  
  
- 转换形状，用于将信息从一个文档到另一个，并将其转换通过调用定义的 BizTalk 映射器映射。  
  
- 并行操作形状，它允许开发人员指定并行，而不是序列中应执行多个操作。 所有的并行操作完成之前，不执行跟随此形状。  
  
- 作用域形状，用于为事务的操作的分组以及定义错误处理的异常处理程序。 支持传统原子事务和长时间运行的事务。 与不同的原子事务、 长时间运行的事务依赖补偿逻辑而不是非回滚来处理意外的事件。  
  
- 消息赋值形状，用于将值分配到业务流程变量。 可以使用这些变量来存储使用的业务流程，如字符串或要创建的消息的状态信息。  
  
  下图显示了在业务流程设计器中创建业务流程使用几个这些形状。 在此简单示例中，收到一条消息、 决定根据对该消息的内容和结果执行的两个路径之一。 解决实际问题的业务流程可以是复杂得多比这一点;若要使这些更复杂的关系图更轻松地使用，业务流程设计器包括放大和缩小功能。开发人员可以查看只有他们当前感兴趣的业务流程的那些部分。  
  
  ![](../core/media/understandingbts-08-orchestration.gif "UnderstandingBTS_08_Orchestration")  
  
  开发人员定义了业务流程后，组形状和它们之间的关系将转换为 Microsoft 中间语言 (MSIL) 使用由.NET Framework 公共语言运行时 (CLR)。 从根本上讲，BizTalk Server 开发人员定义的形状的组将成为只是一个标准。启用 NET 的程序集。 此外可以将显式代码添加到业务流程在必要时，通过调用 COM 或.NET 对象中，在形状内。  
  
### <a name="the-role-of-web-services"></a>Web 服务的角色  
 Web 服务允许应用程序交换使用 SOAP、 XML 文档，并对集成平台有很大的影响。 若要访问外部 Web 服务，业务流程的创建者可以使用中的添加 Web 引用选项[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]以及 Web Services 适配器来直接调用操作。 同样，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]提供了可生成 ASP.NET Web 服务项目，将一个或多个业务流程的操作为 SOAP 可调用 Web 服务公开的 Web Services 发布向导。 这两个选项允许开发人员能够同时访问从业务流程中的现有 Web 服务并公开为 Web 服务与其他业务流程的业务流程的功能。  
  
- Web 服务的出现还会影响业务流程的定义。 例如，考虑这种情况，两个组织使用 Web 服务进行交互。 若要有效地进行交互操作，可能会有所了解对方使用的业务流程的交互对所需的每个参与方。 如果这两个组织都使用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，这不是大问题; 可以使用贸易合作伙伴管理技术等工具来分发这些信息。 但如果它们使用不同的产品？ 这种情况下，最好有办法以非供应商特定的方式描述业务流程的方面。  
  
  为此，Microsoft、 IBM 和其他人已创建业务流程执行语言 (BPEL)。 使用业务流程设计器定义的业务流程可以导出为 bpel 格式，和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]还可以导入用 BPEL 定义。 用于描述和共享业务流程的外部可见部分语言时，BPEL 更着重于解决此问题，而非在跨平台执行整个业务流程。 也很重要若要了解 BPEL 完全基于 Web 服务，而[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]和其他支持此语言的产品提供的详细信息。 例如，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]支持不同的 XML 架构之间的映射、 调用本地对象和 BPEL 中未提供其他功能中的方法。 有关这些和其他原因，BPEL 并不是一种用于定义业务流程的完整语言。 并假定 BPEL 是仍在进行标准化的进步的结构化信息标准组织 (OASIS) 过程中，很难看作完全成熟的技术。  
  
- 业务流程是 BizTalk Server 中创建业务流程的基本机制。 业务流程的某些方面往往会更改次数多过其他，但是。 具体而言，业务流程中嵌入的决策 — 业务规则 — 通常是其最容易发生变化。 管理器的支出限制为 100,000 美元的奖金过去一周，但升迁，这最多 500,000 美元或从 100 个单位的慢速付费客户的最大允许的订单减少至仅有 10。 您可以指定和更新这些规则使用业务规则引擎。  
  
## <a name="using-the-business-rule-engine"></a>使用业务规则引擎  
 业务流程设计器中，以及在 BizTalk 编辑器和 BizTalk 映射器中，提供一种有效的方式来定义业务流程和它使用的规则。 它可能很有用，但是，能够轻松地定义和更改业务规则。 为此，BizTalk Server 提供业务规则引擎 (BRE)。 开发人员经常会使用 BRE，但更多面向业务的用户可以创建和修改业务规则使用名为业务规则编辑器的工具集。  
  
 BRE 可的一个情况是业务的一种复杂规则必须进行评估设置。 例如，在决定是否发放贷款时，可能需要通过大量的基于客户的信用额度历史记录、 收入和其他因素的规则。 同样，确定是否向申请人销售人寿保险取决于许多因素，包括申请人的年龄、 性别和运行状况。 表示所有这些规则作为使用条件语句，说，业务流程的判定形状可能是有可能，但是会非常复杂，来实现。 这些规则密集型流程，BRE 可使开发人员的生活更简单。  
  
 使用 BRE，开发人员可以快速并轻松地根据需要更改规则。 要了解原因，考虑一下所需更改业务流程中实现的业务规则。 开发人员必须首先打开中的业务流程[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]，修改相应的形状 （和可能是调用.NET 或 COM 对象它们），然后生成并部署修改后的程序集。 另外，还需要停止并重新启动包含此业务流程的 BizTalk 应用程序。 如果改为使用 BRE 实现此业务规则，它可以无需重新编译或重新启动任何修改。 所有需要的只是使用业务规则编辑器来更改所需的规则，然后重新部署新的规则集。 此更改将立即生效。 和业务流程通常创建和维护由开发人员，业务规则用于读取，在某些情况下可以进行修改而无需涉及到更多技术人员的业务分析师。  
  
 通过使用业务规则编辑器来指定这些规则定义用于词汇通常开始的一组业务规则的创建者。 词汇中的每一项提供了一些信息的用户友好名称。 例如，词汇表可能会定义诸如 Number Shipped 或 Maximum Quantity of Items 或 Approval Limit 之类的术语。 每个这些术语可设置为常数或映射到特定元素或属性，在某些 XML 架构 （并且因此将传入消息中），或者针对一些数据库的 SQL 查询的结果或甚至到.NET 对象中的值映射。  
  
 定义词汇后，可以使用业务规则编辑器来创建使用此词汇表的业务策略。 每个策略可以包含一个或多个业务规则。 规则使用在某个词汇表以及逻辑运算符，例如大于、 小于、 等于，和其他定义的术语来定义业务流程的运行方式。 业务规则可以定义在收到的 XML 文档中包含的值应如何影响所发送 XML 文档中创建的值或这些收到的值应影响哪些值用一个数据库，以及其他内容。  
  
 若要执行的业务策略，业务流程使用调用规则形状。 此形状将创建 BRE 的实例，指定要执行，然后传入此策略所需，如接收 XML 文档的信息的策略。 此外可以使用以编程方式调用 BRE。基于网络的对象模型中，这使它在不使用的应用程序中调用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 这意味着该 Windows 窗体应用程序、 公开 Web services 的软件，和任何其他.NET Framework 上构建可以使用 BRE 只要它可帮助解决的问题。  
  
 词汇和业务规则可以是复杂得多 — 和强大得多 — 比此处所述的简单示例。 但定义词汇表、 然后定义使用该词汇表的规则集的核心理念是业务规则引擎的核心。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk Server 消息引擎](../core/the-biztalk-server-messaging-engine.md)