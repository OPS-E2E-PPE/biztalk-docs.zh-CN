---
title: 平面文件消息的结构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 00f2adf6-a47c-498b-b5ae-c6bd55bafceb
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5dfb2e5f159ad3b792393ad828e0addc7907030c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65244120"
---
# <a name="structure-of-a-flat-file-message"></a>平面文件消息的结构
Microsoft 的上下文中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，平面文件实例消息是一个文本文件，可以包含三个逻辑部分： 一个标头、 正文和尾部，按该顺序。 标头和尾部是可选的。 下面的示例演示平面文件实例消息，它包含具有以粗体显示的正文的所有三个部分。  
  
```  
Microsoft Corporation  
One Microsoft Way  
Redmond, WA 98033  
  
TRANSACTION-1111,1  
  
```  
  
 有关以正确区分使用标头、 正文和尾部的平面文件实例消息的平面文件拆装器，必须创建并配置为每个单独的架构。  
  
 数据的不同项的分组中的平面文件实例消息的特定部分，为记录，本身可以包含子记录，并最终称为字段的数据的各个项。 这些记录和字段相互区从每个其他使用两个不同的基本方法之一。 第一种方法，称为位置法，定义要为预先确定的长度，以将数据保持其预期的长度最短的数据项的填充字符的数据的每个项。 第二个方法，名为带分隔符、 使用一个或多个特殊字符来分隔每个项的数据。 此方法不需要使用否则为多余填充字符，但当数据本身包含的字符或字符用作分隔符的序列时引入了一些特殊注意事项。  
  
 本部分的余下部分提供了 BizTalk Server 如何处理标头、 正文和尾部平面文件实例消息中的高级概述，具体而言，如何决定可选部分是否存在，以及它如何分隔的部分入站平面文件实例消息，并将组合出站平面文件实例消息的组成部分。 本部分还提供有关使用位置记录和字段的平面文件实例消息和平面文件实例消息与使用分隔记录和字段之间的区别的其他信息。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [平面文件消息标头](../core/flat-file-message-headers.md)  
  
-   [平面文件消息正文](../core/flat-file-message-bodies.md)  
  
-   [平面文件消息尾部](../core/flat-file-message-trailers.md)  
  
-   [带有位置记录的平面文件消息](../core/flat-file-messages-with-positional-records.md)  
  
-   [带有分隔记录的平面文件消息](../core/flat-file-messages-with-delimited-records.md)  
  
-   [迁移平面文件记录](../core/migrating-flat-file-records.md)