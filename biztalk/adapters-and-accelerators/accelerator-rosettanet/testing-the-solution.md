---
title: "测试解决方案 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing solutions
- private process tutorial, testing solutions
ms.assetid: 90faf959-bac6-4695-8cb7-ecabe52baf1a
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4692035aed17f8432eb2bb515fa75df61be8047f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="testing-the-solution"></a><span data-ttu-id="7bed6-102">测试解决方案</span><span class="sxs-lookup"><span data-stu-id="7bed6-102">Testing the Solution</span></span>
<span data-ttu-id="7bed6-103">在此部分中，你可以测试你完成的解决方案。</span><span class="sxs-lookup"><span data-stu-id="7bed6-103">In this section, you test your complete solution.</span></span> <span data-ttu-id="7bed6-104">在 Fabrikam 解决方案中创建该 LOBWebApplication 工具用于 3A2 PIP 将请求提交给 Contoso LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="7bed6-104">You use the LOBWebApplication tool created in the Fabrikam solution to submit 3A2 PIP requests to the Contoso LOB application.</span></span> <span data-ttu-id="7bed6-105">Contoso 私有业务流程，然后创建 Contoso 基于的 3A2 价格和可用性将请求提交到使用的 SQL 适配器的 ERP 系统[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="7bed6-105">The Contoso private orchestration that you created then submits a Contoso based 3A2 Price and Availability request to the ERP system using the SQL adapter for [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)].</span></span> <span data-ttu-id="7bed6-106">当从 ERP 系统收到响应时，业务流程调用业务规则引擎，以强制实施紧急情况下需要你创建的业务策略。</span><span class="sxs-lookup"><span data-stu-id="7bed6-106">When the response is received from the ERP system, the orchestration calls the Business Rule Engine to enforce the emergency needs business policy that you created.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="7bed6-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="7bed6-107">In This Section</span></span>  
  
-   [<span data-ttu-id="7bed6-108">创建具有 Fabrikam 示例的价格和可用性请求</span><span class="sxs-lookup"><span data-stu-id="7bed6-108">Creating a Price and Availability Request with the Fabrikam Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-price-and-availability-request-with-the-fabrikam-sample.md)