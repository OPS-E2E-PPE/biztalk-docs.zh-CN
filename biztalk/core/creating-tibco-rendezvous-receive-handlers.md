---
title: 创建 TIBCO 会合适配器接收项目 |Microsoft 文档
description: 创建发送端口，配置为在 BizTalk TIBCO 会合从 BizTalk 适配器接收消息的传输属性
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d617a97-c165-46bb-b5a7-b66f0c1ff9f2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed400a06f07d61f78f62f2633a80deeee293f618
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
ms.locfileid: "24014484"
---
# <a name="create-tibco-rendezvous-receive-artifacts"></a>创建 TIBCO 会合接收项目
创建通知或事件与在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中创建其他调用类似。 本部分说明如何创建用于侦听 TIBCO Rendezvous 消息的接收位置。  

## <a name="events-and-receive-locations"></a>事件和接收位置
任何 TIBCO Rendezvous 系统都可以将消息发送到其选择的使用者名称。 这一概念 *事件* 是代的其他 TIBCO 会合程序的消息。  
  
 以下步骤描述了接收位置的生命周期：  
  
1.  创建接收位置。  
  
2.  将接收位置与主机相关联。  
  
3.  接收位置绑定到业务流程。  
  
4.  接收位置已启用。  
  
5.  接收位置接收消息。  
  
> [!IMPORTANT]
>  每个接收位置都必须具有唯一名称。 同一 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 部署中的两个接收位置不能具有相同的名称。  
  
> [!IMPORTANT]
>  建议您在接收位置的存放位置中设置加强的访问控制列表 (ACL)。 例如，在文件接收位置从其中提取消息的目录中，必须设置加强的 ACL，以便只有经过授权的用户才能在此位置中存放消息。 

## <a name="create-a-receive-port"></a>创建接收端口  
  
1.  在**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。  
  
2.  右键单击 **接收端口**, ，指向 **新建**, ，然后单击 **单向接收端口**。  
  
3.  在 **接收端口属性** 窗口，请在 **常规** 页上，执行以下操作︰  
  
    1.  在 **名称** 字段中，键入 `ReceiveFromTIBCORV`。  
  
    2.  在 **身份验证** 组框中，指定使用身份验证时处理消息的方式。  
  
    3.  选择 **启用路由失败消息** 复选框。  
  
4.  上 **接收位置** 页上，执行以下操作︰  
  
    1.  单击 **“新建”**。  
  
    2.  在 **接收位置** 窗口，请在 **常规** 页上，键入 **名称** 的接收位置。  
  
    3.  从**类型**下拉列表中，选择**BizTalkServerIsolatedHost**，和从**接收处理程序**下拉列表中，选择的传输地址。  
  
    4.  从**接收管道**下拉列表中，选择**XMLReceive**或任何等效的管道。 
  
    5.  上 **计划** 页上，选择 **开始日期** 和 **结束日期** 限制接收的文档。  
  
    6.  选择 **启用服务窗口** 复选框。  
  
    7.  单击 **“确定”**。  
  
5.  上 **入站映射** 页上，选择转换所选的端口上的文档的入站的映射。  
  
6.  上 **跟踪** 页上，选择所需的跟踪消息正文和跟踪消息属性。  
  
7.  单击 **“确定”**。  

## <a name="set-the-transport-properties"></a>设置传输属性
当您配置用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器以侦听消息时，指定要侦听的使用者名称。 这是唯一需要的属性。  
  
 
1.  在 TIBCO 会合传输属性对话框中，展开 **适配器所需属性**, ，输入 **会合使用者名称**。  
  
     这是适配器侦听的使用者名称（允许 Rendezvous 通配符）。 在最简单的部署方案中,这是唯一必需的属性。  
  
     ![](../core/media/sadp-tibcorecvtranspropertiess.gif "SAdp_TIBCORecvTransPropertiess")  
  
