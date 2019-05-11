---
title: 设置 CIDX 解决方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, process configuration
- creating, CIDX solutions
- CIDX, connecting to Elemica network
- agreements, CIDX
- process configuration, CIDX
- CIDX, agreements
- PIPs, importing for CIDX
- CIDX, PIPs
- CIDX, creating solutions
- CIDX, importing PIPs
- PIPs, CIDX
ms.assetid: 7f1f159f-3b09-4efd-907b-9a75f7f3ecd1
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fc14c208886497b001d50bbb8b5446b1ecccc20a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281785"
---
# <a name="setting-up-a-cidx-solution"></a><span data-ttu-id="402bf-102">设置 CIDX 解决方案</span><span class="sxs-lookup"><span data-stu-id="402bf-102">Setting Up a CIDX Solution</span></span>
<span data-ttu-id="402bf-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] CIDX （化工行业数据交换） XML 消息交换 (CIDX Chem eStandards 2.0 和 3.0 版) 的支持。</span><span class="sxs-lookup"><span data-stu-id="402bf-103">Microsoft [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] support for CIDX (Chemical Industry Data Exchange) XML message exchange (CIDX Chem eStandards versions 2.0 and 3.0).</span></span> <span data-ttu-id="402bf-104">本主题介绍如何设置 CIDX 解决方案，通过执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="402bf-104">This topic describes how to set up a CIDX solution by doing the following:</span></span>  
  
-   <span data-ttu-id="402bf-105">流程配置设置</span><span class="sxs-lookup"><span data-stu-id="402bf-105">Setting up a process configuration</span></span>  
  
-   <span data-ttu-id="402bf-106">设置协议</span><span class="sxs-lookup"><span data-stu-id="402bf-106">Setting up an agreement</span></span>  
  
-   <span data-ttu-id="402bf-107">应用 PIP</span><span class="sxs-lookup"><span data-stu-id="402bf-107">Applying a PIP</span></span>  
  
-   <span data-ttu-id="402bf-108">导入基于 XSD 的 PIP</span><span class="sxs-lookup"><span data-stu-id="402bf-108">Importing an XSD-based PIP</span></span>  
  
-   <span data-ttu-id="402bf-109">连接到 Elemica 网络</span><span class="sxs-lookup"><span data-stu-id="402bf-109">Connecting to the Elemica Network</span></span>  
  
## <a name="setting-up-a-cidx-process-configuration"></a><span data-ttu-id="402bf-110">设置 CIDX 流程配置</span><span class="sxs-lookup"><span data-stu-id="402bf-110">Setting Up a CIDX Process Configuration</span></span>  
 <span data-ttu-id="402bf-111">若要设置 CIDX eStandards 消息交换，需要创建具有以下属性的流程配置：</span><span class="sxs-lookup"><span data-stu-id="402bf-111">To set up a CIDX eStandards message exchange, you need to create a process configuration that has the following properties:</span></span>  
  
- <span data-ttu-id="402bf-112">**标准**属性设置为流程配置设置中的**CIDX**</span><span class="sxs-lookup"><span data-stu-id="402bf-112">**Standard** property in the process configuration settings set to **CIDX**</span></span>  
  
- <span data-ttu-id="402bf-113">**是否为单一操作**属性设置为流程配置设置中的 **，则返回 True**</span><span class="sxs-lookup"><span data-stu-id="402bf-113">**Is Single Action** property in the process configuration settings set to **True**</span></span>  
  
- <span data-ttu-id="402bf-114">**0A1 协议**属性设置为贸易合作伙伴协议中的**非 0A1**</span><span class="sxs-lookup"><span data-stu-id="402bf-114">**0A1 agreement** property in the trading partner agreement set to **No 0A1**</span></span>  
  
  <span data-ttu-id="402bf-115">有关详细信息，请参阅[设置 CIDX eStandards 消息交换](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)。</span><span class="sxs-lookup"><span data-stu-id="402bf-115">For more information, see [Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md).</span></span>  
  
## <a name="creating-a-cidx-agreement"></a><span data-ttu-id="402bf-116">创建 CIDX 协议</span><span class="sxs-lookup"><span data-stu-id="402bf-116">Creating a CIDX Agreement</span></span>  
 <span data-ttu-id="402bf-117">若要设置 CIDX eStandards 消息交换，需要创建具有以下属性的协议：</span><span class="sxs-lookup"><span data-stu-id="402bf-117">To set up a CIDX eStandards message exchange, you need to create an agreement that has the following properties:</span></span>  
  
- <span data-ttu-id="402bf-118">**RNIF 版本**属性设置为协议设置中的**V01.10.00**</span><span class="sxs-lookup"><span data-stu-id="402bf-118">**RNIF Version** property in the agreement settings set to **V01.10.00**</span></span>  
  
