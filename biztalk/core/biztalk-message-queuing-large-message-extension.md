---
title: BizTalk 消息队列大消息扩展 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Message Queuing Large Message Extension
- utilities, BizTalk Message Queuing Large Message Extension
ms.assetid: 5d6892d3-fda8-41a3-8111-d28c11bd71fb
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb50b2e3270644a73dd3fb4f3b11af4da2dc0f72
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37020507"
---
# <a name="biztalk-message-queuing-large-message-extension"></a>BizTalk 消息队列大消息扩展
本地消息队列无法处理的消息其正文大于 4megabytes (MB)。 但是，Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 包含的本地消息队列的加载项可处理大于 4 MB 的消息。 此加载项以 Mqrtlarge.dll 文件，交付，并公开**MQSendLargeMessage**并**MQReceiveLargeMessage**应用程序的编程接口 (Api) 和类似的 COM 模型。 这些函数作为标准消息队列 Api，实现**MQSendMessage**并**MQReceiveMessage**分别。  

 若要进行大消息交换，消息队列计算机必须已安装了 Mqrtlarge.dll 文件，并且消息队列应用程序应该使用加载项 API。 否则，完整的消息将进行分片。  

 **在 SDK 中的位置**  

 \<*安装路径*\>\SDK\ Mqrtlarge.dll  

 **文件清单**  

 下表显示了本实用程序使用的文件及其用途。  


|    文件    |                                                                                                                                                                                              Description                                                                                                                                                                                               |
|---------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Mqrtlarge.dll | 公开的 Win32 动态链接库**MQSendLargeMessage**并**MQReceiveLargeMessage**。<br /><br /> 标头文件位于*\<安装路径\>* \SDK\Include 目录。 **注意：** 必须安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 64 位版本的 Windows，才能访问 64 位版本的 Mqrtlarge.dll。 |

 **使用此实用程序**  

 通过以下过程运行 Mqrtlarge.dll 文件。  

### <a name="to-use-the-mqrtlargedll-file"></a>使用 Mqrtlarge.dll 文件  

1. > [!NOTE]
   >  对于 MSMQ 解决方案未使用 BizTalk Server，MQRTLarge.dll 仍可正常运行。 但是，这不的建议的配置，Microsoft 支持，并且如果在 BizTalk Server 环境外部使用，可能会发生意外的结果。  

    将文件 Mqrtlarge.dll 添加到未安装 BizTalk Server 的计算机中。 消息队列使用 Mqrtlarge.dll 向 BizTalk Server 发送消息，或从 BizTalk Server 接收消息。  

2. 若要访问 Mqrtlarge.dll 文件中的 API，可在适当应用程序中添加一个对 Mqrtlarge.dll 文件的引用，该应用程序是在其他计算机与 BizTalk 消息队列终结点之间发送或接收消息的应用程序。  

   **备注**  

   大消息被发送到标准消息队列（也叫作 MSMQ）。 在这类队列中只应使用大消息 API，尽管这不是强制性的。  

   您仍然可以使用**MQSendMessage**将消息发送到向其发送大消息的队列。 同样，可以使用**MQReceiveMessage**从这类队列接收消息，但因为它可能会影响性能的不建议**MQReceiveLargeMessage** API。  

   为了进行恢复，建议你使用**DEAD_LETTER**日记功能。  

   **碎片**  

   通常情况下，大消息会分段为多个消息，每个消息都小于 4 MB。 只会将正文分段，了解这一点很重要。 其他属性随每个片断一起发送。  

   分段的数量由消息的大小和片断的大小确定。 片断大小可以由文件 Mqrtlarge.dll 或 BizTalk 消息队列的相应部分自动确定。 应用程序还可以显式指定片断大小。  

   请注意，大消息扩展要求通过添加固定大小的其他内部数据来扩展消息。  

   **PROPID_M_EXTENSION**  

   可以使用**PROPID_M_EXTENSION/PROPID_M_EXTENSION_LEN**属性对消息进行签名。 签名由 40 个字节 (B) 组成 。 下表显示了签名片断。  

|Description|Size|  
|-----------------|----------|  
|表示是否已发送此消息使用的全局唯一标识符 (GUID) **MQSendLargeMessage**|16 B|  
|消息的 GUID： 普遍适用于消息的所有部分的唯一的每个大型消息 ID|16 B|  
|大消息的总大小|4 B|  
|部分号|2 B|  
|消息部分数|2 B|  

 若要使用的决定**PROPID_M_EXTENSION**还有其他用途。 Microsoft Host Integration Server MSMQ-MQSeries Bridge 使用此属性传递一个结构，该结构包含那些在 MQSeries 和消息队列消息之间不直接映射的属性。 将消息发送到 MQSeries，或从 MQSeries 发送消息的应用程序显式或隐式使用此结构。 当接收应用程序从队列接收到消息时，消息队列能够生成确认信息。 确认信息被发送到由发送应用程序指定的队列中。 对于大消息，仅为大消息的最后部分发送此确认信息。  

## <a name="see-also"></a>请参阅  
 [SDK 中的实用工具](../core/utilities-in-the-sdk.md)