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
ms.openlocfilehash: 9daf93fd6c925e5412aef3f4e985dd966f576eee
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="changes-in-dehydration-policy-from-biztalk-server-2004"></a>自 BizTalk Server 2004 后在冻结策略中的变化
BizTalk Server 冻结策略已更改，不再[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]到[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]。 之间的差异的介绍[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]和[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]可以按以下的布尔值，确定在冻结汇总[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)](true = 冻结)  
  
```  
Dehydrate = (WaitingHistory == -1 OR WaitingHistory > TestThreshold)  
```  
  
 冻结策略[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]这样次要中已更改。 [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]如果没有等待时间超过 2 始终 dehydrates 接收/延迟/侦听 ***MaxThreshold**。