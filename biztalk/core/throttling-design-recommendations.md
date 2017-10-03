---
title: "限制设计建议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- host throttling, best practices
- best practices, host throttling
ms.assetid: c3332bb4-abfd-4961-9562-5a3a930d4380
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ebc5fff27bf634480c1de3c5e28f1184e0a8d046
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="throttling-design-recommendations"></a><span data-ttu-id="e4cc1-102">阻止设计建议</span><span class="sxs-lookup"><span data-stu-id="e4cc1-102">Throttling Design Recommendations</span></span>
<span data-ttu-id="e4cc1-103">本部分提供有关如何设计解决方案以利用阻止功能的建议。</span><span class="sxs-lookup"><span data-stu-id="e4cc1-103">This section provides recommendations on how to design a solution to take advantage of throttling.</span></span> <span data-ttu-id="e4cc1-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中限制引擎增强功能可能很大程度上影响 BizTalk Server 的性能</span><span class="sxs-lookup"><span data-stu-id="e4cc1-104">The throttling engine enhancements in [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] may significantly impact the performance of BizTalk Server</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e4cc1-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="e4cc1-105">In This Section</span></span>  
  
-   [<span data-ttu-id="e4cc1-106">如何避免限制关联的消息</span><span class="sxs-lookup"><span data-stu-id="e4cc1-106">How to Avoid Throttling Correlated Messages</span></span>](../core/how-to-avoid-throttling-correlated-messages.md)  
  
-   [<span data-ttu-id="e4cc1-107">调整限制阈值： 何时和为何</span><span class="sxs-lookup"><span data-stu-id="e4cc1-107">Adjusting Throttling Thresholds: When and Why</span></span>](../core/adjusting-throttling-thresholds-when-and-why.md)  
  
-   [<span data-ttu-id="e4cc1-108">挂起的消息都包含在数据库限制阈值中的消息计数</span><span class="sxs-lookup"><span data-stu-id="e4cc1-108">Suspended Messages are Included in the Message Count in Database Throttling Threshold</span></span>](../core/suspended-messages-included-in-message-count-in-database-throttling-threshold.md)