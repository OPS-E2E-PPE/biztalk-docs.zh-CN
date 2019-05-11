---
title: 创建 TIBCO Rendezvous 适配器接收项目 |Microsoft Docs
description: 创建发送端口，配置要在 BizTalk 中的 TIBCO Rendezvous 的 BizTalk 适配器从接收消息的传输属性
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
ms.openlocfilehash: 503b7cf4115c9f27eaad2b9701fc8965b7b6711f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65389866"
---
# <a name="create-tibco-rendezvous-receive-artifacts"></a>创建 TIBCO Rendezvous 接收项目
创建通知或事件将类似于创建中的其他调用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。 本部分介绍如何创建用于侦听 TIBCO Rendezvous 消息的接收位置。  

## <a name="events-and-receive-locations"></a>事件和接收位置
任何 TIBCO Rendezvous 系统可以将消息发送到选择其使用者名称。 这一概念*事件*是消息的其他 TIBCO Rendezvous 程序生成。  
  
 以下步骤描述了接收位置的生命周期：  
  
1.  接收位置创建。  
  
2.  接收位置是与主机关联。  
  
3.  接收位置绑定到业务流程。  
  
4.  接收位置启用。  
  
5.  接收位置接收消息。  
  
> [!IMPORTANT]
>  每个接收位置必须具有唯一的名称。 两个接收位置不能在同一个具有相同名称[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]部署。  
> 
> [!IMPORTANT]
>  建议您设置加强的访问控制列表 (ACL) 中接收位置的存放位置。 例如，您必须设置加强的目录的 Acl 文件接收位置从其中提取消息，以便只有经过授权的用户可以在此位置中存放消息。 

## <a name="create-a-receive-port"></a>创建接收端口  
  
1.  在中**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开你的应用程序。  
  
2.  右键单击**接收端口**，依次指向**新建**，然后单击**单向接收端口**。  
  
3.  在中**接收端口属性**窗口，然后在**常规**页上，执行以下操作：  
  
    1.  在中**名称**字段中，键入`ReceiveFromTIBCORV`。  
  
    2.  在中**身份验证**组框中，指定如何处理消息时使用身份验证。  
  
    3.  选择**失败消息启用路由功能**复选框。  
  
4.  上**接收位置**页上，执行以下操作：  
  
    1.  单击 **“新建”**。  
  
    2.  在中**接收位置**窗口，然后在**常规**页上，键入**名称**的接收位置。  
  
    3.  从**类型**下拉列表中，选择**BizTalkServerIsolatedHost**，并从**接收处理程序**下拉列表中，选择的传输地址。  
  
    4.  从**接收管道**下拉列表中，选择**XMLReceive**或任何等效的管道。 
  
    5.  上**计划**页上，选择**开始日期**并**结束日期**以限制接收文档。  
  
    6.  选择**启用服务时段**复选框。  
  
    7.  单击“确定” 。  
  
5.  上**入站映射**页上，选择用于转换所选端口上的文档的入站的映射。  
  
6.  上**跟踪**页上，选择所需的跟踪消息正文和跟踪消息属性。  
  
7.  单击“确定” 。  

## <a name="set-the-transport-properties"></a>设置传输属性
在配置为侦听消息的 TIBCO Rendezvous 的 Microsoft BizTalk 适配器时，指定要侦听的使用者名称。 这是唯一的属性是必需的。  
  
 
1.  在 TIBCO Rendezvous 传输属性对话框中，展开**适配器所需的属性**，输入**Rendezvous 使用者名称**。  
  
     这是使用者名称 （允许 Rendezvous 通配符字符） 的适配器侦听。 在最简单的部署方案中，这是唯一的属性是必需的。  
  
     ![](../core/media/sadp-tibcorecvtranspropertiess.gif "SAdp_TIBCORecvTransPropertiess")  
  
2.  在中**已认证监听器设置**，根据需要已认证的消息提供的可重复使用名称和分类帐文件名称。  
  
     这是必需的如果您要定义分布式的队列。 如果不需要已认证消息，则将这些项保留为空。 分类帐文件名称和可重复使用的名称必须是唯一的此主机和在此主机上运行的其他 TIBCO Rendezvous 程序上定义的所有端口。 如果这不是这种情况，用户界面不会检测它，但捕获和记录在运行时错误。  
  
