---
title: 定义业务流程 |Microsoft 文档
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
ms.openlocfilehash: 6776b78b06e68b67e9391d4f3fb1ddf64db72198
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22243269"
---
# <a name="defining-business-processes"></a>定义业务流程
解决 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 所涉及的问题时需要在不同系统间交换消息。 不过，交换消息的实际目的是根据应用程序定义和执行业务流程。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎使用业务流程来定义这些业务程序的逻辑。 另外，它还使用业务规则引擎来创建和评估业务规则组。 本部分介绍业务流程和业务规则引擎。  
  
## <a name="using-orchestrations"></a>使用业务流程  
 自动化业务流程的逻辑可以通过语言（如 Microsoft Visual Basic 或 Microsoft Visual C#）直接实现。 然而，使用传统编程语言创建、维护和管理复杂的业务流程可能会非常困难。 与其早期版本不同，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 采用一种不同的方法。 使用此版本的 BizTalk Server，业务经理或开发人员可以按图形方式定义业务流程。 与使用编程语言直接构建业务流程相比，这种方法更快，并且使业务流程更易于理解、阐释和更改。 另外，使用这种方法构建的业务流程也更易于监视，这正是业务活动监视 (BAM) 功能所需的。  
  
 对于开发人员，创建业务流程依赖于三个主要的工具： BizTalk 编辑器中创建 XML 架构，用于定义这些架构和业务流程设计器中为指定的业务逻辑之间的翻译 BizTalk 映射程序处理。 所有这些工具均以 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 为宿主，从而为开发人员提供了一致的环境。 本部分介绍了这其中的每种工具的功能以及这些工具协同工作的方式。  
  
### <a name="creating-schemas-the-biztalk-editor"></a>创建架构： BizTalk 编辑器  
 业务流程处理的各种 XML 文档均遵循某种 XML 架构。 通过 BizTalk 编辑器，开发人员可以使用 XML 架构定义语言 (XSD) 来定义这些架构，这些架构主要定义文档信息的结构和类型。  
  
 不借助某些工具，从头创建 XSD 架构将会非常困难。 为了更方便地完成这一必需步骤，可以使用 BizTalk 编辑器，这样用户（可能是开发人员）就可以通过在图形化层次结构中定义架构元素来生成架构。 也可以从文件或可访问的 Web Services 中导入现有架构。 不管以何种方式获得，这些架构都将用作 BizTalk 映射的基础。  
  
### <a name="mapping-between-schemas-the-biztalk-mapper"></a>架构之间的映射： BizTalk 映射程序  
 实现业务流程的业务流程往往会接收一些文档并发送其他文档。 通常，会将接收到的文档中的部分信息传输到已发送的文档（可能进行某种方式的转换）。 例如，订单履行流程可能会收到一份要求购买一定数量货品的订单，然后送回一条消息，指出已由于某种原因而拒绝该订单。 可能会将该订单中的信息（例如，请求标识符和订货量）从所收到的订单消息的某些字段复制到拒绝消息的相应字段中。 使用 BizTalk 映射器可以定义从一个文档到另一个文档的转换（称为映射）。  
  
 ![架构之间的映射](../core/media/understandingbts-2010-mapper.gif "UnderstandingBTS_2010_Mapper")  
  
 如上图所示，每个映射以两个 XML 架构间的图形化相关形式表示，从而定义这两个架构中元素之间的关系。 万维网联合会 (W3C) 已将可扩展样式表语言转换 (XSLT) 规定为表示 XML 架构间的此类转换的标准方法，因此 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中的映射将以 XSLT 转换的方式实现。  
  
 映射中定义的转换可能非常简单，例如，将值从一个文档原封不动地复制到另一个文档。 使用的链接，将显示在 BizTalk 映射程序作为一条连接目标架构中与其对应项的源架构中的相应元素线条表示如下直接数据副本。 使用 functoid 还可以实现更复杂的转换。 Functoid 为一组可执行代码，可用于定义 XML 架构之间的任意复杂映射，如上所示，BizTalk 映射器将 functoid 表示为连接要转换的元素的线上的方框。 由于上述某些转换相当常见，所以 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中包含了许多内置 functoid。 这些内置 functoid 分为以下类别：  
  
-   “数学”functoid，可以对源文档中各字段的值执行加、乘和除等运算，然后将结果存储在目标文档的某个字段中。  
  
-   “转换”functoid，可以将数值转换为其对应的 ASCII 码，反之亦然。  
  
-   “逻辑”functoid，可用于根据源文档中指定值之间的逻辑比较，确定是否应该在目标文档中创建某个元素或属性。 可以对这些值的相等性、大小关系以及其他方面进行比较。  
  
-   “累计”functoid，可用于计算源文档中各字段的值的平均值、总和或其他值，然后将结果存储在目标文档的单个字段中。  
  