2.  在 **认证侦听器设置**, ，如果你想认证消息传送提供的可重用的名称和分类帐文件名称。  
  
     如果您要定义分布式队列，这是必填字段。 如果不需要已认证消息，则将这些项保留为空。 对于所有定义在此主机上的端口和运行在此主机上的其他 TIBCO Rendezvous 程序，分类帐文件名和可重复使用名称必须是唯一的。 如果不是这种情况，用户接口将无法检测到它，而在运行时捕获和记录一个错误。  
  
3.  在 **分布式队列设置**, 、 分布式的队列不是必需的如果不更改的条目。  
  
     下面的值与 BizTalk Server 组一起使用。 用于 TIBCO Rendezvous 的 BizTalk 适配器在 API 调用 TIBCO RV 中使用这些值。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**分类帐文件名称**|已认证的侦听器（或组成员）的分类帐文件名称。 默认值为 Null。<br /><br /> 如果未指定一个值，则使用内存分类帐。|  
    |**可重用的名称**|已认证的侦听器（或组成员）的可重复使用名称。 默认值为 Null。<br /><br /> 若要避免进程被重新启动，则需要一个可重复使用的名称。 如果未指定一个值，则使用生成的（非可重用）名称。|  
  
     如果在 BizTalk Server 组中部署 TIBCO Rendezvous 接收位置，则分布式队列将非常有用。 在这种情况下，输入所需的时间间隔和策略值。 激活间隔和心跳间隔都按原样向 TIBCO Rendezvous 提供。 因为在一个分布式队列的所有参与者中，间隔必须是相同的，因此值必须一次性输入。 使用策略，每台主机上的这些值可以很容易地互为不同。 所有策略值都遵循用逗号分开以分号分隔的主机:值对。  
  
     例如， **host1:10; host2:20; host3:30**  
  
     主机名必须是有效的 DNS 主机名或 IP 地址。 对于这些策略中的每个策略，适配器将查找与其主机关联的值，并将其与 TIBCO Rendezvous API 一起使用。  
  
     如果值是要在所有计算机上完全相同，则可以 enteOn Tibr 简单值而不是名称︰ 值对的列表 (例如， **20**)。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**激活时间间隔**|用于此分布式队列的计划程序权重策略。 它是没有收到来自计划程序的心跳消息的时间间隔，在此之后，TIBCO RV 会激活一个新的计划程序。 默认值是 20 秒。|  
    |**心跳间隔**|在此分布式队列内使用的心跳时间间隔。 它与 BizTalk Server 组参数一起使用。 用于 TIBCO Rendezvous 的 BizTalk 适配器在 API 调用 TIBCO RV 中使用这些值。 作为组的活动计划程序并在该时间间隔内广播心跳消息的适配器实例将使用该值。 默认值为 10。|  
    |**权重的计划程序策略**|默认情况下（空值），组的所有成员都有相同的机会成为计划程序。 主机权重对值列表提供了不同的权重策略。 默认值为 Null。|  
    |**辅助容量策略**|用于此分布式队列的工作能力策略。 此值表示组成员可以处理的并发任务数量。 如果未指定，默认值为 1。 为不同的容量策略提供的主机容量对值列表。|  
    |**辅助权重策略**|用于此分布式队列的工作权重策略。 此值提供了一个权重值，以在 TIBCO 分布式队列中帮助 TIBCO 分配任务。 可用的工作人员将首先被分配高权重任务。 默认值为 1。|  
  
