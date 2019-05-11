---
title: 在 JD Edwards OneWorld 适配器中设置字符串对齐 |Microsoft Docs
description: 更新 jdearglist 文件以在 BizTalk Server 业务流程中使用 JD Edwards OneWorld 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f33941e997315a5e91e5c99f4e6dc4bd0d2b7aa
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393247"
---
# <a name="set-string-justification-in-jdearglist"></a><span data-ttu-id="d10af-103">在 Jdearglist 中设置字符串对齐</span><span class="sxs-lookup"><span data-stu-id="d10af-103">Set string Justification in Jdearglist</span></span>

## <a name="overview"></a><span data-ttu-id="d10af-104">概述</span><span class="sxs-lookup"><span data-stu-id="d10af-104">Overview</span></span>
<span data-ttu-id="d10af-105">若要配置某些字符串参数，右对齐 （并且向左填充） 在 JD Edwards OneWorld jdearglist.txt 文件中，您必须知道你想要访问; 哪些业务函数具体而言，您必须知道你想要调用业务函数中的哪些字段。</span><span class="sxs-lookup"><span data-stu-id="d10af-105">To configure certain string arguments as right-justified (and left padded) in the JD Edwards OneWorld jdearglist.txt file, you must know what business function you want to access; specifically, you must know which fields in the business function you want to call.</span></span>  
  
 <span data-ttu-id="d10af-106">在业务流程中生成的绑定 （架构） 之前，必须更新 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="d10af-106">You must update the jdearglist.txt before you generate the bindings (schemas) in the orchestration.</span></span> <span data-ttu-id="d10af-107">用于更新 jdearglist.txt 文件的说明所述[处理字符串值](../core/handling-string-values1.md)。</span><span class="sxs-lookup"><span data-stu-id="d10af-107">The instructions for updating the jdearglist.txt file are outlined in [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
 <span data-ttu-id="d10af-108">如果审核日志中收到 jdearglist.txt 警告消息，它将通知您缺少指定 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="d10af-108">If you receive a jdearglist.txt warning message in the audit log, it informs you that the jdearglist.txt is missing.</span></span> <span data-ttu-id="d10af-109">如果运行 SalesOrder 或 PurchaseOrder 业务函数，该文件必须在你的路径，或它将无法工作。</span><span class="sxs-lookup"><span data-stu-id="d10af-109">If you run the SalesOrder or PurchaseOrder business functions, you must have the file in your PATH, or it will not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d10af-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="d10af-110">See Also</span></span>  
[<span data-ttu-id="d10af-111">使用 BizTalk Server 异常处理</span><span class="sxs-lookup"><span data-stu-id="d10af-111">Use BizTalk Server Exception Handling</span></span>](using-biztalk-server-exception-handling1.md)