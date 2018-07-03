---
title: 步骤 3： 创建 Fabrikam 0 C 2 个贸易合作伙伴协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: 4552f712-f226-423f-b06d-98e943e8efd4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c10881f1ac703f07d6daaf2a87abd96f3086672b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970262"
---
# <a name="step-3-creating-the-fabrikam-0c2-trading-partner-agreement"></a><span data-ttu-id="c7b5c-102">步骤 3： 创建 Fabrikam 0 C 2 个贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="c7b5c-102">Step 3: Creating the Fabrikam 0C2 Trading Partner Agreement</span></span>
<span data-ttu-id="c7b5c-103">在此步骤中，创建 Contoso 和 Fabrikam 使用 Microsoft® 之间的贸易合作伙伴协议[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="c7b5c-104">并为 0C2 合作伙伴接口流程 (PIP) 创建新的贸易合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-104">You create a new trading partner agreement for the 0C2 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="c7b5c-105">启动 BTARN 管理控制台</span><span class="sxs-lookup"><span data-stu-id="c7b5c-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="c7b5c-106">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-0c2-trading-partner-agreement"></a><span data-ttu-id="c7b5c-107">创建 0C2 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="c7b5c-107">To create the 0C2 trading partner agreement</span></span>  

1. <span data-ttu-id="c7b5c-108">在中**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**协议**，指向**新建**，然后单击**协议**.</span><span class="sxs-lookup"><span data-stu-id="c7b5c-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="c7b5c-109">在新协议属性对话框中，在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7b5c-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="c7b5c-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c7b5c-110">Use this</span></span>          |                        <span data-ttu-id="c7b5c-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c7b5c-111">To do this</span></span>                         |
   |---------------------------|-----------------------------------------------------------|
   |         <span data-ttu-id="c7b5c-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-112">**Name**</span></span>          |             <span data-ttu-id="c7b5c-113">类型**Fabrikam_To_Contoso_0C2**。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-113">Type **Fabrikam_To_Contoso_0C2**.</span></span>             |
   | <span data-ttu-id="c7b5c-114">**过程配置**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-114">**Process Configuration**</span></span> |    <span data-ttu-id="c7b5c-115">选择**STD_0C2_R01.02**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-115">Select **STD_0C2_R01.02** from the drop-down list.</span></span>     |
   |    <span data-ttu-id="c7b5c-116">**我的组织**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-116">**My Organization**</span></span>    |       <span data-ttu-id="c7b5c-117">选择**Fabrikam**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-117">Select **Fabrikam** from the drop-down list.</span></span>        |
   | <span data-ttu-id="c7b5c-118">**合作伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-118">**Partner Organization**</span></span>  |        <span data-ttu-id="c7b5c-119">选择**Contoso**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-119">Select **Contoso** from the drop-down list.</span></span>        |
   |     <span data-ttu-id="c7b5c-120">**RNIF 版本**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-120">**RNIF Version**</span></span>      |       <span data-ttu-id="c7b5c-121">选择**V02.00.01**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-121">Select **V02.00.01** from the drop-down list.</span></span>       |
   |       <span data-ttu-id="c7b5c-122">**本组织角色**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-122">**Home Role**</span></span>       | <span data-ttu-id="c7b5c-123">选择**发起方 （发起方）** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-123">Select **Initiator (Initiator)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="c7b5c-124">**Usage**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-124">**Usage**</span></span>         |         <span data-ttu-id="c7b5c-125">选择**测试**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-125">Select **Test** from the drop-down list.</span></span>          |


3. <span data-ttu-id="c7b5c-126">单击**端口**选项卡，然后再执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c7b5c-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="c7b5c-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c7b5c-127">Use this</span></span>    |                          <span data-ttu-id="c7b5c-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c7b5c-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="c7b5c-129">**操作 URL**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-129">**Action URL**</span></span> | <span data-ttu-id="c7b5c-130">类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   | <span data-ttu-id="c7b5c-131">**信号 URL**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-131">**Signal URL**</span></span> | <span data-ttu-id="c7b5c-132">类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   |  <span data-ttu-id="c7b5c-133">**同步 URL**</span><span class="sxs-lookup"><span data-stu-id="c7b5c-133">**Sync URL**</span></span>  | <span data-ttu-id="c7b5c-134">类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |


4. <span data-ttu-id="c7b5c-135">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-135">Click **OK**.</span></span>  

5. <span data-ttu-id="c7b5c-136">右键单击**Fabrikam_To_Contoso_0C2**协议，，然后单击**激活**。</span><span class="sxs-lookup"><span data-stu-id="c7b5c-136">Right-click the **Fabrikam_To_Contoso_0C2** agreement, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c7b5c-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7b5c-137">See Also</span></span>  
 [<span data-ttu-id="c7b5c-138">步骤 4：创建 Fabrikam 0C4 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="c7b5c-138">Step 4: Creating the Fabrikam 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-fabrikam-0c4-trading-partner-agreement.md)