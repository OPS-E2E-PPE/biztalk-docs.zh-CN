---
title: "创建和为 Contoso 配置 BizTalk 端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, creating
- private process tutorial, creating ports
- creating, ports
- configuring, ports
- private process tutorial, configuring ports
- ports, configuring
ms.assetid: 179af692-e14c-40da-9c43-1a7d0b6beb1f
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7264d2eaa5c3ce249bc1077f7754d93eecdd786a
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="creating-and-configuring-biztalk-ports-for-contoso"></a><span data-ttu-id="c7866-102">创建和为 Contoso 配置 BizTalk 端口</span><span class="sxs-lookup"><span data-stu-id="c7866-102">Creating and Configuring BizTalk Ports for Contoso</span></span>
<span data-ttu-id="c7866-103">在此部分中，你将集成到当前解决方案[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="c7866-103">In this section, you integrate your current solution into [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® BizTalk Server.</span></span> <span data-ttu-id="c7866-104">执行此操作之前，请将自己的程序集安装到全局程序集缓存 (GAC) 中，然后在配置数据库中配置它。</span><span class="sxs-lookup"><span data-stu-id="c7866-104">Before you do this, you install your assembly in the Global Assembly Cache (GAC), and then configure it in the Configuration database.</span></span> <span data-ttu-id="c7866-105">然后使用 SQL 适配器和 HTTP 适配器创建和配置发送端口。</span><span class="sxs-lookup"><span data-stu-id="c7866-105">You then create and configure send ports using a SQL adapter and a HTTP adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c7866-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="c7866-106">In This Section</span></span>  
  
-   [<span data-ttu-id="c7866-107">步骤 1：向 Contoso 程序集分配强名称</span><span class="sxs-lookup"><span data-stu-id="c7866-107">Step 1: Assigning a Strong Name to the Contoso Assembly</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-assigning-a-strong-name-to-the-contoso-assembly.md)  
  
-   [<span data-ttu-id="c7866-108">步骤 2： 为 Contoso 3A2 价格和可用性查询/响应方案创建端口</span><span class="sxs-lookup"><span data-stu-id="c7866-108">Step 2: Creating Ports for the Contoso 3A2 Price and Availability Query/Response Scenario</span></span>](step-2-create-ports-for-contoso-3a2-price-and-availability-query.md)