- <span data-ttu-id="402bf-119">**0A1 协议**属性设置为协议设置中的**非 0A1**</span><span class="sxs-lookup"><span data-stu-id="402bf-119">**0A1 agreement** property in the agreement settings set to **No 0A1**</span></span>  
  
  <span data-ttu-id="402bf-120">有关详细信息，请参阅[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="402bf-120">For more information, see [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
## <a name="applying-a-pip-for-cidx"></a><span data-ttu-id="402bf-121">为 CIDX 应用 PIP</span><span class="sxs-lookup"><span data-stu-id="402bf-121">Applying a PIP for CIDX</span></span>  
 <span data-ttu-id="402bf-122">若要将 PIP 应用于 CIDX 实现中，设置**标准**到过程配置文件中的属性**CIDX**。</span><span class="sxs-lookup"><span data-stu-id="402bf-122">To apply a PIP to a CIDX implementation, set the **Standard** property in the process configuration profile to **CIDX**.</span></span> <span data-ttu-id="402bf-123">完成后，你将能够输入的值**消息标准**，**标准版本**，并**负载绑定 ID**。</span><span class="sxs-lookup"><span data-stu-id="402bf-123">After you have finished, you will be able to enter values for the **Message standard**, **Standard version**, and **Payload binding ID**.</span></span> <span data-ttu-id="402bf-124">您可以在 CIDX Chem eStandards 规范中找到这些值。</span><span class="sxs-lookup"><span data-stu-id="402bf-124">You can find these values in the CIDX Chem eStandards specification.</span></span>  
  
## <a name="importing-an-xsd-based-pip-for-cidx"></a><span data-ttu-id="402bf-125">为 CIDX 导入基于 XSD 的 PIP</span><span class="sxs-lookup"><span data-stu-id="402bf-125">Importing an XSD-based PIP for CIDX</span></span>  
 <span data-ttu-id="402bf-126">若要为 CIDX 导入基于 XSD 的 PIP，需要在 cidx.org 下载 PIP 的 ZIP 文件[ http://go.microsoft.com/FWLink/?LinkID=33859 ](http://go.microsoft.com/FWLink/?LinkID=62361)。</span><span class="sxs-lookup"><span data-stu-id="402bf-126">To import an XSD-based PIP for CIDX, you need to download the PIP's ZIP file from CIDX.org at [http://go.microsoft.com/FWLink/?LinkID=33859](http://go.microsoft.com/FWLink/?LinkID=62361).</span></span> <span data-ttu-id="402bf-127">请按照导入过程中所述[导入基于 XSD 的 PIP](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)。</span><span class="sxs-lookup"><span data-stu-id="402bf-127">Follow the import procedure described in [Importing an XSD-based PIP](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md).</span></span>  
  
## <a name="connecting-to-the-elemica-network"></a><span data-ttu-id="402bf-128">连接到 Elemica 网络</span><span class="sxs-lookup"><span data-stu-id="402bf-128">Connecting to the Elemica Network</span></span>  
 <span data-ttu-id="402bf-129">你可以自定义[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]以连接到 Elemica 使用 Elemica 连接包中的项目文件。</span><span class="sxs-lookup"><span data-stu-id="402bf-129">You can customize [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] to connect to Elemica using project files in the Elemica Connectivity Pack.</span></span> <span data-ttu-id="402bf-130">您可以下载连接包从[ http://go.microsoft.com/fwlink/?LinkId=46195 ](http://go.microsoft.com/fwlink/?LinkId=46195)。</span><span class="sxs-lookup"><span data-stu-id="402bf-130">You can download the Connectivity Pack from [http://go.microsoft.com/fwlink/?LinkId=46195](http://go.microsoft.com/fwlink/?LinkId=46195).</span></span> <span data-ttu-id="402bf-131">有关详细信息，请在 MSDN 上参阅"连接到 Elemica 网络使用 BizTalk Accelerator for RosettaNet 3.0"白皮书[ http://go.microsoft.com/fwlink/?linkid=46539 ](http://go.microsoft.com/fwlink/?linkid=46539)。</span><span class="sxs-lookup"><span data-stu-id="402bf-131">For more information, see the “Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0” white paper on MSDN at [http://go.microsoft.com/fwlink/?linkid=46539](http://go.microsoft.com/fwlink/?linkid=46539).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="402bf-132">在"连接到 Elemica 网络使用 BizTalk Accelerator for RosettaNet 3.0"白皮书中的信息是对有效[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="402bf-132">The information in the "Connecting to the Elemica Network with BizTalk Accelerator for RosettaNet 3.0" white paper is valid for [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="402bf-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="402bf-133">See Also</span></span>  
 <span data-ttu-id="402bf-134">[CIDX 支持](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md) </span><span class="sxs-lookup"><span data-stu-id="402bf-134">[CIDX Support](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md) </span></span>  
 <span data-ttu-id="402bf-135">[CIDX 消息传送标准](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md) </span><span class="sxs-lookup"><span data-stu-id="402bf-135">[CIDX Messaging Standards](../../adapters-and-accelerators/accelerator-rosettanet/cidx-messaging-standards.md) </span></span>  
 <span data-ttu-id="402bf-136">[设置 CIDX eStandards 消息交换](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md) </span><span class="sxs-lookup"><span data-stu-id="402bf-136">[Setting Up CIDX eStandards Message Exchange](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md) </span></span>  
 <span data-ttu-id="402bf-137">[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="402bf-137">[Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span></span>  
 [<span data-ttu-id="402bf-138">导入基于 XSD 的 PIP</span><span class="sxs-lookup"><span data-stu-id="402bf-138">Importing an XSD-based PIP</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/importing-an-xsd-based-pip.md)