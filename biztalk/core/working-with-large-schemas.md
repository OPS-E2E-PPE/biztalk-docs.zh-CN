---
title: 处理大型架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8348036d-6edb-46a3-badd-0223cfe0a92f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f122d56c5a5632a3d6edcb785968c51f487f0b8b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65295371"
---
# <a name="working-with-large-schemas"></a><span data-ttu-id="d9c41-102">处理大型架构</span><span class="sxs-lookup"><span data-stu-id="d9c41-102">Working with Large Schemas</span></span>
<span data-ttu-id="d9c41-103">当架构变得非常大时，可能会发现刷新 XSD 视图变得越来越慢，也可以受到影响的用户界面其他方面的响应。</span><span class="sxs-lookup"><span data-stu-id="d9c41-103">When your schemas become very large, you may find that refreshing the XSD view is increasingly slow and that the response of other aspects of the user interface can be impacted as well.</span></span> <span data-ttu-id="d9c41-104">此问题的解决方案是关闭自动刷新功能，并改为使用手动**刷新**XSD 视图来定期刷新 XSD 视图中的链接。</span><span class="sxs-lookup"><span data-stu-id="d9c41-104">The solution to this issue is to turn off the auto-refresh feature and instead use the manual **Refresh** link in the XSD view to periodically refresh the XSD view.</span></span> <span data-ttu-id="d9c41-105">有关分步说明有关如何启用自动刷新功能关闭，请参阅"打开和关闭自动刷新 XSD 视图的"过程中[管理 XSD 视图](../core/how-to-manage-the-xsd-view.md)。</span><span class="sxs-lookup"><span data-stu-id="d9c41-105">For step-by-step instructions about how turn the auto-refresh feature on an off, see the procedure "To turn automatic refresh of the XSD view on and off" in [Managing the XSD View](../core/how-to-manage-the-xsd-view.md).</span></span>  
  
 <span data-ttu-id="d9c41-106">性能也可能较慢大型架构中有多个附加到的根**架构**节点。</span><span class="sxs-lookup"><span data-stu-id="d9c41-106">Performance may also be slow in large schemas with multiple roots attached to the **schema** node.</span></span> <span data-ttu-id="d9c41-107">设置**根引用**属性可能会增加用户界面中的性能。</span><span class="sxs-lookup"><span data-stu-id="d9c41-107">Setting the **Root Reference** property may increase performance in the user interface.</span></span> <span data-ttu-id="d9c41-108">设置**根引用**提高性能，因为编译器会创建C#类为所有根架构。</span><span class="sxs-lookup"><span data-stu-id="d9c41-108">Setting **Root Reference** improves performance because the compiler creates C# classes for all root schemas.</span></span> <span data-ttu-id="d9c41-109">单个节点意味着创建较少的类。</span><span class="sxs-lookup"><span data-stu-id="d9c41-109">A single root means the creation of fewer classes.</span></span>  
  
 <span data-ttu-id="d9c41-110">**验证实例**可能会出现在用户界面中缓慢，因为始终执行验证的架构验证实例之前。</span><span class="sxs-lookup"><span data-stu-id="d9c41-110">**Validate Instance** may appear slow in the user interface because a validation is always done on the schema before validating the instance.</span></span> <span data-ttu-id="d9c41-111">仅在用户界面中进行架构验证。</span><span class="sxs-lookup"><span data-stu-id="d9c41-111">Schema validation occurs only in the user interface.</span></span> <span data-ttu-id="d9c41-112">设置**根引用**属性还提高了用户界面的性能在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="d9c41-112">Setting the **Root Reference** property also improves user interface performance in this case.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9c41-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9c41-113">See Also</span></span>  
 [<span data-ttu-id="d9c41-114">使用 BizTalk 编辑器</span><span class="sxs-lookup"><span data-stu-id="d9c41-114">Using BizTalk Editor</span></span>](../core/using-biztalk-editor.md)