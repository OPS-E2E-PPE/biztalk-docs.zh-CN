---
title: 应用场景 1：为简单 BizTalk 消息调整跟踪数据库的大小 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking database, database size
ms.assetid: 5b8fed48-d9c9-4d1f-a320-d3e23b8b1ec9
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e559869bfb62439bb5f83a97b528ecf6960e123f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65308615"
---
# <a name="scenario-1-sizing-the-tracking-database--for-simple-biztalk-messages"></a>应用场景 1：为简单 BizTalk 消息调整跟踪数据库的大小
在下图中，一个简单的 BizTalk Server 消息传递而无需进行任何消息转换入和移出 BizTalk Server。  
  
 ![简单的 BizTalk Server 消息&#45;无转换](../core/media/simple-bts-message.gif "Simple_BTS_Message")  
  
 **简单的 BizTalk Server 消息-无转换**  
  
 在应用上一节中的公式之前，需要收集一些有关此方案的事实。 在此示例中，我们使用以下方法：  
  
- 消息大小为 5 个 K。  
  
- 将不升级任何属性。  
  
- 一年中接收的消息数为 350 万条。  
  
- 跟踪被打开的所有事件。 在此方案中有四个事件。 这些事件是：  
  
  -   接收消息 M0  
  
  -   输出消息 M1 从接收端口  
  
  -   接收消息 M1 通过传输管道  
  
  -   通过输出消息 M2 发送管道  
  
- 在此方案中创建两个其他消息。 消息 M0 是传入的消息，因此不创建由 BizTalk Server。 消息 M1 是从接收端口输出消息，M2 是从传输端口输出。 由 BizTalk Server 创建 M1 和 M2。  
  
  将这些信息应用到公式中提供了以下功能：  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-with-a-single-promoted-property"></a>具有单个升级属性的消息  
 让我们看看此示例中，并将一个事实添加到方案。 你想要升级单个字段，约为 10 字节的大小，原始消息中。 已升级的最大大小是字段的 256 个字符或大约 256 个字节 （512 字节 Unicode 字符是否）。  
  
 与此事实，公式将如下所示：  
  
```  
[(2*150 bytes) + (4*230 bytes) + (1*2(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 124) * 3,500,000]/1024/1024 = 4486 MB ~ 4.38 GB per year  
```  
  
 如果您想要提升为大小的 10 个字节的附加字段，公式为：  
  
```  
[(2*150 bytes) + (4*230 bytes) + ((1*2*(52 bytes + 10 bytes) + (1*2*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 248) * 3,500,000]/1024/1024 = 4899 MB ~ 4.78 GB per year  
```  
  
 您可以看到，如果升级一个 10 字节属性在此方案中，它会将添加额外的 333.79 MB ~ 0.33 GB 每年的大小的 BizTalk 跟踪数据库。  
  
 升级两个 10 字节属性将添加额外的 667.58 MB ~ 0.65 GB 的 BizTalk 跟踪数据库每年的大小的额外空间。  
  
## <a name="messages-with-message-body-tracking-activated"></a>消息正文跟踪的消息激活  
 在此示例中，我们还假设我们计划在激活消息正文跟踪。 我们将需要添加消息跟踪，在上一节中所示的第二个公式。 公式将如下所示，对于此示例：  
  
```  
[3,500,000 * 4 * 5KB]/1024 = 68359.375 MB ~ 66.75 GB per year  
  
```  
  
 通过添加两个等式的结果，我们可以估计 BizTalk 跟踪数据库的每年为 54.88 GB 增长了大约 54.48 GB。  
  
## <a name="see-also"></a>请参阅  
 [使用消息变量调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md)   
 [调整跟踪数据库来跟踪消息正文大小](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [方案 2：为业务流程中消息调整跟踪数据库的大小](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [方案 4:为所有消息调整跟踪数据库的大小](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [方案 3:为发送到分发列表的消息调整跟踪数据库的大小](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)