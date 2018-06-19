---
title: MLLP 接收适配器处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- MLLP-encoded messages, receive adapters
- MLLP adapters, send adapters
- receive adapters
ms.assetid: 03c9a5f6-6f23-454f-8bab-e7c7b6057efa
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 28713e22c37c12ef6f2cb9f8df8d228759d00c8e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207445"
---
# <a name="mllp-receive-adapter-processing"></a>MLLP 接收适配器处理
最小的较低层协议 (MLLP) 接收适配器支持这两个单向和双向请求响应模式。 适配器侦听和接受连接。  
  
 当 MLLP 接收在双向模式下运行的适配器，该适配器将无法收到一封新邮件来自连接直到管道都生成前面的消息，确认 (ACK)。  
  
## <a name="configuration-parameters"></a>配置参数  
 接收处理程序的参数 BizTalk 主机级别进行配置，然后将应用于与之关联的所有 MLLP 接收位置。  
  
|参数|改用|  
|---------------|---------|  
|*最大接受连接限制*|限制并发接收适配器将接受的打开连接数。|  
  
## <a name="acknowledgments-with-the-two-way-mllp-receive-adapter"></a>使用双向 MLLP 确认接收适配器  
 当双向 MLLP 接收适配器会收到一条消息， [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 可以生成以下类型的确认：  
  
-   HL7 增强提交 ACK： 在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送同一个连接上提交的 ACK。 它将发送出不同发送端口上应用程序接受 ACK。  
  
-   应用程序接受 ACK： 在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]同一个连接上发送应用程序接受 ACK。  
  
-   静态 ACK: 在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]同一个连接上发送 ACK。  
  
-   确认生成的类型取决于[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器设置为将消息发送方。 字段 MSH 15 和 16 单条消息中的值可以替代此设置。 但是，对于应用程序应为静态 Ack，可以仅将配置设置通过[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
## <a name="error-conditions"></a>错误条件  
 出现错误条件或处于非活动状态时，会发生以下事件：  
  
-   如果禁用接收位置或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]关闭，将发生以下情况：  
  
    -   接收位置将不再接受新连接。  
  
    -   对于现有连接，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]完全接收当前消息，并且在关闭连接。  
  
-   检测到处于非活动状态时 （没有在指定的超时内接收位置上接收到负载数据），该适配器关闭连接。  
  
-   如果[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]接收不完整消息时，挂起接收的部分。 收到一条消息 （在之前之间 EB/CR 和 SB 的下一条消息的新连接上第一个 SB) 之外的所有字节被都忽略。  
  
-   如果管道无法分析消息，消息仍传递到 MessageBox 数据库，使用提升的属性**ParseError = true**。  
  
-   如果消息无法正常工作，这是由于没有订阅，或在标题中，结构化错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]保持其原来的"网络"格式 （之前正在分析） 挂起消息。 无订阅失败的常见原因是缺少的已提升属性。 由于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]挂起未分析的消息， **BTS。MessageType**将为空。  
  
 下表列出 MLLP 接收适配器返回的错误。  
  
|事件|ID|错误条件|  
|-----------|--------|---------------------|  
|**ErrorListening**|8448|无法绑定到本地的套接字 （很可能某些其他本地应用程序使用相同的 IP 地址/端口 ID 组合）。|  
|**ErrorAcceptingConnection**|8449|无法建立与远程方的 TCP 连接。 任一[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]达到最大连接限制，或者资源不足。|  
|**ErrorSubmittingMessage**|8452|MessageBox 数据库无法接受消息。 任一[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]不可用或资源不足。|  
|**ErrorSendingAck**|8454|[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]无法返回该确认，因为连接不可用。|  
  
## <a name="performance-counters"></a>性能计数器  
 下表列出 MLLP 适配器使用的性能计数器。  
  
|计数器|含义|  
|-------------|-------------|  
|字节|所有文档接收或发送的负载的大小。|  
|字节数/秒|接收或发送的负载的当前吞吐量。|  
|Documents processed|**MLLP 接收**:<br /><br /> 已成功传递到 MessageBox 数据库的文档数。<br /><br /> **MLLP 发送**:<br /><br /> 已成功传递到远程应用程序的文档数。|  
|失败的文档|**MLLP 接收**:<br /><br /> 未成功传递到 MessageBox 数据库的文档数。<br /><br /> **MLLP 发送**:<br /><br /> 未成功传递到远程应用程序的文档数。|  
|连接状态|连接的适配器，状态 1 或 0 (1 = 连接)。|  
  
 性能计数器实例使用以下命名方案：  
  
```  
{recv|trans} : connection name : remote IP address : remote port ID  
```  
  
 如果 MLLP 接收适配器使用的"接收"前缀，并 MLLP 发送适配器使用"trans"。  
  
> [!NOTE]
>  发送的确认接收 （例如，在双向模式下运行的适配器） 的端口和发送端口 （若要在同一套接字连接上接收确认的操作系统） 不会进行计数。  
  
## <a name="see-also"></a>另请参阅  
 [处理 MLLP 编码消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [配置参数发送和接收适配器](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [MLLP 发送适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [设置发送端口用于接收确认](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)