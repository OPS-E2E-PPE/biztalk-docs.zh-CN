---
title: "设置 TIBCO 会合接收传输属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- transport properties, setting for receive ports
- setting transport properties, receive
ms.assetid: 56e0a51a-6505-43bf-a48b-de35f4b114df
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 06ff1b3a11d6b95c2fb784e969363433dec3dc28
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-tibco-rendezvous-receive-transport-properties"></a>设置 TIBCO Rendezvous 接收传输属性
当您配置用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器以侦听消息时，指定要侦听的使用者名称。 这是唯一需要的属性。  
  
 使用此过程指定属性。  
  
### <a name="to-specify-tibco-rendezvous-transport-properties"></a>指定 TIBCO Rendezvous 传输属性  
  
1.  在 TIBCO 会合传输属性对话框中，展开**适配器所需属性**，输入**会合使用者名称**。  
  
     这是适配器侦听的使用者名称（允许 Rendezvous 通配符）。 在最简单的部署方案中,这是唯一必需的属性。  
  
     ![](../core/media/sadp-tibcorecvtranspropertiess.gif "SAdp_TIBCORecvTransPropertiess")  
  
2.  在**认证侦听器设置**，如果你想认证消息传送提供的可重用的名称和分类帐文件名称。  
  
     如果您要定义分布式队列，这是必填字段。 如果不需要已认证消息，则将这些项保留为空。 对于所有定义在此主机上的端口和运行在此主机上的其他 TIBCO Rendezvous 程序，分类帐文件名和可重复使用名称必须是唯一的。 如果不是这种情况，用户接口将无法检测到它，而在运行时捕获和记录一个错误。  
  
3.  在**分布式队列设置**、 分布式的队列不是必需的如果不更改的条目。  
  
     下面的值与 BizTalk Server 组一起使用。 用于 TIBCO Rendezvous 的 BizTalk 适配器在 API 调用 TIBCO RV 中使用这些值。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**分类帐文件名称**|已认证的侦听器（或组成员）的分类帐文件名称。 默认值为 Null。<br /><br /> 如果未指定一个值，则使用内存分类帐。|  
    |**可重用的名称**|已认证的侦听器（或组成员）的可重复使用名称。 默认值为 Null。<br /><br /> 若要避免进程被重新启动，则需要一个可重复使用的名称。 如果未指定一个值，则使用生成的（非可重用）名称。|  
  
     如果在 BizTalk Server 组中部署 TIBCO Rendezvous 接收位置，则分布式队列将非常有用。 在这种情况下，输入所需的时间间隔和策略值。 激活间隔和心跳间隔都按原样向 TIBCO Rendezvous 提供。 因为在一个分布式队列的所有参与者中，间隔必须是相同的，因此值必须一次性输入。 使用策略，每台主机上的这些值可以很容易地互为不同。 所有策略值都遵循用逗号分开以分号分隔的主机:值对。  
  
     例如， **host1:10; host2:20; host3:30**  
  
     主机名必须是有效的 DNS 主机名或 IP 地址。 对于这些策略中的每个策略，适配器将查找与其主机关联的值，并将其与 TIBCO Rendezvous API 一起使用。  
  
     如果值是要在所有计算机上完全相同，则可以 enteOn Tibr 简单值而不是名称： 值对的列表 (例如， **20**)。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**激活时间间隔**|用于此分布式队列的计划程序权重策略。 它是没有收到来自计划程序的心跳消息的时间间隔，在此之后，TIBCO RV 会激活一个新的计划程序。 默认值是 20 秒。|  
    |**心跳间隔**|在此分布式队列内使用的心跳时间间隔。 它与 BizTalk Server 组参数一起使用。 用于 TIBCO Rendezvous 的 BizTalk 适配器在 API 调用 TIBCO RV 中使用这些值。 作为组的活动计划程序并在该时间间隔内广播心跳消息的适配器实例将使用该值。 默认值为 10。|  
    |**权重的计划程序策略**|默认情况下（空值），组的所有成员都有相同的机会成为计划程序。 主机权重对值列表提供了不同的权重策略。 默认值为 Null。|  
    |**辅助容量策略**|用于此分布式队列的工作能力策略。 此值表示组成员可以处理的并发任务数量。 如果未指定，默认值为 1。 为不同的容量策略提供的主机容量对值列表。|  
    |**辅助权重策略**|用于此分布式队列的工作权重策略。 此值提供了一个权重值，以在 TIBCO 分布式队列中帮助 TIBCO 分配任务。 可用的工作人员将首先被分配高权重任务。 默认值为 1。|  
  
