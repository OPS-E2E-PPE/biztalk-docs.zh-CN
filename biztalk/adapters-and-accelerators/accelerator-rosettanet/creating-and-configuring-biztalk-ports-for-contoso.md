---
title: 创建和配置 Contoso 的 BizTalk 端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- ports, creating
- private process tutorial, creating ports
- creating, ports
- configuring, ports
- private process tutorial, configuring ports
- ports, configuring
ms.assetid: 179af692-e14c-40da-9c43-1a7d0b6beb1f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 68483898150e7ba2d876cf5d798683e9b313a726
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65284384"
---
# <a name="creating-and-configuring-biztalk-ports-for-contoso"></a><span data-ttu-id="8f688-102">创建和配置 Contoso 的 BizTalk 端口</span><span class="sxs-lookup"><span data-stu-id="8f688-102">Creating and Configuring BizTalk Ports for Contoso</span></span>
<span data-ttu-id="8f688-103">在本部分中，您将您当前的解决方案集成到 Microsoft® BizTalk Server。</span><span class="sxs-lookup"><span data-stu-id="8f688-103">In this section, you integrate your current solution into Microsoft® BizTalk Server.</span></span> <span data-ttu-id="8f688-104">执行此操作之前，安装您的程序集在全局程序集缓存 (GAC)，然后将其配置中配置数据库。</span><span class="sxs-lookup"><span data-stu-id="8f688-104">Before you do this, you install your assembly in the Global Assembly Cache (GAC), and then configure it in the Configuration database.</span></span> <span data-ttu-id="8f688-105">然后创建并配置发送端口使用 SQL 适配器和 HTTP 适配器。</span><span class="sxs-lookup"><span data-stu-id="8f688-105">You then create and configure send ports using a SQL adapter and a HTTP adapter.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f688-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="8f688-106">In This Section</span></span>  
  
-   [<span data-ttu-id="8f688-107">步骤 1：向 Contoso 程序集分配强名称</span><span class="sxs-lookup"><span data-stu-id="8f688-107">Step 1: Assigning a Strong Name to the Contoso Assembly</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-assigning-a-strong-name-to-the-contoso-assembly.md)  
  
-   [<span data-ttu-id="8f688-108">步骤 2：为 Contoso 3A2 价格与可用性查询/响应方案创建端口</span><span class="sxs-lookup"><span data-stu-id="8f688-108">Step 2: Creating Ports for the Contoso 3A2 Price and Availability Query/Response Scenario</span></span>](step-2-create-ports-for-contoso-3a2-price-and-availability-query.md)