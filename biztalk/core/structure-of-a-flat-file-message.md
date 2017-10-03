---
title: "平面文件消息的结构 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 00f2adf6-a47c-498b-b5ae-c6bd55bafceb
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: badb8aacf6f2ed8ce9e38f1ea6bbe432a1d3b89e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="structure-of-a-flat-file-message"></a>平面文件消息的结构
Microsoft 的上下文中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，平面文件实例消息是一个文本文件，可以包含三个逻辑部分： 标头、 正文和尾部，按此顺序。 其中，头部和尾部均是可选的。 以下示例显示的平面文件实例消息由这三个部分组成（其正文部分以粗体显示）：  
  
```  
Microsoft Corporation  
One Microsoft Way  
Redmond, WA 98033  
  
TRANSACTION-1111,1  
  
```  
  
 为使平面文件拆装器可正确区分平面文件实例消息的头部、正文和尾部，您必须为每部分分别创建和配置单独的架构。  
  
 在平面文件实例消息的特定部分中，不同的数据项将分成不同的记录，而记录本身可包含子记录，并最终包含各个数据项（称为字段）。 使用以下两种不同的基本方法之一，可以将这些记录和字段相互区分开。 第一种方法（称为位置法）将每个数据项定义为具有预先确定的长度，并使用填充字符将较短的数据项加长到所需长度。 第二种方法（称为分隔法）使用一个或多个特殊字符将数据项彼此分隔开。 此方法不需要使用其他方法所需的多余填充字符，但当数据本身包含已用作分隔符的字符或字符序列时，将需要注意某些特殊事项。  
  
 本部分的其余内容对于 BizTalk Server 如何处理平面文件实例消息的头部、正文和尾部提供了高级概述，具体来说，即介绍了 BizTalk Server 将如何决定是否使用可选部分，以及如何分隔入站平面文件实例消息的各个部分和如何将出站平面文件实例消息的各个部分组合起来。 本部分还提供了有关使用位置记录和字段的平面文件实例消息与使用分隔记录和字段的平面文件实例消息之间的差异的其他信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [平面文件消息标头](../core/flat-file-message-headers.md)  
  
-   [平面文件消息正文](../core/flat-file-message-bodies.md)  
  
-   [平面文件消息拖车安排](../core/flat-file-message-trailers.md)  
  
-   [包含的位置记录的平面文件消息](../core/flat-file-messages-with-positional-records.md)  
  
-   [分隔记录的平面文件消息](../core/flat-file-messages-with-delimited-records.md)  
  
-   [迁移的平面文件记录](../core/migrating-flat-file-records.md)