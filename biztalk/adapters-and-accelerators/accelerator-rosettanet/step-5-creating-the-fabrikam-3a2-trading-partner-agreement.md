---
title: 步骤 5： 创建 Fabrikam 3A2 贸易合作伙伴协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- double action tutorial, creating agreements
ms.assetid: a5fafdc6-e9dd-4d15-98a2-8b603901308c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d69b129744df598d69b3209f4af46123ff22fda3
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36992350"
---
# <a name="step-5-creating-the-fabrikam-3a2-trading-partner-agreement"></a><span data-ttu-id="c5495-102">步骤 5： 创建 Fabrikam 3A2 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="c5495-102">Step 5: Creating the Fabrikam 3A2 Trading Partner Agreement</span></span>
<span data-ttu-id="c5495-103">在此步骤中，创建 Contoso 和 Fabrikam 使用 Microsoft® 之间的贸易合作伙伴协议[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c5495-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="c5495-104">并为 3A2 合作伙伴接口流程 (PIP) 创建新的贸易合作伙伴协议。</span><span class="sxs-lookup"><span data-stu-id="c5495-104">You create a new trading partner agreement for the 3A2 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="c5495-105">启动 BTARN 管理控制台</span><span class="sxs-lookup"><span data-stu-id="c5495-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="c5495-106">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c5495-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-3a2-trading-partner-agreement"></a><span data-ttu-id="c5495-107">创建 3A2 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="c5495-107">To create the 3A2 trading partner agreement</span></span>  

1. <span data-ttu-id="c5495-108">在中**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**协议**，指向**新建**，然后单击**协议**.</span><span class="sxs-lookup"><span data-stu-id="c5495-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="c5495-109">在中**新协议属性**对话框中，在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c5495-109">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="c5495-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c5495-110">Use this</span></span>          |                        <span data-ttu-id="c5495-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c5495-111">To do this</span></span>                        |
   |---------------------------|----------------------------------------------------------|
   |         <span data-ttu-id="c5495-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="c5495-112">**Name**</span></span>          |            <span data-ttu-id="c5495-113">类型**Fabrikam_To_Contoso_3A2**。</span><span class="sxs-lookup"><span data-stu-id="c5495-113">Type **Fabrikam_To_Contoso_3A2**.</span></span>             |
   | <span data-ttu-id="c5495-114">**过程配置**</span><span class="sxs-lookup"><span data-stu-id="c5495-114">**Process Configuration**</span></span> |  <span data-ttu-id="c5495-115">选择**STD_3A2_R02.00.00A**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c5495-115">Select **STD_3A2_R02.00.00A** from the drop-down list.</span></span>  |
   |    <span data-ttu-id="c5495-116">**我的组织**</span><span class="sxs-lookup"><span data-stu-id="c5495-116">**My Organization**</span></span>    |       <span data-ttu-id="c5495-117">选择**Fabrikam**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c5495-117">Select **Fabrikam** from the drop-down list.</span></span>       |
   | <span data-ttu-id="c5495-118">**合作伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="c5495-118">**Partner Organization**</span></span>  |       <span data-ttu-id="c5495-119">选择**Contoso**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c5495-119">Select **Contoso** from the drop-down list.</span></span>        |
   |     <span data-ttu-id="c5495-120">**RNIF 版本**</span><span class="sxs-lookup"><span data-stu-id="c5495-120">**RNIF Version**</span></span>      |      <span data-ttu-id="c5495-121">选择**V02.00.01**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c5495-121">Select **V02.00.01** from the drop-down list.</span></span>       |
   |       <span data-ttu-id="c5495-122">**本组织角色**</span><span class="sxs-lookup"><span data-stu-id="c5495-122">**Home Role**</span></span>       | <span data-ttu-id="c5495-123">选择**客户 （发起方）** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c5495-123">Select **Customer (Initiator)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="c5495-124">**Usage**</span><span class="sxs-lookup"><span data-stu-id="c5495-124">**Usage**</span></span>         |         <span data-ttu-id="c5495-125">选择**测试**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="c5495-125">Select **Test** from the drop-down list.</span></span>         |


3. <span data-ttu-id="c5495-126">单击**端口**选项卡，然后再执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c5495-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="c5495-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="c5495-127">Use this</span></span>    |                          <span data-ttu-id="c5495-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="c5495-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="c5495-129">**操作 URL**</span><span class="sxs-lookup"><span data-stu-id="c5495-129">**Action URL**</span></span> | <span data-ttu-id="c5495-130">类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。</span><span class="sxs-lookup"><span data-stu-id="c5495-130">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   | <span data-ttu-id="c5495-131">**信号 URL**</span><span class="sxs-lookup"><span data-stu-id="c5495-131">**Signal URL**</span></span> | <span data-ttu-id="c5495-132">类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。</span><span class="sxs-lookup"><span data-stu-id="c5495-132">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |
   |  <span data-ttu-id="c5495-133">**同步 URL**</span><span class="sxs-lookup"><span data-stu-id="c5495-133">**Sync URL**</span></span>  | <span data-ttu-id="c5495-134">类型**https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**。</span><span class="sxs-lookup"><span data-stu-id="c5495-134">Type **https://<contoso_machine>/BTARNApp/RNIFReceive.aspx**.</span></span> |


4. <span data-ttu-id="c5495-135">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="c5495-135">Click **OK**.</span></span>  

5. <span data-ttu-id="c5495-136">右键单击**Fabrikam_To_Contoso_3A2**协议，然后单击**激活**。</span><span class="sxs-lookup"><span data-stu-id="c5495-136">Right-click the **Fabrikam_To_Contoso_3A2** agreement and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c5495-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5495-137">See Also</span></span>  
 [<span data-ttu-id="c5495-138">步骤 6：创建 Fabrikam 3A4 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="c5495-138">Step 6: Creating the Fabrikam 3A4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-6-creating-the-fabrikam-3a4-trading-partner-agreement.md)