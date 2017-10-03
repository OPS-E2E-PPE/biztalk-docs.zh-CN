---
title: "创建 Contoso LOB 架构和映射 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- schemas, LOB
- LOBs, schemas
- private process tutorial, creating LOB schemas
- private process tutorial, creating maps
- maps
ms.assetid: fda8852a-51d8-4987-a187-834883a06d9b
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f204efd00858f3f4204848f4fb4a0dcef5233b3c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="creating-the-contoso-lob-schemas-and-maps"></a><span data-ttu-id="e6cba-102">创建 Contoso LOB 架构和映射</span><span class="sxs-lookup"><span data-stu-id="e6cba-102">Creating the Contoso LOB Schemas and Maps</span></span>
<span data-ttu-id="e6cba-103">在本节中，将创建 Contoso 组织在其 ERP 系统中使用的业务线 (LOB) 架构。</span><span class="sxs-lookup"><span data-stu-id="e6cba-103">In this section, you create the line-of-business (LOB) schemas that the Contoso organization uses in their ERP system.</span></span> <span data-ttu-id="e6cba-104">使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] 映射器工具可创建 Contoso 内部消息与入站和出站 RosettaNet 消息类型之间的数据转换。</span><span class="sxs-lookup"><span data-stu-id="e6cba-104">You use the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)] Mapper tool to create data transformations between the internal Contoso messages and the inbound and outbound RosettaNet message types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e6cba-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="e6cba-105">In This Section</span></span>  
  
-   [<span data-ttu-id="e6cba-106">步骤 1： 为 Contoso 价格和可用性请求创建一个新的 BizTalk 解决方案</span><span class="sxs-lookup"><span data-stu-id="e6cba-106">Step 1: Creating a New BizTalk Solution for the Contoso Price and Availability Request</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-1-create-new-biztalk-solution-for-contoso-price-and-availability-request.md)  
  
-   [<span data-ttu-id="e6cba-107">步骤 2： 为价格和可用性项目使用 BizTalk 编辑器创建 Contoso LOB 应用程序架构</span><span class="sxs-lookup"><span data-stu-id="e6cba-107">Step 2: Creating the Contoso LOB Application Schemas for the Price and Availability Project Using BizTalk Editor</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-2-create-contoso-lob-application-schema-for-price-and-availability.md)  
  
-   [<span data-ttu-id="e6cba-108">步骤 3： 为价格和可用性项目使用 BizTalk 映射程序创建 Contoso LOB 应用程序映射</span><span class="sxs-lookup"><span data-stu-id="e6cba-108">Step 3: Creating the Contoso LOB Application Maps for the Price and Availability Project Using BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-create-contoso-lob-application-map-for-price-and-availability-in-mapper.md)