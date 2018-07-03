---
title: MLLP 接收适配器处理 |Microsoft Docs
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
ms.openlocfilehash: dbb5932d65bce2b17ebfca3645b8c755549b9a9c
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968134"
---
# <a name="mllp-receive-adapter-processing"></a>MLLP 接收适配器处理
最小的较低层协议 (MLLP) 接收适配器支持这两个单向和双向请求响应模式。 适配器侦听和接受连接。  
  
 当 MLLP 接收适配器在双向模式下运行，适配器将不接收新消息从连接直到管道都生成确认 (ACK) 前面的消息。  
  
## <a name="configuration-parameters"></a>配置参数  
 接收处理程序的参数进行配置的 BizTalk 主机级别，并将应用于与之关联的所有 MLLP 接收位置。  
  
|参数|改用|  
|---------------|---------|  
|*最大接受连接限制*|限制并发接收适配器将接受的打开连接数。|  
  
## <a name="acknowledgments-with-the-two-way-mllp-receive-adapter"></a>确认与双向 MLLP 接收适配器  
 当双向 MLLP 接收适配器接收消息时，Microsoft BizTalk Accelerator for HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) 可以生成以下类型的确认：  
  
- HL7 增强提交确认： 在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]同一个连接上发送了提交确认。 它会发送出不同的发送端口上应用程序接受确认。  
  
- 应用程序接受确认： 在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]同一个连接上发送应用程序接受确认。  
  
- 静态确认： 在此方案中，[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]同一个连接上发送确认。  
  
- 生成的确认类型取决于[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]发送消息的参与方的配置资源管理器设置。 字段 MSH 15 和 16 个的单个消息中的值来覆盖此设置。 但是，对于应用程序应为静态 Ack，可以仅将配置设置通过[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器。  
  
## <a name="error-conditions"></a>错误条件  
 当出现错误条件或处于非活动状态时，会发生以下事件：  
  
- 如果禁用该接收位置或[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]关闭，将发生以下情况：  
  
  - 接收位置将不再接受新连接。  
  
  - 对于现有连接，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]完全接收当前消息，然后关闭连接。  
  
- 检测到处于非活动状态时 （无指定的超时内接收位置上接收有效负载数据），适配器将关闭连接。  
  
- 如果[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]收到不完整消息时，接收到的部分被挂起。 接收一条消息 （在之前 EB/CR 和 SB 的下一条消息之间的新连接上第一个 SB) 之外的所有字节数将被忽略。  
  
- 如果管道无法分析该消息，消息仍传送到 MessageBox 数据库，使用提升的属性**ParseError = true**。  
  
- 如果一条消息失败由于没有订阅，或由于在标题中，结构化错误[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]挂起该消息以其原始的"在线"形式 （之前正在分析）。 未将任何订阅失败的常见原因是缺少的升级的属性。 由于[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]挂起未分析的消息**BTS。MessageType**将为空白。  
  
  下表列出了 MLLP 接收适配器返回的错误。  
  
|            事件             |  ID  |                                                                                                          错误条件                                                                                                           |
|------------------------------|------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      **ErrorListening**      | 8448 |                                                   无法绑定到本地套接字 （很可能某些其他本地应用程序使用相同的 IP 地址/端口 ID 组合）。                                                    |
| **ErrorAcceptingConnection** | 8449 | 无法建立与远程方的 TCP 连接。 任一[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]达到最大连接限制，或者资源不足。 |
|  **ErrorSubmittingMessage**  | 8452 |                   MessageBox 数据库不能接受该消息。 任一[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]不可用或资源不足。                   |
|     **ErrorSendingAck**      | 8454 |                                [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] 由于连接不可用，无法返回确认。                                 |
  
## <a name="performance-counters"></a>性能计数器  
 下表列出了 MLLP 适配器使用的性能计数器。  
  
|计数器|含义|  
|-------------|-------------|  
|字节|已接收或发送的所有文档的有效负载的大小。|  
|字节数/秒|已接收或发送的负载的当前吞吐量。|  
|Documents processed|**MLLP 接收**:<br /><br /> 已成功传递到 MessageBox 数据库的文档数。<br /><br /> **MLLP 发送**:<br /><br /> 已成功传递到远程应用程序的文档数。|  
|失败的文档|**MLLP 接收**:<br /><br /> 未成功传送到 MessageBox 数据库的文档数。<br /><br /> **MLLP 发送**:<br /><br /> 未成功传递到远程应用程序的文档数。|  
|连接状态|连接的适配器，状态 1 或 0 (1 = 连接)。|  
  
 性能计数器实例使用以下命名方案：  
  
```  
{recv|trans} : connection name : remote IP address : remote port ID  
```  
  
 MLLP 接收适配器将使用"接收"前缀和 MLLP 发送适配器将使用"事务"。  
  
> [!NOTE]
>  用于确认由发送接收端口 （例如，在双向模式下运行的适配器） 和发送端口 （操作系统相同的套接字连接上接收的确认） 不计。  
  
## <a name="see-also"></a>请参阅  
 [处理用 MLLP 编码的消息](../../adapters-and-accelerators/accelerator-hl7/processing-mllp-encoded-messages.md)   
 [配置参数，以便进行发送和接收适配器](../../adapters-and-accelerators/accelerator-hl7/configuration-parameters-for-send-and-receive-adapters.md)   
 [MLLP 发送适配器处理](../../adapters-and-accelerators/accelerator-hl7/mllp-send-adapter-processing.md)   
 [设置用于接收 ACK 的发送端口](../../adapters-and-accelerators/accelerator-hl7/setting-up-a-send-port-for-receiving-acks.md)