---
title: 测试解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing solutions
- private process tutorial, testing solutions
ms.assetid: 90faf959-bac6-4695-8cb7-ecabe52baf1a
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7b43ab300fefbe1916b58e9c606c2541dfd0a10e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280599"
---
# <a name="testing-the-solution"></a><span data-ttu-id="c63b9-102">测试解决方案</span><span class="sxs-lookup"><span data-stu-id="c63b9-102">Testing the Solution</span></span>
<span data-ttu-id="c63b9-103">在本部分中，测试完整的解决方案。</span><span class="sxs-lookup"><span data-stu-id="c63b9-103">In this section, you test your complete solution.</span></span> <span data-ttu-id="c63b9-104">使用 LOBWebApplication 工具创建 Fabrikam 解决方案中提交 3A2 PIP 请求到 Contoso LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="c63b9-104">You use the LOBWebApplication tool created in the Fabrikam solution to submit 3A2 PIP requests to the Contoso LOB application.</span></span> <span data-ttu-id="c63b9-105">然后创建 Contoso 专用业务流程将提交到 ERP 系统为 BizTalk Server 使用 SQL 适配器的 Contoso 基于的 3A2 价格与可用性请求。</span><span class="sxs-lookup"><span data-stu-id="c63b9-105">The Contoso private orchestration that you created then submits a Contoso based 3A2 Price and Availability request to the ERP system using the SQL adapter for BizTalk Server.</span></span> <span data-ttu-id="c63b9-106">当从 ERP 系统收到响应时，业务流程调用业务规则引擎，以强制实施紧急情况下需要你创建的业务策略。</span><span class="sxs-lookup"><span data-stu-id="c63b9-106">When the response is received from the ERP system, the orchestration calls the Business Rule Engine to enforce the emergency needs business policy that you created.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c63b9-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="c63b9-107">In This Section</span></span>  
  
-   [<span data-ttu-id="c63b9-108">使用 Fabrikam 示例创建价格和可用性请求</span><span class="sxs-lookup"><span data-stu-id="c63b9-108">Creating a Price and Availability Request with the Fabrikam Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-a-price-and-availability-request-with-the-fabrikam-sample.md)