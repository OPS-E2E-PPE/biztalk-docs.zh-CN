---
title: "从 BizTalk Server 2004 冻结策略中的更改 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c760bffe-5f64-4eb2-bc23-89d7c9310f39
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 167c53d953369d7b35138995b4f38ad8994c18cb
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="changes-in-dehydration-policy-from-biztalk-server-2004"></a>自 BizTalk Server 2004 后在冻结策略中的变化
BizTalk Server 冻结策略已更改，不再[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]给 BizTalk Server。 之间的差异的介绍[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]和 BizTalk Server 可以按以下的布尔值，确定在冻结汇总[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)](true = 冻结)  
  
```  
Dehydrate = (WaitingHistory == -1 OR WaitingHistory > TestThreshold)  
```  
  
 BizTalk Server 的冻结策略已更改此次要的方式。 BizTalk Server 始终 dehydrates 接收/延迟/侦听是否存在等待时间超过 2 ***MaxThreshold**。