-   “数据库”functoid，可用于访问存储在数据库中的信息。  
  
 也可以直接以 XSLT 或使用启用 .NET 的语言（例如 Visual C# 和 Visual Basic）创建自定义 functoid。 还可以按顺序组合 functoid，将一个 functoid 的输出与另一个 functoid 的输入级联。  
  
 定义文档的 XML 架构以及在不同架构的文档间映射信息都非常重要。 BizTalk 编辑器和 BizTalk 映射器可解决这两个问题。 但是，定义架构和映射只是流程的一部分。 你还必须指定将使用架构和调用映射的业务逻辑。  
  
### <a name="defining-business-logic-the-orchestration-designer"></a>定义业务逻辑： Orchestration 设计器  
 业务流程指一组操作，这些操作共同满足某些有用的业务需求。 使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，开发人员可以使用业务流程设计器以图形方式定义这些操作。 开发人员可以通过将一系列形状按逻辑方式连接在一起来创建业务流程，而无需使用某种编程语言来表示这些步骤。 业务流程设计器中可用的形状包括：  
  
-   接收形状，供业务流程接收消息。 接收形状可具有定义接收消息类型的筛选器，还可配置为在新消息到达时启动业务流程的新实例。  
  
-   发送形状，供业务流程发送消息。  
  
-   端口形状，用于定义消息的传输方式。 端口形状的每个实例均连接到发送形状或接收形状。 每个端口还具有特定的类型，用于定义以下内容：端口可接收消息的类型；方向（例如，发送或接收）；以及绑定（确定如何发送或接收消息，例如，指定特定的 URL 和其他信息）。  
  
-   判定形状，表示 if-then-else 语句，使用此语句，业务流程可根据布尔条件执行不同的任务。 表达式编辑器是业务流程设计器的一部分，可用于指定此类条件语句。  
  
-   循环形状，在特定条件为 True 的情况下控制操作的重复执行。  
  
-   构造消息形状，用于构造消息。  
  
-   转换形状，用于将信息从一个文档传输到另一个文档，并通过调用由 BizTalk 映射器定义的映射对其进行转换。  
  
-   并行操作形状，供开发人员用于指定应并行执行而不是按序执行的多个操作。 直到所有的并行操作执行完后才会执行此形状后面的形状。  
  
-   作用域形状，用于将操作分组到不同的事务中以及定义用于错误处理的异常处理程序。 该形状支持传统原子事务和长期事务。 与原子事务不同，长期事务依赖补偿逻辑而非回滚来处理意外事件。  
  
-   消息赋值形状，用于向业务流程变量赋值。 这些变量可用于存储业务流程使用的状态信息，例如要创建的消息或字符串。  
  
 下图显示了使用这其中部分形状在业务流程设计器中创建的一个业务流程。 在这个简单的示例中，接收到消息后将根据消息的内容做出判定，然后根据判定结果执行两条路径之一。 但是，解决实际问题的业务流程可能比此示例要复杂得多；为了更方便地处理这些更加复杂的图形，业务流程设计器还提供了放大和缩小功能。这样，开发人员就可以只查看业务流程中他们所关注的部分。  
  
 ![](../core/media/understandingbts-08-orchestration.gif "UnderstandingBTS_08_Orchestration")  
  
 在开发人员定义了业务流程后，形状组以及这些形状间的关系将转换为 .NET Framework 的公共语言运行时 (CLR) 使用的 Microsoft 中间语言 (MSIL)。 最后，这组由 BizTalk Server 开发人员定义的形状将成为标准的启用 .NET 的程序集。 必要时，你还可以通过从形状内调用 COM 或 .NET 对象向业务流程添加显式代码。  
  
### <a name="the-role-of-web-services"></a>Web Services 的角色  
 Web Services 允许应用程序使用 SOAP 交换 XML 文档，对集成平台有很大的影响。 若要访问外部 Web Services，业务流程的创建者可以使用 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中的“添加 Web 引用”选项以及 Web Services 适配器来直接调用操作。 同样，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 也提供了一个 Web Services 发布向导。使用该向导可生成 ASP.NET Web services 项目，将一个或多个业务流程的操作公开为 SOAP 可调用的 Web Services。 通过上述两种方法，开发人员可以从业务流程中访问现有 Web Services，也可以将业务流程的功能作为 Web Services 公开给其他业务流程。  
  