3.  在中**分布式队列设置**、 分布式的队列不是必需的如果不更改的条目。  
  
     与 BizTalk Server 组结合使用以下值。 用于 TIBCO Rendezvous 的 BizTalk 适配器使用这些值在 API 调用 TIBCO rv。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**分类帐文件名称**|已认证的侦听器 （或组成员） 的分类帐文件名称。 默认值为 Null。<br /><br /> 如果未指定一个值，则使用内存分类帐。|  
    |**可重复使用名称**|已认证的侦听器 （或组成员） 的可重复使用的名称。 默认值为 Null。<br /><br /> 可重复使用的名称需要避免重新启动进程。 如果未指定一个值，则使用生成的 （非可重用） 名称。|  
  
     分布式的队列将 BizTalk Server 组中部署 TIBCO Rendezvous 接收位置的情况下很有用。 在这种情况下，输入所需的时间间隔和策略值。 提供了激活间隔和心跳间隔按原样向 TIBCO Rendezvous。 由于时间间隔必须是一个分布式队列的所有参与方之间完全相同，只进行一次被输入值。 借助策略，这些值轻松可能每个主机上不同。 所有策略值都遵循相同的语法的部分号分隔冒号分隔主机： 值对。  
  
     例如， **host1:10; host2:20; host3:30**  
  
     主机名称必须是有效的 DNS 主机名或 IP 地址。 对于每个这些策略，该适配器查找及其与宿主关联的值，并使用用于 TIBCO Rendezvous API。  
  
     如果值都将是在所有计算机上完全相同，则可以 enteOn 上输入一个简单的值，而不是名称： 值对的列表 (例如， **20**)。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**激活间隔**|用于此分布式队列的计划程序权重策略。 它是而无需从计划程序，在其后 TIBCO RV 会激活新的计划程序的心跳消息的时间间隔。 默认值为 20 秒的时间。|  
    |**检测信号间隔**|心跳时间间隔此分布式队列内使用。 它是与 BizTalk Server 组参数一起使用。 用于 TIBCO Rendezvous 的 BizTalk 适配器使用这些值在 API 调用 TIBCO rv。 为组的活动计划程序并在该时间间隔 （以秒为单位） 广播心跳消息的适配器的实例使用的值。 默认值为 10。|  
    |**计划程序权重策略**|默认情况下 （空值），组的所有成员都具有相同的机会成为计划程序。 主机权重对值的列表提供了不同的权重策略。 默认值为 Null。|  
    |**工作能力策略**|用于此分布式队列的工作能力策略。 此值指示组成员可以处理的并发任务数量。 如果未指定，默认值为 1。 为不同的容量策略提供了主机能力对值的列表。|  
    |**工作权重策略**|用于此分布式队列的工作权重策略。 此值提供权重值，以帮助 TIBCO 分配分布式队列中的任务。 可用的辅助角色是首先分配任务的更高的权重。 默认值为 1。|  
  
