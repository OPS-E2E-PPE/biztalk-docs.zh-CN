---
title: "如何设置有关 TIBCO 会合接收管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive pipelines, setting
- setting receive pipelines
- pipelines, setting
ms.assetid: d40e0225-0313-4e9b-8d92-464870aabf71
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1dd29852ab41af0d5b1f4ed0d184c158a23b5ae7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-set-receive-pipelines-for-tibco-rendezvous"></a><span data-ttu-id="7fc07-102">如何设置 TIBCO Rendezvous 的接收管道</span><span class="sxs-lookup"><span data-stu-id="7fc07-102">How to Set Receive Pipelines for TIBCO Rendezvous</span></span>
<span data-ttu-id="7fc07-103">用于 TIBCO Rendezvous 的 Microsoft BizTalk 适配器要求设置接收处理程序和接收管道。</span><span class="sxs-lookup"><span data-stu-id="7fc07-103">Microsoft BizTalk Adapter for TIBCO Rendezvous requires that you set the receive handler and receive pipeline.</span></span>  
  
### <a name="to-set-the-pipeline"></a><span data-ttu-id="7fc07-104">若要设置管道</span><span class="sxs-lookup"><span data-stu-id="7fc07-104">To set the pipeline</span></span>  
  
1.  <span data-ttu-id="7fc07-105">设置**接收处理程序**到**BizTalkServerIsolatedHost**列表中。</span><span class="sxs-lookup"><span data-stu-id="7fc07-105">Set the **Receive Handler** to **BizTalkServerIsolatedHost** in the list.</span></span>  
  
2.  <span data-ttu-id="7fc07-106">设置**接收管道**到**XMLReceive**或任何等效的管道。</span><span class="sxs-lookup"><span data-stu-id="7fc07-106">Set the **Receive Pipeline** to **XMLReceive** or any equivalent pipeline.</span></span>  
  
3.  <span data-ttu-id="7fc07-107">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="7fc07-107">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc07-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fc07-108">See Also</span></span>  
 [<span data-ttu-id="7fc07-109">创建 TIBCO 会合接收处理程序</span><span class="sxs-lookup"><span data-stu-id="7fc07-109">Creating TIBCO Rendezvous Receive Handlers</span></span>](../core/creating-tibco-rendezvous-receive-handlers.md)