---
title: "步骤 6： 创建 Fabrikam 3A4 贸易合作伙伴协议 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: double action tutorial, creating agreements
ms.assetid: 6ccd2414-a1d4-460e-9529-65b2d30cfca6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9e5b034e2da0101cb8ce37ad193fa04e8c3d6d16
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="step-6-creating-the-fabrikam-3a4-trading-partner-agreement"></a><span data-ttu-id="85569-102">步骤 6： 创建 Fabrikam 3A4 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="85569-102">Step 6: Creating the Fabrikam 3A4 Trading Partner Agreement</span></span>
<span data-ttu-id="85569-103">在此步骤中，将使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理控制台创建 Contoso 和 Fabrikam 之间的贸易合作伙伴协议，</span><span class="sxs-lookup"><span data-stu-id="85569-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="85569-104">并为 3A4 合作伙伴接口流程 (PIP) 创建新的贸易合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="85569-104">You create a new trading partner agreement for the 3A4 Partner Interface Process (PIP).</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="85569-105">启动 BTARN 管理控制台</span><span class="sxs-lookup"><span data-stu-id="85569-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="85569-106">单击**启动**，指向**所有程序**，指向**Microsoft BizTalk\<版本 > Accelerator for RosettaNet**，然后单击**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="85569-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-the-3a4-trading-partner-agreement"></a><span data-ttu-id="85569-107">创建 3A4 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="85569-107">To create the 3A4 trading partner agreement</span></span>  
  
1.  <span data-ttu-id="85569-108">在 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**协议**，指向**新建**，然后单击**协议**.</span><span class="sxs-lookup"><span data-stu-id="85569-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
2.  <span data-ttu-id="85569-109">在**新协议属性**对话框中，在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="85569-109">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  
  
    |<span data-ttu-id="85569-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="85569-110">Use this</span></span>|<span data-ttu-id="85569-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="85569-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="85569-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="85569-112">**Name**</span></span>|<span data-ttu-id="85569-113">类型**Fabrikam_To_Contoso_3A4**。</span><span class="sxs-lookup"><span data-stu-id="85569-113">Type **Fabrikam_To_Contoso_3A4**.</span></span>|  
    |<span data-ttu-id="85569-114">**过程配置**</span><span class="sxs-lookup"><span data-stu-id="85569-114">**Process Configuration**</span></span>|<span data-ttu-id="85569-115">选择**STD_3A4_V02.02**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="85569-115">Select **STD_3A4_V02.02** from the drop-down list.</span></span>|  
    |<span data-ttu-id="85569-116">**我的组织**</span><span class="sxs-lookup"><span data-stu-id="85569-116">**My Organization**</span></span>|<span data-ttu-id="85569-117">选择**Fabrikam**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="85569-117">Select **Fabrikam** from the drop-down list.</span></span>|  
    |<span data-ttu-id="85569-118">**伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="85569-118">**Partner Organization**</span></span>|<span data-ttu-id="85569-119">选择**Contoso**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="85569-119">Select **Contoso** from the drop-down list.</span></span>|  
    |<span data-ttu-id="85569-120">**RNIF 版本**</span><span class="sxs-lookup"><span data-stu-id="85569-120">**RNIF Version**</span></span>|<span data-ttu-id="85569-121">选择**V02.00.01**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="85569-121">Select **V02.00.01** from the drop-down list.</span></span>|  
    |<span data-ttu-id="85569-122">**主角色**</span><span class="sxs-lookup"><span data-stu-id="85569-122">**Home Role**</span></span>|<span data-ttu-id="85569-123">选择**Buyer （发起程序）**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="85569-123">Select **Buyer (Initiator)** from the drop-down list.</span></span>|  
    |<span data-ttu-id="85569-124">**用法**</span><span class="sxs-lookup"><span data-stu-id="85569-124">**Usage**</span></span>|<span data-ttu-id="85569-125">选择**测试**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="85569-125">Select **Test** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="85569-126">上**端口**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="85569-126">On the **Ports** tab, do the following:</span></span>  
  
    |<span data-ttu-id="85569-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="85569-127">Use this</span></span>|<span data-ttu-id="85569-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="85569-128">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="85569-129">**操作 URL**</span><span class="sxs-lookup"><span data-stu-id="85569-129">**Action URL**</span></span>|<span data-ttu-id="85569-130">类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。</span><span class="sxs-lookup"><span data-stu-id="85569-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="85569-131">**信号 URL**</span><span class="sxs-lookup"><span data-stu-id="85569-131">**Signal URL**</span></span>|<span data-ttu-id="85569-132">类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。</span><span class="sxs-lookup"><span data-stu-id="85569-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
    |<span data-ttu-id="85569-133">**同步 URL**</span><span class="sxs-lookup"><span data-stu-id="85569-133">**Sync URL**</span></span>|<span data-ttu-id="85569-134">类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。</span><span class="sxs-lookup"><span data-stu-id="85569-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span>|  
  
4.  <span data-ttu-id="85569-135">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="85569-135">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="85569-136">右键单击**Fabrikam_To_Contoso_3A4**协议，然后单击**激活**。</span><span class="sxs-lookup"><span data-stu-id="85569-136">Right-click the **Fabrikam_To_Contoso_3A4** agreement and then click **Activate**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85569-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="85569-137">See Also</span></span>  
 [<span data-ttu-id="85569-138">步骤 7： 构建和部署 LOBWebApplication SDK 示例</span><span class="sxs-lookup"><span data-stu-id="85569-138">Step 7: Building and Deploying the LOBWebApplication SDK Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-lobwebapplication-sdk-sample.md)