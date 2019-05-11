---
title: 步骤 3：创建 Contoso 0 C 2 个贸易合作伙伴协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- agreements, creating
- creating, agreements
- double action tutorial, creating agreements
ms.assetid: b4267faa-5f10-4294-9890-169f1d5ad8f7
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 663254f8b0cc6d71508d99d3e7b40e9ac8faef4d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281130"
---
# <a name="step-3-creating-the-contoso-0c2-trading-partner-agreement"></a><span data-ttu-id="66453-102">步骤 3：创建 Contoso 0 C 2 个贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="66453-102">Step 3: Creating the Contoso 0C2 Trading Partner Agreement</span></span>
<span data-ttu-id="66453-103">在此步骤中，创建 Contoso 和 Fabrikam 使用 Microsoft® 之间的贸易合作伙伴协议[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="66453-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="66453-104">您创建新的贸易合作伙伴协议为 0c2 合作伙伴接口流程 (PIP)。</span><span class="sxs-lookup"><span data-stu-id="66453-104">You create a new trading partner agreement for the 0C2 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="66453-105">若要启动 BTARN 管理控制台</span><span class="sxs-lookup"><span data-stu-id="66453-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="66453-106">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="66453-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-0c2-trading-partner-agreement"></a><span data-ttu-id="66453-107">创建 0 C 2 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="66453-107">To create the 0C2 trading partner agreement</span></span>  

1. <span data-ttu-id="66453-108">在中**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**协议**，单击**新建**，然后单击**协议**.</span><span class="sxs-lookup"><span data-stu-id="66453-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, click **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="66453-109">在新协议属性对话框中，在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="66453-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="66453-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="66453-110">Use this</span></span>          |                        <span data-ttu-id="66453-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="66453-111">To do this</span></span>                         |
   |---------------------------|-----------------------------------------------------------|
   |         <span data-ttu-id="66453-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="66453-112">**Name**</span></span>          |             <span data-ttu-id="66453-113">类型**Fabrikam_To_Contoso_0C2**。</span><span class="sxs-lookup"><span data-stu-id="66453-113">Type **Fabrikam_To_Contoso_0C2**.</span></span>             |
   | <span data-ttu-id="66453-114">**过程配置**</span><span class="sxs-lookup"><span data-stu-id="66453-114">**Process configuration**</span></span> |    <span data-ttu-id="66453-115">选择**STD_0C2_R01.02**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="66453-115">Select **STD_0C2_R01.02** from the drop-down list.</span></span>     |
   |    <span data-ttu-id="66453-116">**我的组织**</span><span class="sxs-lookup"><span data-stu-id="66453-116">**My organization**</span></span>    |        <span data-ttu-id="66453-117">选择**Contoso**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="66453-117">Select **Contoso** from the drop-down list.</span></span>        |
   | <span data-ttu-id="66453-118">**合作伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="66453-118">**Partner organization**</span></span>  |       <span data-ttu-id="66453-119">选择**Fabrikam**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="66453-119">Select **Fabrikam** from the drop-down list.</span></span>        |
   |     <span data-ttu-id="66453-120">**RNIF 版本**</span><span class="sxs-lookup"><span data-stu-id="66453-120">**RNIF version**</span></span>      |       <span data-ttu-id="66453-121">选择**V02.00.01**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="66453-121">Select **V02.00.01** from the drop-down list.</span></span>       |
   |       <span data-ttu-id="66453-122">**本组织角色**</span><span class="sxs-lookup"><span data-stu-id="66453-122">**Home role**</span></span>       | <span data-ttu-id="66453-123">选择**响应方 （响应方）** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="66453-123">Select **Responder (Responder)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="66453-124">**Usage**</span><span class="sxs-lookup"><span data-stu-id="66453-124">**Usage**</span></span>         |         <span data-ttu-id="66453-125">选择**测试**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="66453-125">Select **Test** from the drop-down list.</span></span>          |


3. <span data-ttu-id="66453-126">单击**端口**选项卡，然后再执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="66453-126">Click the **Ports** tab, and then do the following:</span></span>  


   |    <span data-ttu-id="66453-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="66453-127">Use this</span></span>    |                          <span data-ttu-id="66453-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="66453-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="66453-129">**操作 URL**</span><span class="sxs-lookup"><span data-stu-id="66453-129">**Action URL**</span></span> | <span data-ttu-id="66453-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="66453-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   | <span data-ttu-id="66453-131">**信号 URL**</span><span class="sxs-lookup"><span data-stu-id="66453-131">**Signal URL**</span></span> | <span data-ttu-id="66453-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="66453-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   |  <span data-ttu-id="66453-133">**同步 URL**</span><span class="sxs-lookup"><span data-stu-id="66453-133">**Sync URL**</span></span>  | <span data-ttu-id="66453-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="66453-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |


4. <span data-ttu-id="66453-135">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="66453-135">Click **OK**.</span></span>  

5. <span data-ttu-id="66453-136">右键单击**Fabrikam_To_Contoso_0C2**协议，，然后单击**激活**。</span><span class="sxs-lookup"><span data-stu-id="66453-136">Right-click the **Fabrikam_To_Contoso_0C2** agreement, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="66453-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="66453-137">See Also</span></span>  
 [<span data-ttu-id="66453-138">步骤 4：创建 Contoso 0C4 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="66453-138">Step 4: Creating the Contoso 0C4 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-4-creating-the-contoso-0c4-trading-partner-agreement.md)