---
title: "如何配置 MSMQ 发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, send ports
- send ports, MSMQ adapters
- configuring [MSMQ adapters], send ports
ms.assetid: 37313d45-8148-4aaf-a3f2-ea05b3b8b448
caps.latest.revision: "29"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1281426116d3b83730fd98a355d1d1b78ac24c4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-msmq-send-port"></a>如何配置 MSMQ 发送端口
可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中设置 MSMQ 发送端口适配器变量。 如果未设置发送端口的属性，则使用在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中设置的默认发送处理程序值。  
  
> [!IMPORTANT]
>  如果主机实例与 MSMQ 发送端口或接收位置相关联，则请验证该 MSMQ 服务正在该计算机上运行。 如果该服务未运行，则 MSMQ 接收端口在启动后将随即关闭，并将发送到 MSMQ 发送端口的消息挂起。  
>   
>  在群集方案中，不仅需要运行群集 MSMQ 实例，还应在每个群集计算机上运行本地 MSMQ 服务。  
  
## <a name="to-configure-variables-for-an-msmq-send-port"></a>若要配置 MSMQ 的变量，将发送端口  
 按照下列步骤为 MSMQ 发送端口配置变量：  
  
1.  在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，创建一个新的发送端口或双击某个现有发送端口以对其进行修改。 请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)有关详细信息。 配置所有发送端口选项。 上**常规**选项卡上，在**传输**部分中，指定**MSMQ**为**类型**选项。  
  
2.  上**常规**选项卡上，在**传输**部分中，单击**配置**按钮旁边**类型**。  
  
3.  在**MSMQ 传输属性**对话框框中，执行以下操作：  
  
    |使用此属性|执行的操作|数据类型|默认值|  
    |-----------------------|----------------|---------------|-------------------|  
    |**密码**|指定远程队列的密码。 使用与**用户名**。|字符串|空白|  
    |**用户名**|指定远程队列的用户名。 使用与**密码**。 不能使用远程计算机的本地用户作为该用户名。|字符串|空白|  
    |**确认类型**|指定消息队列返回给发送方应用程序的确认消息的类型。 您可以选择多个确认类型。 中的确认类型的任何**System.Messaging.AcknowledgeTypes**枚举是否可用。|字符串|无|  
    |**管理队列**|指定收到确认消息的队列名称。|字符串|空白|  
    |**正文类型**|指定 MSMQ 中的消息正文类型。 有效值为.NET 成员**VarEnum**枚举。|int|8209|  
    |**证书指纹**|指定用于消息验证的证书的指纹。 将此属性与结合**使用身份验证**属性以验证消息。 使用**用户名**和**密码**属性来访问队列。|字符串|空白|  
    |**目标队列**|指定目标队列。 有关队列的详细信息，请参阅[消息队列的队列](../core/message-queuing-queues.md)。 **注意：**对要发送的 URI 端口或接收位置不能超过 256 个字符。|字符串|空白|  
    |**加密算法**|选择**RC2**， **RC4**，或**无**加密算法。|Enum|无|  
    |**最大消息大小 （以千字节为单位）**|指定发送到指定的队列消息的最大消息大小。|UnsignedInt|1024|  
    |**消息优先级**|设置消息优先级。|Enum|Normal|  
    |**可恢复**|指定是否确保消息的可恢复性。|Boolean|False|  
    |**支持分段**|将此布尔属性值设置为**True**段消息大于 4 MB。|Boolean|False|  
    |**超时**|指定等待消息到达目标队列的最长时间。 只有当使用事务时才适用。|int|0|  
    |**超时单元**|设置要使用的单元**超时**属性。<br /><br /> 选择**天**，**小时**，**分钟**，或**秒**。|Enum|Days|  
    |**事务性**|将此值设置为**True**发送消息，如果您使用事务。|Boolean|False|  
    |**使用身份验证**|将此布尔属性值设置为**True**到控制身份验证。 将此属性与结合**证书指纹**属性以验证消息。 使用**用户名**和**密码**属性来访问队列。|Boolean|False|  
    |**使用死信队列**|将此值设置为**True**将消息发送到死信队列，如果发生故障。|Boolean|True|  
    |**使用日记队列**|将此值设置为**True**以保存消息的副本，无论何时处理消息。|Boolean|False|  
  
4.  单击**确定**和**确定**再次以保存设置。  
  
## <a name="see-also"></a>另请参阅  
 [如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)   
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)