---
title: 方案 1： 调整跟踪数据库的简单 BizTalk 消息 |Microsoft 文档
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
ms.openlocfilehash: 7b9c99c99485e34f95c6f6a75b86170d73678518
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="scenario-1-sizing-the-tracking-database--for-simple-biztalk-messages"></a>方案 1： 调整跟踪数据库的简单 BizTalk 消息
在下图中，一个简单的 BizTalk Server 消息传递而无需进行任何消息转换入和移出 BizTalk Server。  
  
 ![简单的 BizTalk Server 消息 &#45;任何转换](../core/media/simple-bts-message.gif "Simple_BTS_Message")  
  
 **简单的 BizTalk Server 消息的任何转换**  
  
 在应用上一节中的公式前，你将需要收集一些有关这种情况下事实。 在此示例中，我们使用以下方法：  
  
-   消息大小为 5 的 K。  
  
-   没有属性将被提升。  
  
-   一年中接收的消息数是 350 万个。  
  
-   已打开对所有事件的跟踪。 在此方案中有四个事件。 这些事件是：  
  
    -   收到消息 M0  
  
    -   接收端口从消息 M1 的输出  
  
    -   收到消息 M1 传输管道  
  
    -   消息 M2 发送管道的输出  
  
-   在这种情况下创建两个其他消息。 消息 M0 是传入消息，并因此不由 BizTalk Server。 消息 M1 是来自接收端口的输出消息和 M2 是传输端口的输出。 M1 和 M2 由 BizTalk Server 创建。  
  
 将此信息应用于该公式中提供了以下功能：  
  
```  
[(5*252 bytes) + (10*182 bytes) + (0*5(40 bytes + 0) * 3,500,000]/1024/1024  
[(1620 + 1820 + 0) * 3,500,000]/1024/1024 = 10280.61 MB ~ 10.04 GB per year  
```  
  
## <a name="messages-with-a-single-promoted-property"></a>与单个提升的属性的消息  
 让我们看一看此示例中，并添加到方案的一个附加的事实。 你想要将一个字段，大约 10 个字节的大小，提升原始消息中。 升级的最大大小是字段的 256 个字符或大约 256 个字节 （512 字节如果字符都是字段的 Unicode）。  
  
 使用此附加的事实，公式现在如下所示：  
  
```  
[(2*150 bytes) + (4*230 bytes) + (1*2(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 124) * 3,500,000]/1024/1024 = 4486 MB ~ 4.38 GB per year  
```  
  
 如果你想要提升是大小为 10 个字节的其他字段，将为公式：  
  
```  
[(2*150 bytes) + (4*230 bytes) + ((1*2*(52 bytes + 10 bytes) + (1*2*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(300 + 920 + 248) * 3,500,000]/1024/1024 = 4899 MB ~ 4.78 GB per year  
```  
  
 你可以看到，如果将升级在此方案中的单个 10 字节属性，它会将添加额外的 333.79 MB ~ 0.33 GB 每年的大小的 BizTalk 跟踪数据库。  
  
 升级两个 10 字节属性将添加额外的 667.58 MB ~ 0.65 GB 的额外的空间，每年的大小的 BizTalk 跟踪数据库。  
  
## <a name="messages-with-message-body-tracking-activated"></a>使用跟踪的消息正文的消息激活  
 在此示例中，我们还假定我们计划在激活消息正文跟踪。 我们将需要添加消息跟踪上, 一节中所示的第二个公式。 公式将如下所示对于此示例：  
  
```  
[3,500,000 * 4 * 5KB]/1024 = 68359.375 MB ~ 66.75 GB per year  
  
```  
  
 通过添加两个公式的结果，我们可以预计 BizTalk 跟踪数据库将每年到 54.88 GB 增加了大约 54.48 GB。  
  
## <a name="see-also"></a>另请参阅  
 [使用消息变量来调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md)   
 [大小调整跟踪数据库来跟踪消息正文](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [方案 2： 调整跟踪数据库的业务流程中的消息](../core/scenario-2-sizing-the-tracking-database-for-messages-in-orchestrations.md)   
 [方案 4： 调整跟踪数据库的所有消息](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [方案 3： 调整跟踪数据库的消息发送到通讯组列表](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)