4.  展开 **常规设置** 然后输入 TIBCO 会合服务器连接的所有必要的信息。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**附录通配符替换**|指定通配符文本替换。 接收位置正在侦听的使用者名称用于在结果消息中生成 XML 目标命名空间。 默认情况下，适配器将使用文本 GTWILDCARD 替换生成消息中的任何“>”通配符。 您可以在此字段中指定一个不同的通配符。|  
    |**代码页编号**|识别消息创建者使用的代码页，以对包含在传入消息中的字符串进行编码。 默认值为 65001。 （该适配器不支持具有两种不同的代码页环境从生成的相同消息内容。）|  
    |**元素通配符替换**|指定不同的通配符文本替换，接收位置正在侦听的使用者名称用于在结果消息中生成 XML 目标命名空间。 默认情况下，适配器将使用文本 STARWILDCARD 替换生成消息中的任何“*”通配符。 您可以在此字段中指定一个不同的通配符。|  
    |**事件队列名称**|指定要在创建 Rendezvous 队列对象时使用的名称。 该名称为方便而提供，因为关联日志消息将显示事件队列名称。 默认值为空。|  
    |**筛选器**|当您在侦听使用者名称中指定通配符时，目标业务流程可能仅对可能达到的潜在非常大使用者集的子集感兴趣。 若要使对 BizTalk Server 和到数据库的关联访问的影响降低到最小，您可以进一步指定哪些消息应被发送到 BizTalk Server。 此项包含一个分号隔离的使用者名称列表（不允许使用通配符）。 对于与指定通配符的使用者名称匹配，但其使用者命名位于该列表中的任何消息，都将被筛选掉（不被发送到 BizTalk Server）。 通过预先计算可逆转的筛选器逻辑 ！ 字符到筛选器值。 默认为空 （无筛选器）。|  
    |**将不受支持的类型映射到字符串**|不受支持的类型是生成错误还是映射到字符串。 如果使用具有较新版本 TIBCO Rendezvous 的适配器（可能添加了新类型），则可以使用此设置。|  
    |**BizTalk 组的成员**|如果设置为 True，则必须设置分布式队列参数（参考分布式队列设置节点）和已认证的侦听参数（参考已认证侦听设置节点）。 默认值为 False。|  
    |**路径**|如果该信息还未在路径环境变量中，则设置为指向 TIBCO Rendezvous 二进制文件。|  
    |**保留顺序**|适配器是否按接收消息的相同顺序（例如，使用单一调度线程）将传入消息调度到 BizTalk 服务器。 注意，如果未设置已认证消息参数，它不表示适配器将按发送消息的顺序接收消息（指单源情况）|  
    |**接收位置标识符**|接收位置的名称。|  
    |**保留**|为特殊用途保留的字段。|  
  
5.  展开 **会合传输**, ，输入 TIBCO 会合守护程序和程序之间的通信的所有必要的信息。  
  
     **传输 （网络，后台程序，服务）** 指定如何 TIBCO 会合守护程序交换消息。 这些设置将按原样发送到 TIBCO Rendezvous API。 使用默认值（空白）会导到使用默认的通信策略。  
  
     TIBCO Rendezvous 传输定义传输范围—即其发送信息的可能目标集。 此属性集定义了一种传输。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |**后台程序**|为 Rendezvous 传输后台程序参数键入数字标识符。|  
    |**网络**|键入 Rendezvous 网络参数的名称。|  
    |**服务名** `e`|键入 Rendezvous 传输服务的名称。|  
  
6.  使用单一登录 (SSO) 提供凭据。  
  
     有两种方法可用于访问 TIBCO Rendezvous 系统。 您可以使用凭据（用户名和密码参数）或单一登录。  
  
    1.  选择 **是** 中 **使用 SSO** 用于单一登录。  
  
        > [!NOTE]
        >  请参阅[安全](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)有关如何设置 SSO 信息。  
  
    2.  从列表中选择一个关联应用程序。  
  
         一个由企业单一登录工具创建的关联应用程序表示一个应用程序（如 TIBCO Rendezvous）。 用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 这些凭据是从服务器系统的 SSO 数据库中为指定关联应用程序检索的。  
  
        > [!NOTE]
        >  有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。  
  
7.  提供所有所需的信息后，单击 **应用**, ，然后单击 **确定**。  
  
     您必须为用于 TIBCO Rendezvous 的 BizTalk 适配器设置连接参数以接收 TIBCO Rendezvous 消息。  
  

   
## <a name="next-steps"></a>后续步骤
  
-   [接收架构并处理事件](../core/using-tibco-rendezvous-receive-ports-from-biztalk-server.md) 
  
-   [消息映射](../core/message-mapping-in-tibco-rendezvous.md)  
  
-   [数据类型映射](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)  
  
-   [消息上下文属性 （接收处理程序）](../core/biztalk-server-message-context-properties-receive-handlers.md)