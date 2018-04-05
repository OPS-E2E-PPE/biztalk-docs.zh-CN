---
title: 实现突出显示的业务流程管理解决方案 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- process management solution tutorial, implementing
ms.assetid: 3558db0e-d7f6-4c10-bd58-1601bd44e73f
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: decad6f68398cca2d0b88c4904d3e63c075749b3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="implementation-highlights-of-the-business-process-management-solution"></a><span data-ttu-id="3b823-102">实现突出显示的业务流程管理解决方案</span><span class="sxs-lookup"><span data-stu-id="3b823-102">Implementation Highlights of the Business Process Management Solution</span></span>
<span data-ttu-id="3b823-103">本部分介绍更多详细信息中的解决方案的实现相关的元素。</span><span class="sxs-lookup"><span data-stu-id="3b823-103">This section describes the implementation-related elements of the solution in greater detail.</span></span> <span data-ttu-id="3b823-104">这些元素包括业务规则框架的处理阶段数如何**OrderManager**通信的处理阶段，使用**OrderHandler**对象，以及如何应用程序使用 Ops 适配器。</span><span class="sxs-lookup"><span data-stu-id="3b823-104">These elements include the Business Rules Framework, the number of processing stages, how the **OrderManager** communicates with the processing stages, the use of the **OrderHandler** object, and how the application uses the Ops Adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3b823-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="3b823-105">In This Section</span></span>  
  
-   [<span data-ttu-id="3b823-106">使用业务规则验证</span><span class="sxs-lookup"><span data-stu-id="3b823-106">Validation with Business Rules</span></span>](../core/validation-with-business-rules.md)  
  
-   [<span data-ttu-id="3b823-107">处理阶段数</span><span class="sxs-lookup"><span data-stu-id="3b823-107">Number of Processing Stages</span></span>](../core/number-of-processing-stages.md)  
  
-   [<span data-ttu-id="3b823-108">反直接合作伙伴绑定</span><span class="sxs-lookup"><span data-stu-id="3b823-108">Inverse Direct Partner Binding</span></span>](../core/inverse-direct-partner-binding.md)  
  
-   [<span data-ttu-id="3b823-109">OrderBroker 和 OrderManager 之间的通信</span><span class="sxs-lookup"><span data-stu-id="3b823-109">Communication between OrderBroker and OrderManager</span></span>](../core/communication-between-orderbroker-and-ordermanager.md)  
  
-   [<span data-ttu-id="3b823-110">在业务流程管理解决方案中有效地使用 SSO</span><span class="sxs-lookup"><span data-stu-id="3b823-110">Using SSO Efficiently in the Business Process Management Solution</span></span>](../core/using-sso-efficiently-in-the-business-process-management-solution.md)  
  
-   [<span data-ttu-id="3b823-111">使用顺序处理程序对象与后端系统进行通信</span><span class="sxs-lookup"><span data-stu-id="3b823-111">Using the Order Handler Object to Communicate with Backend Systems</span></span>](../core/using-the-order-handler-object-to-communicate-with-backend-systems.md)  
  
-   [<span data-ttu-id="3b823-112">合并 XML 文档</span><span class="sxs-lookup"><span data-stu-id="3b823-112">Merging XML Documents</span></span>](../core/merging-xml-documents.md)  
  
-   [<span data-ttu-id="3b823-113">Ops 适配器</span><span class="sxs-lookup"><span data-stu-id="3b823-113">The Ops Adapter</span></span>](../core/the-ops-adapter.md)  
  
-   [<span data-ttu-id="3b823-114">Recaller 对象</span><span class="sxs-lookup"><span data-stu-id="3b823-114">The Recaller Object</span></span>](../core/the-recaller-object.md)