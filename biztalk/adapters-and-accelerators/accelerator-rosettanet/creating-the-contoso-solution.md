---
title: 创建 Contoso 解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private process tutorial, creating solutions
ms.assetid: 02f5326a-68bd-418a-af81-684a73056e2c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2ed65010926f04e99eb126980870368c5d4a512
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000126"
---
# <a name="creating-the-contoso-solution"></a><span data-ttu-id="10d52-102">创建 Contoso 解决方案</span><span class="sxs-lookup"><span data-stu-id="10d52-102">Creating the Contoso Solution</span></span>
<span data-ttu-id="10d52-103">本节详细介绍了对于 Contoso 组织必须执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="10d52-103">This section details the steps that you have to follow for the Contoso organization.</span></span> <span data-ttu-id="10d52-104">第一步是添加两个组织使用 Microsoft® 联系人信息和合作伙伴协议[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="10d52-104">The first step is to add the contact information and partner agreements for the two organizations using the Microsoft® [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console.</span></span> <span data-ttu-id="10d52-105">然后创建业务线 (LOB) 架构，再构造这些架构与其各自的基于 RosettaNet 的合作伙伴接口流程 (PIP) 架构间的映射。</span><span class="sxs-lookup"><span data-stu-id="10d52-105">You then create line-of-business (LOB) schemas, and construct a mapping between those schemas and their respective RosettaNet-based Partner Interface Process (PIP) schemas.</span></span> <span data-ttu-id="10d52-106">下一步，使用 SQL 适配器配置用于与 ERP 系统进行通信的端口信息，以及使用 HTTP 适配器配置用于向 Fabrikam 发送信息的端口信息。</span><span class="sxs-lookup"><span data-stu-id="10d52-106">Next, you configure port information using the SQL adapter for communicating with the ERP system, and the HTTP adapter for sending information to Fabrikam.</span></span> <span data-ttu-id="10d52-107">最后一步是自定义专用业务流程要在 BizTalk Server 中使用业务规则引擎 (BRE)。</span><span class="sxs-lookup"><span data-stu-id="10d52-107">The last step is to customize the private process orchestration to use the Business Rule Engine (BRE) in BizTalk Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="10d52-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="10d52-108">In This Section</span></span>  
  
-   [<span data-ttu-id="10d52-109">为 Contoso 创建组织和贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="10d52-109">Creating Organizations and Trading Partner Agreement for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-organizations-and-trading-partner-agreement-for-contoso.md)  
  
-   [<span data-ttu-id="10d52-110">创建 Contoso LOB 架构和映射</span><span class="sxs-lookup"><span data-stu-id="10d52-110">Creating the Contoso LOB Schemas and Maps</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-lob-schemas-and-maps.md)  
  
-   [<span data-ttu-id="10d52-111">创建和配置 Contoso 的 BizTalk 端口</span><span class="sxs-lookup"><span data-stu-id="10d52-111">Creating and Configuring BizTalk Ports for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-configuring-biztalk-ports-for-contoso.md)  
  
-   [<span data-ttu-id="10d52-112">创建和修改 Contoso 的私有流程</span><span class="sxs-lookup"><span data-stu-id="10d52-112">Creating and Modifying the Private Process for Contoso</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-and-modifying-the-private-process-for-contoso.md)