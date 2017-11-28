---
title: "在 Jdearglist 中设置字符串理由 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, setting string justification
- strings, configuring
- strings, right-justified
ms.assetid: 1c9b013a-839d-45f1-9da0-c96fd45b25e5
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: daecf4101ebf5dc8964562dc7f385d41279a3401
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="setting-string-justification-in-jdearglist"></a><span data-ttu-id="e7bd8-102">在 Jdearglist 中设置字符串对齐</span><span class="sxs-lookup"><span data-stu-id="e7bd8-102">Setting String Justification in Jdearglist</span></span>
<span data-ttu-id="e7bd8-103">若要在 JD Edwards OneWorld jdearglist.txt 文件中将某些字符串参数配置为右对齐（并且向左填充），您必须知道要访问哪一个业务函数；尤其必须了解要调用业务函数中的哪些字段。</span><span class="sxs-lookup"><span data-stu-id="e7bd8-103">To configure certain string arguments as right-justified (and left padded) in the JD Edwards OneWorld jdearglist.txt file, you must know what business function you want to access; specifically, you must know which fields in the business function you want to call.</span></span>  
  
 <span data-ttu-id="e7bd8-104">您必须先更新该 jdearglist.txt，然后在业务流程中生成绑定（架构）。</span><span class="sxs-lookup"><span data-stu-id="e7bd8-104">You must update the jdearglist.txt before you generate the bindings (schemas) in the orchestration.</span></span> <span data-ttu-id="e7bd8-105">更新 jdearglist.txt 文件的说明所述[处理字符串值](../core/handling-string-values1.md)。</span><span class="sxs-lookup"><span data-stu-id="e7bd8-105">The instructions for updating the jdearglist.txt file are outlined in [Handling String Values](../core/handling-string-values1.md).</span></span>  
  
 <span data-ttu-id="e7bd8-106">如果在审核日志中收到 jdearglist.txt 警告消息，则是通知您缺少 jdearglist.txt。</span><span class="sxs-lookup"><span data-stu-id="e7bd8-106">If you receive a jdearglist.txt warning message in the audit log, it informs you that the jdearglist.txt is missing.</span></span> <span data-ttu-id="e7bd8-107">如果运行 SalesOrder 或 PurchaseOrder 业务函数，您的路径中必须具有该文件，否则它将不会运行。</span><span class="sxs-lookup"><span data-stu-id="e7bd8-107">If you run the SalesOrder or PurchaseOrder business functions, you must have the file in your PATH, or it will not work.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7bd8-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e7bd8-108">See Also</span></span>  
 [<span data-ttu-id="e7bd8-109">管理 BizTalk 适配器用于博士 Edwards OneWorld</span><span class="sxs-lookup"><span data-stu-id="e7bd8-109">Administering BizTalk Adapter for JD Edwards OneWorld</span></span>](../core/administering-biztalk-adapter-for-jd-edwards-oneworld.md)