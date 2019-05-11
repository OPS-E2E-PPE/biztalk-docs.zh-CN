---
title: 应用场景 2：为业务流程中消息调整跟踪数据库的大小 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: d1cfb8b9-d4e2-4069-8db3-18f72358652b
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e3a62df0431611c294a123835d7cc2faddca474
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308611"
---
# <a name="scenario-2-sizing-the-tracking-database--for-messages-in-orchestrations"></a>应用场景 2：为业务流程中消息调整跟踪数据库的大小
让我们看一下示例，其中包括业务流程。 下图显示了整个业务流程。 在此方案中，一条消息到 BizTalk Server，通过业务流程发送、 更改在业务流程内并且然后发出通过发送端口。  
  
 ![BizTalk Server 消息进程](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")  
  
 **BizTalk Server 消息处理**  
  
 下面是一些有关此方案中的事实：  
  
- 消息大小为 5 个 K。  
  
- 我们不会升级任何属性。  
  
- 我们在一年中收到的消息数为 350 万条。  
  
- 跟踪被打开的所有事件。 在此方案中有六个事件：  
  
  -   接收消息 M0  
  
  -   输出消息 M1 从接收端口  
  
  -   接收消息 M1 由业务流程  
  
  -   输出消息 M2 从业务流程  
  
  -   通过接收消息 M2 发送端口  
  
  -   输出消息 M3 的发送管道  
  
- 在此方案中创建其他三个消息。 消息 M0 是传入的消息，因此不创建由 BizTalk Server。 消息 M1 是输出消息从接收端口，M2 是从业务流程，输出消息，M3 是从传输端口输出消息。  
  
  将此信息应用到该公式会得到以下结果：  
  
```  
[(3*150 bytes) + (6*230 bytes) + (0*0(52 bytes + 0) * 3,500,000]/1024/1024  
[(450 + 1380 + 0) * 3,500,000]/1024/1024 = 6108 MB ~ 5.96 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-a-single-promoted-property"></a>业务流程中具有单个升级属性的消息  
 现在让我们来升级单个字段在此方案中，如前面的示例中所示。 升级的属性是约为 10 字节的大小。 公式现在如下所示：  
  
```  
[((3*150 bytes) + (6*230 bytes) + (1*3*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 186) * 3,500,000]/1024/1024 = 6729 MB ~ 6.57 GB per year  
```  
  
 如果你需要升级的其他属性，为 20 字节的大小，该公式现在如下所示：  
  
```  
[(3*150 bytes) + (6*230 bytes) + ((1*3*(52 bytes + 10 bytes) + (1*3*(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 372) * 3,500,000]/1024/1024 = 7350 MB ~ 7.18 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-message-body-tracking-activated"></a>与消息正文跟踪的业务流程中的消息激活  
 如果你想要允许消息跟踪，所需的额外空间的计算结果等于结果中前面的方案或 50.1 GB 每年。  
  
## <a name="see-also"></a>请参阅  
 [使用消息变量调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md)   
 [调整跟踪数据库来跟踪消息正文大小](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [方案 1：为简单 BizTalk 消息调整跟踪数据库的大小](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [方案 4:为所有消息调整跟踪数据库的大小](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [方案 3:为发送到分发列表的消息调整跟踪数据库的大小](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)