-   此外，Web Services 的出现还影响了业务流程的定义方式。 例如，假定两个组织要使用 Web Services 进行交互。 为了高效地进行互操作，交互双方都应了解对方使用的业务流程。 如果双方组织都使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，则将非常简单，他们可以使用诸如贸易伙伴管理等工具来分享这些信息。 但如果他们使用不同的产品，又该如何呢？ 对于此类情况，如果能够以非供应商特定的方式对业务流程的方方面面进行说明，则会非常有用。  
  
 为实现这一目标，Microsoft、IBM 和其他供应商创建了业务处理执行语言 (BPEL)。 使用业务流程设计器定义的业务程序可以导出为 BPEL 格式，并且 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 也可以导入用 BPEL 定义的程序。 虽然 BPEL 对描述和共享业务流程的外部可见部分非常有用，但该语言更着重于解决上述问题，而非跨平台执行整个业务流程。 需要了解的重要一点是，BPEL 完全建立于 Web services 基础之上，而 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 和其他支持此语言的产品可提供更多的功能。 例如，[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 支持在不同 XML 架构间进行映射、调用本地对象中的方法，以及 BPEL 中所不具有的其他功能。 由于这样和那样的原因，BPEL 并不是一种可用于定义业务流程的完善语言。 另外，由于结构化信息标准发展组织 (OASIS) 仍然在对 BPEL 进行标准化，因此很难将该语言看作完全成熟的技术。  
  
-   业务流程是在 BizTalk Server 中创建业务流程的基础。 但是，业务流程的某些方面可能比其他方面更易变动。 特别是，嵌入到业务流程中的决策（业务规则）最容易发生变化。 管理器的支出限制为 100000 美元上周，但她升级 bumps 这最多 $500,000 或从 100 个单位的慢速付费客户的最大允许的顺序减少到唯一的 10。 你可以指定和更新使用业务规则引擎这些规则。  
  
## <a name="using-the-business-rule-engine"></a>使用业务规则引擎  
 将业务流程设计器与 BizTalk 编辑器和 BizTalk 映射器结合使用，可有效地定义业务流程及其使用的规则。 不过，如果能够更方便地定义和更改业务规则，则会更为有用。 为实现这一目的，BizTalk Server 提供了业务规则引擎 (BRE)。 开发人员经常会使用 BRE，但与业务更为相关的用户可以使用一种称为业务规则编辑器的工具来创建和修改业务规则集。  
  
 在必须评估复杂的业务规则集时，使用 BRE 会非常有用。 例如，在决定是否发放贷款时，可能需要根据客户的信用历史记录、收入和其他因素来处理大型规则集。 同样，决定是否向申请人销售人寿保险也取决于多方面的因素，包括申请人的年龄、性别和健康状况等。 也许可以用条件语句（例如使用业务流程的判定形状）来表示所有这些规则，但会非常复杂，难于实现。 对于此类规则密集型流程，使用 BRE 可为开发人员提供便利。  
  
 使用 BRE，开发人员可以根据需要便捷地更改规则。 若要明白其中原因，则需了解更改业务流程中实现的业务规则所需执行的操作。 首先，开发人员必须在 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 中打开业务流程，修改相应的形状（可能是这些形状调用的 .NET 或 COM 对象），然后生成并部署已修改的程序集。 另外，还需要停止并重新启动包含此业务流程的 BizTalk 应用程序。 但是，如果使用 BRE 实现此业务规则，则无需重新编译任何内容或重新启动任何应用程序即可对其进行修改。 所有执行的操作仅仅是使用业务规则编辑器来更改所需规则，然后重新部署新的规则集。 所做的更改会立即生效。 虽然业务流程通常是由开发人员创建和维护的，但业务规则很容易理解，因此有时业务分析员可以自行修改这些规则，而无需求助其他技术人员。  
  
 业务规则集的创建者一开始通常是使用业务规则编辑器来定义用于指定这些规则的词汇表。 词汇表中的每个术语为特定的信息提供了用户友好的名称。 例如，词汇表可能会定义诸如“Number Shipped”、“Maximum Quantity of Items”或“Approval Limit”之类的术语。 其中每个术语都可以设置为常数或映射到特定 XML 架构（以及相应的传入消息）中的特定元素或属性，或映射到对某个数据库进行的 SQL 查询的结果，甚至还可映射到 .NET 对象中的值。  
  
 在定义词汇表后，即可将业务规则编辑器用于创建使用此词汇表的业务策略。 每个策略均包含一个或多个业务规则。 规则使用在某个词汇表中定义的术语以及逻辑运算符（例如大于、小于、等于）和其他功能来定义业务流程的运行方式。 业务规则可以定义所接收 XML 文档中包含的值应如何影响所发送 XML 文档中创建的值，这些收到的值应如何影响写入到数据库中的值，以及其他内容。  
  
 业务流程使用调用规则形状执行业务策略。 此形状将创建 BRE 的实例，指定要执行的策略，然后传入此策略所需的信息（例如，所收到的 XML 文档）。 也可使用基于 .NET 的对象模型以编程方式调用 BRE，这样就可以通过不使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 引擎的应用程序调用 BRE。 这意味着只要 BRE 有助于解决当前问题，Windows 窗体应用程序、公开 Web Services 的软件以及其他建立在 .NET Framework 基础之上的任何组件都可以使用 BRE。  
  
 因此，与上述简单示例相比，实际应用中的词汇表和业务规则会更为复杂，当然功能也更为强大。 不过，首先定义词汇表、然后定义使用该词汇表的规则集这一核心思路始终是业务规则引擎的根本原则。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Server Messaging Engine](../core/the-biztalk-server-messaging-engine.md)