---
title: 如何配置 MSMQ 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MSMQ adapters, send ports
- send ports, MSMQ adapters
- configuring [MSMQ adapters], send ports
ms.assetid: 37313d45-8148-4aaf-a3f2-ea05b3b8b448
caps.latest.revision: 29
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aad4a63a11f415c57778db726af0559858eab05c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992014"
---
# <a name="how-to-configure-an-msmq-send-port"></a>如何配置 MSMQ 发送端口
可以在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中设置 MSMQ 发送端口适配器变量。 如果未设置发送端口的属性，则使用在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中设置的默认发送处理程序值。  

> [!IMPORTANT]
>  如果主机实例与 MSMQ 发送端口或接收位置相关联，则请验证该 MSMQ 服务正在该计算机上运行。 如果该服务未运行，则 MSMQ 接收端口在启动后将随即关闭，并将发送到 MSMQ 发送端口的消息挂起。  
>   
>  在群集方案中，不仅需要运行群集 MSMQ 实例，还应在每个群集计算机上运行本地 MSMQ 服务。  

## <a name="to-configure-variables-for-an-msmq-send-port"></a>若要配置 msmq 发送端口的变量  
 按照下列步骤为 MSMQ 发送端口配置变量：  

1. 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中，创建一个新的发送端口或双击某个现有发送端口以对其进行修改。 请参阅[如何创建发送端口](../core/how-to-create-a-send-port2.md)有关详细信息。 配置所有发送端口选项。 上**常规**选项卡上，在**传输**部分中，指定**MSMQ**有关**类型**选项。  

2. 上**常规**选项卡上，在**传输**部分中，单击**配置**旁边**类型**。  

3. 在中**MSMQ 传输属性**对话框框中，执行以下操作：  


   |            使用此属性            |                                                                                                                            执行的操作                                                                                                                            |  数据类型  | 默认值 |
   |-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-------------|---------------|
   |              **密码**               |                                                                                                 指定远程队列的密码。 使用具有**用户名**。                                                                                                 |   String    |     空白     |
   |              **用户名**              |                                                             指定远程队列的用户名。 使用具有**密码**。 不能使用远程计算机的本地用户作为该用户名。                                                             |   String    |     空白     |
   |        **确认类型**         | 指定消息队列返回给发送方应用程序的确认消息的类型。 您可以选择多个确认类型。 在确认类型的任何**System.Messaging.AcknowledgeTypes**枚举都可用。 |   String    |     InclusionThresholdSetting      |
   |        **管理队列**         |                                                                                                指定接收确认消息的队列名称。                                                                                                 |   String    |     空白     |
   |              **正文类型**              |                                                                               指定 MSMQ 中的消息正文类型。 有效值为.NET 成员**VarEnum**枚举。                                                                               |     smallint     |     8209      |
   |       **证书指纹**        |    指定用于消息验证的证书的指纹。 将此属性与结合**使用身份验证**属性对消息进行验证。 使用**用户名**并**密码**属性，以访问队列。     |   String    |     空白     |
   |          **目标队列**          |                     指定目标队列。 有关队列的详细信息，请参阅[消息队列队列](../core/message-queuing-queues.md)。 **注意：** 的 URI 发送端口或接收位置不能超过 256 个字符。                      |   String    |     空白     |
   |        **加密算法**         |                                                                                                选择**RC2**， **RC4**，或**None**加密算法。                                                                                                |    Enum     |     InclusionThresholdSetting      |
   | **最大消息大小 （以千字节为单位）** |                                                                                       指定发送到指定的队列的消息的最大消息大小。                                                                                        | UnsignedInt |     1024      |
   |          **消息优先级**           |                                                                                                                    设置消息优先级。                                                                                                                     |    Enum     |    Normal     |
   |             **可恢复**             |                                                                                                  指定是否确保消息的可恢复性。                                                                                                   |   Boolean   |     False     |
   |        **支持分段**         |                                                                                        将此布尔属性值设置为 **，则返回 True**到大于 4 MB 的消息分段。                                                                                         |   Boolean   |     False     |
   |               **超时**               |                                                                    指定等待消息到达目标队列的最长时间。 只有当使用事务时才适用。                                                                     |     smallint     |       0       |
   |            **超时单位**             |                                                                      设置要用于单元**超时**属性。<br /><br /> 选择**天**，**小时**，**分钟**，或者**秒**。                                                                      |    Enum     |     Days      |
   |            **事务性**            |                                                                                               将此值设置为 **，则返回 True**发送消息，如果使用的事务。                                                                                               |   Boolean   |     False     |
   |         **使用身份验证**          |     将此布尔属性值设置为 **，则返回 True**到控制身份验证。 将此属性与结合**证书指纹**属性对消息进行验证。 使用**用户名**并**密码**属性，以访问队列。      |   Boolean   |     False     |
   |        **使用死信队列**        |                                                                                    将此值设置为 **，则返回 True**将消息发送到死信队列，如果发生故障。                                                                                     |   Boolean   |     True      |
   |          **使用日志队列**          |                                                                                   将此值设置为 **，则返回 True**处理消息时保存消息的副本。                                                                                    |   Boolean   |     False     |


4. 单击**确定**并**确定**次以保存设置。  

## <a name="see-also"></a>请参阅  
 [如何配置 MSMQ 接收位置](../core/how-to-configure-an-msmq-receive-location.md)   
 [配置 MSMQ 适配器](../core/configuring-the-msmq-adapter.md)