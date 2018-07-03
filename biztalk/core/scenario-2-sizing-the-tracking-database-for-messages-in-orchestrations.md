---
title: 方案 2： 调整跟踪数据库的业务流程中消息大小 |Microsoft Docs
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
ms.openlocfilehash: 9df587902f8b527e82d202221211b8c09cf2f418
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976982"
---
# <a name="scenario-2-sizing-the-tracking-database--for-messages-in-orchestrations"></a>方案 2：调整业务流程中消息的跟踪数据库
我们将介绍一个包含业务流程的示例。 下图显示了整个业务流程。 在此方案中，通过业务流程发送传递到 BizTalk Server 中的消息并在该业务流程内对其进行更改，然后通过发送端口发送出该消息。  
  
 ![BizTalk Server 消息进程](../core/media/biztalk-server-message-process.gif "BizTalk_Server_Message_Process")  
  
 **BizTalk Server 消息处理**  
  
 以下为有关此方案的一些实际信息：  
  
- 消息大小为 5 个 K。  
  
- 我们不会升级任何属性。  
  
- 一年内接收的消息数为 350 万条。  
  
- 已打开对所有事件的跟踪。 此方案包含以下六个事件：  
  
  -   接收消息 M0  
  
  -   输出消息 M1 从接收端口  
  
  -   通过业务流程接收消息 M1  
  
  -   从业务流程输出消息 M2  
  
  -   通过发送端口接收消息 M2  
  
  -   通过发送管道输出消息 M3  
  
- 此方案中创建了其他三个消息。 消息 M0 是传入的消息，因此不创建由 BizTalk Server。 消息 M1 是从接收端口输出的消息，M2 是从业务流程输出的消息，M3 是从传输端口输出的消息。  
  
  将此信息应用到该公式会得到以下结果：  
  
```  
[(3*150 bytes) + (6*230 bytes) + (0*0(52 bytes + 0) * 3,500,000]/1024/1024  
[(450 + 1380 + 0) * 3,500,000]/1024/1024 = 6108 MB ~ 5.96 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-a-single-promoted-property"></a>业务流程中具有单个升级属性的消息  
 在此方案中，请按照之前示例中所执行的操作来升级单个字段。 升级的属性大小约为 10 字节。 公式现在如下所示：  
  
```  
[((3*150 bytes) + (6*230 bytes) + (1*3*(52 bytes + 10 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 186) * 3,500,000]/1024/1024 = 6729 MB ~ 6.57 GB per year  
```  
  
 如果需要另外升级一个大小为 20 字节的属性，则公式将如下所示：  
  
```  
[(3*150 bytes) + (6*230 bytes) + ((1*3*(52 bytes + 10 bytes) + (1*3*(52 bytes + 20 bytes)) * 3,500,000]/1024/1024  
[(450 + 1380 + 372) * 3,500,000]/1024/1024 = 7350 MB ~ 7.18 GB per year  
```  
  
## <a name="messages-in-orchestrations-with-message-body-tracking-activated"></a>业务流程中已激活消息正文跟踪的消息  
 若要允许消息跟踪，则所需额外空间的计算结果应与之前方案中的结果相同，或为每年 50.1 GB。  
  
## <a name="see-also"></a>请参阅  
 [使用消息变量调整跟踪数据库的大小](../core/using-message-variables-to-size-the-tracking-database.md)   
 [调整跟踪数据库来跟踪消息正文大小](../core/sizing-the-tracking-database-to-track-message-bodies.md)   
 [方案 1： 调整简单 BizTalk 消息的大小跟踪数据库](../core/scenario-1-sizing-the-tracking-database-for-simple-biztalk-messages.md)   
 [方案 4： 为所有消息调整跟踪数据库](../core/scenario-4-sizing-the-tracking-database-for-all-messages.md)   
 [方案 3：为发送到通讯组列表的消息调整跟踪数据库的大小](../core/scenario-3-size-the-tracking-database-for-messages-sent-to-distribution-lists.md)