4.  展开**常规设置**然后输入 TIBCO 会合服务器连接的所有必要的信息。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**附录通配符替换**|指定通配符文本替换。 接收位置正在侦听的使用者名称用于在结果消息中生成 XML 目标命名空间。 默认情况下，适配器将使用文本 GTWILDCARD 替换生成消息中的任何“>”通配符。 您可以在此字段中指定一个不同的通配符。|  
    |**代码页编号**|识别消息创建者使用的代码页，以对包含在传入消息中的字符串进行编码。 默认值为 65001。 （该适配器不支持具有两种不同的代码页环境从生成的相同消息内容。）|  
    |**元素通配符替换**|指定不同的通配符文本替换，接收位置正在侦听的使用者名称用于在结果消息中生成 XML 目标命名空间。 默认情况下，适配器将使用文本 STARWILDCARD 替换生成消息中的任何“*”通配符。 您可以在此字段中指定一个不同的通配符。|  
    |**事件队列名称**|指定要在创建 Rendezvous 队列对象时使用的名称。 该名称为方便而提供，因为关联日志消息将显示事件队列名称。 默认值为空。|  
    |**Filter**|当您在侦听使用者名称中指定通配符时，目标业务流程可能仅对可能达到的潜在非常大使用者集的子集感兴趣。 若要使对 BizTalk Server 和到数据库的关联访问的影响降低到最小，您可以进一步指定哪些消息应被发送到 BizTalk Server。 此项包含一个分号隔离的使用者名称列表（不允许使用通配符）。 对于与指定通配符的使用者名称匹配，但其使用者命名位于该列表中的任何消息，都将被筛选掉（不被发送到 BizTalk Server）。 通过预先计算可逆转的筛选器逻辑 ！ 字符到筛选器值。 默认为空 （无筛选器）。|  
    |**将不受支持的类型映射到字符串**|不受支持的类型是生成错误还是映射到字符串。 如果使用具有较新版本 TIBCO Rendezvous 的适配器（可能添加了新类型），则可以使用此设置。|  
    |**BizTalk 组的成员**|如果设置为 True，则必须设置分布式队列参数（参考分布式队列设置节点）和已认证的侦听参数（参考已认证侦听设置节点）。 默认值为 False。|  
    |**路径**|如果该信息还未在路径环境变量中，则设置为指向 TIBCO Rendezvous 二进制文件。|  
    |**保留顺序**|适配器是否按接收消息的相同顺序（例如，使用单一调度线程）将传入消息调度到 BizTalk 服务器。 注意，如果未设置已认证消息参数，它不表示适配器将按发送消息的顺序接收消息（指单源情况）|  
    |**接收位置标识符**|接收位置的名称。|  
    |**保留**|为特殊用途保留的字段。|  
  
5.  展开**会合传输**，输入 TIBCO 会合守护程序和程序之间的通信的所有必要的信息。  
  
     **传输 （网络，后台程序，服务）**指定如何 TIBCO 会合守护程序交换消息。 这些设置将按原样发送到 TIBCO Rendezvous API。 使用默认值（空白）会导到使用默认的通信策略。  
  
     TIBCO Rendezvous 传输定义传输范围—即其发送信息的可能目标集。 此属性集定义了一种传输。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |**后台程序**|为 Rendezvous 传输后台程序参数键入数字标识符。|  
    |**网络**|键入 Rendezvous 网络参数的名称。|  
    |**服务名**`e`|键入 Rendezvous 传输服务的名称。|  
  
6.  使用单一登录 (SSO) 提供凭据。  
  
     有两种方法可用于访问 TIBCO Rendezvous 系统。 您可以使用凭据（用户名和密码参数）或单一登录。  
  
    1.  选择**是**中**使用 SSO**用于单一登录。  
  
        > [!NOTE]
        >  请参阅[使用单一登录](../core/using-single-sign-on5.md)有关如何设置 SSO 信息。  
  
    2.  从列表中选择一个关联应用程序。  
  
         一个由企业单一登录工具创建的关联应用程序表示一个应用程序（如 TIBCO Rendezvous）。 用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。  
  
        > [!NOTE]
        >  有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。  
  
7.  提供所有所需的信息后，单击**应用**，然后单击**确定**。  
  
     您必须为用于 TIBCO Rendezvous 的 BizTalk 适配器设置连接参数以接收 TIBCO Rendezvous 消息。  
  
## <a name="see-also"></a>另请参阅  
 [创建 TIBCO 会合接收处理程序](../core/creating-tibco-rendezvous-receive-handlers.md)