4.  展开**常规设置**并输入所需的所有信息以连接到 TIBCO Rendezvous 服务器。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**附录通配符替换**|指定通配符文本替换。 接收位置正在侦听的使用者名称用于在结果消息中生成 XML 目标命名空间。 默认情况下，适配器将任何 > 文本 gtwildcard 替换生成消息中使用通配符。 在此字段中，可以指定一个不同的通配符。|  
    |**代码页编号**|标识消息原始发件人用于对传入消息中包含的字符串进行编码的代码页。 默认值是 65001。 （该适配器不支持具有相同消息使用者从两个不同的代码页环境生成。）|  
    |**元素通配符替换**|指定接收位置正在侦听的使用者名称用于在结果消息中生成 XML 目标命名空间不同的通配符文本替换。 默认情况下，适配器将任何 * 通配符使用文本 starwildcard 替换生成消息中。 在此字段中，可以指定一个不同的通配符。|  
    |**事件队列名称**|指定要使用在创建 Rendezvous 队列对象的名称。 提供为方便起见，因为关联的日志消息将显示事件队列名称。 默认值为空。|  
    |**Filter**|如果在侦听使用者名称中指定通配符，目标业务流程可能仅对感兴趣的主题可能达到的潜在非常大的集的子集。 为了尽量减少对 BizTalk Server 和数据库关联的访问的影响，可以进一步指定哪些消息应发送到 BizTalk Server。 此条目包含使用者名称 （不允许使用通配符） 的以分号分隔列表。 匹配指定通配符的使用者名称，但其使用者名称在此列表中，会被筛选掉 （不发送到 BizTalk Server） 的任何消息。 可以通过预先计算反转的筛选器逻辑 '！' 字符与筛选器值。 默认值为空 （无筛选器）。|  
    |**将不受支持的类型映射到字符串**|不支持的类型生成错误还是映射到字符串。 如果适配器使用 TIBCO Rendezvous 中，其中新类型已添加的最新版本，可以使用。|  
    |**BizTalk 组的成员**|如果设置为 True，分布式队列参数 （参考分布式队列设置节点） 和已认证的侦听参数 （参考已认证侦听设置节点） 必须设置。 默认值为 False。|  
    |**路径**|设置为指向 TIBCO Rendezvous 二进制文件，如果该信息已不在 PATH 环境变量中。|  
    |**保留顺序**|是否该适配器将调度到 BizTalk Server 中相同的顺序 （例如，使用单一调度线程） 接收的传入消息。 请注意，是否未设置已认证消息参数，它并不意味着该适配器将其发送 （指单源） 的相同顺序接收消息。|  
    |**接收位置标识符**|接收位置的名称。|  
    |Reserved|为特殊用途保留的字段。|  
  
5.  展开**Rendezvous 传输**，并输入 TIBCO Rendezvous 后台程序和程序之间进行通信所需的所有信息。  
  
     **传输 （网络，守护程序、 服务）** 指定 TIBCO Rendezvous 后台程序交换消息的方式。 这些设置将按原样发送到 TIBCO Rendezvous API。 使用默认值 （空白） 会使用默认的通信策略。  
  
     TIBCO Rendezvous 传输定义传输范围 — 即，它发送的消息的可能目标集。 这一组属性定义的传输。  
  
    |参数|Description|  
    |---------------|-----------------|  
    |**守护程序**|类型的数字标识符为 Rendezvous 传输后台程序参数。|  
    |**Network**|键入 Rendezvous 网络参数的名称。|  
    |**服务名称** `e`|键入 Rendezvous 传输服务的名称。|  
  
6.  提供使用单一登录 (SSO) 的凭据。  
  
     有两种方法可用于访问 TIBCO Rendezvous 系统。 您可以使用凭据 （用户名和密码参数） 或单一登录。  
  
    1.  选择**是**中**使用 SSO**若要使用单一登录。  
  
        > [!NOTE]
        >  请参阅[安全](../core/security-in-biztalk-adapter-for-tibco-rendezvous.md)了解如何设置 SSO。  
  
    2.  从列表中选择关联应用程序。  
  
         企业单一登录工具创建的关联应用程序表示诸如 TIBCO Rendezvous 等的应用程序。 用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器使用应用程序用户的凭据。 从指定的关联应用程序的服务器系统的 SSO 数据库检索这些凭据。  
  
        > [!NOTE]
        >  有关如何创建关联应用程序的信息，请参阅[创建关联应用程序](../core/creating-affiliate-applications1.md)。  
  
7.  提供所需的所有信息后，单击**Apply**，然后单击**确定**。  
  
     必须设置为用于 TIBCO Rendezvous 接收 TIBCO Rendezvous 消息的 BizTalk 适配器的连接参数。  
  

   
## <a name="next-steps"></a>后续步骤
  
-   [接收架构并处理事件](../core/using-tibco-rendezvous-receive-ports-from-biztalk-server.md) 
  
-   [消息映射](../core/message-mapping-in-tibco-rendezvous.md)  
  
-   [数据类型映射](../core/data-type-mapping-for-receive-handlers-in-tibco-rendezvous.md)  
  
-   [消息上下文属性 （接收处理程序）](../core/biztalk-server-message-context-properties-receive-handlers.md)