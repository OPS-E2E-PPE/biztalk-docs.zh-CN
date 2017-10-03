---
title: "测试 Double 操作教程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- double action tutorial, testing solutions
- testing solutions
ms.assetid: e5bc66e6-333e-4d94-ae1e-345ab45c83e5
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 807308623780e029fff571a36dc703de0f79460d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="testing-the-double-action-tutorial"></a><span data-ttu-id="fdbb4-102">测试 Double 操作教程</span><span class="sxs-lookup"><span data-stu-id="fdbb4-102">Testing the Double Action Tutorial</span></span>
<span data-ttu-id="fdbb4-103">在本节中，将使用在前几节创建的 Contoso 和 Fabrikam 解决方案来测试四种不同的合作伙伴接口流程 (PIP)：0C2、0C4、3A2 和 3A4。</span><span class="sxs-lookup"><span data-stu-id="fdbb4-103">In this section, you use the Contoso and Fabrikam solutions that you created in the earlier sections to test four different Partner Interface Processes (PIPs): 0C2, 0C4, 3A2 and 3A4.</span></span> <span data-ttu-id="fdbb4-104">您将使用 Fabrikam 计算机上的 LOBWebApplication 生成请求。</span><span class="sxs-lookup"><span data-stu-id="fdbb4-104">You use the LOBWebApplication on the Fabrikam computer to make the request.</span></span> <span data-ttu-id="fdbb4-105">系统将使用增强的通信通道向 Contoso 计算机发送此请求。</span><span class="sxs-lookup"><span data-stu-id="fdbb4-105">The system will send the request using an enhanced communication channel to the Contoso computer.</span></span> <span data-ttu-id="fdbb4-106">双操作业务流程将根据您使用的 PIP 生成适当的响应。</span><span class="sxs-lookup"><span data-stu-id="fdbb4-106">The Double Action orchestration will generate an appropriate response based on the PIP you use.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fdbb4-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="fdbb4-107">In This Section</span></span>  
  
-   [<span data-ttu-id="fdbb4-108">步骤 1： 提交 0 C 2 请求</span><span class="sxs-lookup"><span data-stu-id="fdbb4-108">Step 1: Submitting a 0C2 Request</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-submitting-a-0c2-request.md)  
  
-   [<span data-ttu-id="fdbb4-109">步骤 2： 提交 0 C 4 查询</span><span class="sxs-lookup"><span data-stu-id="fdbb4-109">Step 2: Submitting a 0C4 Query</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-submitting-a-0c4-query.md)  
  
-   [<span data-ttu-id="fdbb4-110">步骤 3： 提交 3A2 请求</span><span class="sxs-lookup"><span data-stu-id="fdbb4-110">Step 3: Submitting a 3A2 Request</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-submitting-a-3a2-request.md)  
  
-   [<span data-ttu-id="fdbb4-111">步骤 4： 提交 3A4 请求</span><span class="sxs-lookup"><span data-stu-id="fdbb4-111">Step 4: Submitting a 3A4 Request</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-submitting-a-3a4-request.md)