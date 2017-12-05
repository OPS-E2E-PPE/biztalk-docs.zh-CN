---
title: "步骤 4： 创建 Contoso 0 C 4 贸易合作伙伴协议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- agreements, creating
- creating, agreements
- double action tutorial, creating agreements
ms.assetid: de2a943f-945a-4bfc-87f3-dd327d5214ef
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fd781c41614edf6bfa1df12fa47de6c944c12ab0
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="step-4-creating-the-contoso-0c4-trading-partner-agreement"></a><span data-ttu-id="307ed-102">步骤 4： 创建 Contoso 0 C 4 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="307ed-102">Step 4: Creating the Contoso 0C4 Trading Partner Agreement</span></span>
<span data-ttu-id="307ed-103">在此步骤中，将使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理控制台创建 Contoso 和 Fabrikam 之间的贸易合作伙伴协议，</span><span class="sxs-lookup"><span data-stu-id="307ed-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="307ed-104">并为 0C4 合作伙伴接口流程 (PIP) 创建新的贸易合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="307ed-104">You create a new trading partner agreement for the 0C4 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="307ed-105">启动 BTARN 管理控制台</span><span class="sxs-lookup"><span data-stu-id="307ed-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="307ed-106">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="307ed-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console.</span></span>  
  
### <a name="to-create-the-0c4-trading-partner-agreement"></a><span data-ttu-id="307ed-107">创建 0C4 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="307ed-107">To create the 0C4 trading partner agreement</span></span>  
  
1.  <span data-ttu-id="307ed-108">在 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**协议**，指向**新建**，然后单击**协议**.</span><span class="sxs-lookup"><span data-stu-id="307ed-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="307ed-109">在新的协议属性对话框中，在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="307ed-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="307ed-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="307ed-110">Use this</span></span>|<span data-ttu-id="307ed-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="307ed-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="307ed-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="307ed-112">**Name**</span></span>|<span data-ttu-id="307ed-113">类型**Fabrikam_To_Contoso_0C4**。</span><span class="sxs-lookup"><span data-stu-id="307ed-113">Type **Fabrikam_To_Contoso_0C4**.</span></span>|  
    |<span data-ttu-id="307ed-114">**过程配置**</span><span class="sxs-lookup"><span data-stu-id="307ed-114">**Process Configuration**</span></span>|<span data-ttu-id="307ed-115">选择**STD_0C4_R01.02**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="307ed-115">Select **STD_0C4_R01.02** from the drop-down list.</span></span>|  
    |<span data-ttu-id="307ed-116">**我的组织**</span><span class="sxs-lookup"><span data-stu-id="307ed-116">**My Organization**</span></span>|<span data-ttu-id="307ed-117">选择**Contoso**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="307ed-117">Select **Contoso** from the drop-down list.</span></span>|  
    |<span data-ttu-id="307ed-118">**伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="307ed-118">**Partner Organization**</span></span>|<span data-ttu-id="307ed-119">选择**Fabrikam**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="307ed-119">Select **Fabrikam** from the drop-down list.</span></span>|  
    |<span data-ttu-id="307ed-120">**RNIF 版本**</span><span class="sxs-lookup"><span data-stu-id="307ed-120">**RNIF Version**</span></span>|<span data-ttu-id="307ed-121">选择**V02.00.01**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="307ed-121">Select **V02.00.01** from the drop-down list.</span></span>|  
    |<span data-ttu-id="307ed-122">**主角色**</span><span class="sxs-lookup"><span data-stu-id="307ed-122">**Home Role**</span></span>|<span data-ttu-id="307ed-123">选择**响应方 （响应方）**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="307ed-123">Select **Responder (Responder)** from the drop-down list.</span></span>|  
    |<span data-ttu-id="307ed-124">**用法**</span><span class="sxs-lookup"><span data-stu-id="307ed-124">**Usage**</span></span>|<span data-ttu-id="307ed-125">选择**测试**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="307ed-125">Select **Test** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="307ed-126">单击**端口**选项卡，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="307ed-126">Click the **Ports** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="307ed-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="307ed-127">Use this</span></span>|<span data-ttu-id="307ed-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="307ed-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="307ed-129">**操作 URL**</span><span class="sxs-lookup"><span data-stu-id="307ed-129">**Action URL**</span></span>|<span data-ttu-id="307ed-130">类型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="307ed-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span>|  
    |<span data-ttu-id="307ed-131">**信号 URL**</span><span class="sxs-lookup"><span data-stu-id="307ed-131">**Signal URL**</span></span>|<span data-ttu-id="307ed-132">类型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="307ed-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span>|  
    |<span data-ttu-id="307ed-133">**同步 URL**</span><span class="sxs-lookup"><span data-stu-id="307ed-133">**Sync URL**</span></span>|<span data-ttu-id="307ed-134">类型**https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="307ed-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span>|  
  
4.  <span data-ttu-id="307ed-135">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="307ed-135">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="307ed-136">右键单击**Fabrikam_To_Contoso_0C4**协议，，然后单击**激活**。</span><span class="sxs-lookup"><span data-stu-id="307ed-136">Right-click the **Fabrikam_To_Contoso_0C4** agreement, and then click **Activate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="307ed-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="307ed-137">See Also</span></span>  
 [<span data-ttu-id="307ed-138">步骤 5：创建 Contoso 3A2 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="307ed-138">Step 5: Creating the Contoso 3A2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-creating-the-contoso-3a2-trading-partner-agreement.md)