---
title: 步骤 6：创建 Contoso 3A4 贸易合作伙伴协议 |Microsoft Docs
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
ms.assetid: a20e40d8-7e3b-4930-8921-056ffddd08ea
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eecadae50658cefe6ed8868be673b9b214b8b9d0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280691"
---
# <a name="step-6-creating-the-contoso-3a4-trading-partner-agreement"></a><span data-ttu-id="902a6-102">步骤 6：创建 Contoso 3A4 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="902a6-102">Step 6: Creating the Contoso 3A4 Trading Partner Agreement</span></span>
<span data-ttu-id="902a6-103">在此步骤中，创建 Contoso 和 Fabrikam 使用 Microsoft® 之间的贸易合作伙伴协议[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="902a6-103">In this step, you create a trading partner agreement between Contoso and Fabrikam using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span> <span data-ttu-id="902a6-104">创建新的贸易合作伙伴协议为 3A4 合作伙伴接口流程 (PIP)。</span><span class="sxs-lookup"><span data-stu-id="902a6-104">You create a new trading partner agreement for the 3A4 Partner Interface Process (PIP).</span></span>  

### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="902a6-105">若要启动 BTARN 管理控制台</span><span class="sxs-lookup"><span data-stu-id="902a6-105">To start the BTARN Management Console</span></span>  

- <span data-ttu-id="902a6-106">单击**启动**，依次指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="902a6-106">Click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  

### <a name="to-create-the-3a4-trading-partner-agreement"></a><span data-ttu-id="902a6-107">若要创建 3A4 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="902a6-107">To create the 3A4 trading partner agreement</span></span>  

1. <span data-ttu-id="902a6-108">在中**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**协议**，指向**新建**，然后单击**协议**.</span><span class="sxs-lookup"><span data-stu-id="902a6-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="902a6-109">在新协议属性对话框中，在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="902a6-109">In the New Agreement Properties dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="902a6-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="902a6-110">Use this</span></span>          |                       <span data-ttu-id="902a6-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="902a6-111">To do this</span></span>                       |
   |---------------------------|--------------------------------------------------------|
   |         <span data-ttu-id="902a6-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="902a6-112">**Name**</span></span>          |           <span data-ttu-id="902a6-113">类型**Fabrikam_To_Contoso_3A4**。</span><span class="sxs-lookup"><span data-stu-id="902a6-113">Type **Fabrikam_To_Contoso_3A4**.</span></span>            |
   | <span data-ttu-id="902a6-114">**过程配置**</span><span class="sxs-lookup"><span data-stu-id="902a6-114">**Process Configuration**</span></span> |   <span data-ttu-id="902a6-115">选择**STD_3A4_V02.02**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="902a6-115">Select **STD_3A4_V02.02** from the drop-down list.</span></span>   |
   |    <span data-ttu-id="902a6-116">**我的组织**</span><span class="sxs-lookup"><span data-stu-id="902a6-116">**My Organization**</span></span>    |      <span data-ttu-id="902a6-117">选择**Contoso**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="902a6-117">Select **Contoso** from the drop-down list.</span></span>       |
   | <span data-ttu-id="902a6-118">**合作伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="902a6-118">**Partner Organization**</span></span>  |      <span data-ttu-id="902a6-119">选择**Fabrikam**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="902a6-119">Select **Fabrikam** from the drop-down list.</span></span>      |
   |     <span data-ttu-id="902a6-120">**RNIF 版本**</span><span class="sxs-lookup"><span data-stu-id="902a6-120">**RNIF Version**</span></span>      |     <span data-ttu-id="902a6-121">选择**V02.00.01**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="902a6-121">Select **V02.00.01** from the drop-down list.</span></span>      |
   |       <span data-ttu-id="902a6-122">**本组织角色**</span><span class="sxs-lookup"><span data-stu-id="902a6-122">**Home Role**</span></span>       | <span data-ttu-id="902a6-123">选择**卖方 （响应方）** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="902a6-123">Select **Seller (Responder)** from the drop-down list.</span></span> |
   |         <span data-ttu-id="902a6-124">**Usage**</span><span class="sxs-lookup"><span data-stu-id="902a6-124">**Usage**</span></span>         |        <span data-ttu-id="902a6-125">选择**测试**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="902a6-125">Select **Test** from the drop down-list.</span></span>        |


3. <span data-ttu-id="902a6-126">上**端口**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="902a6-126">On the **Ports** tab, do the following:</span></span>  


   |    <span data-ttu-id="902a6-127">使用此选项</span><span class="sxs-lookup"><span data-stu-id="902a6-127">Use this</span></span>    |                          <span data-ttu-id="902a6-128">执行的操作</span><span class="sxs-lookup"><span data-stu-id="902a6-128">To do this</span></span>                           |
   |----------------|---------------------------------------------------------------|
   | <span data-ttu-id="902a6-129">**操作 URL**</span><span class="sxs-lookup"><span data-stu-id="902a6-129">**Action URL**</span></span> | <span data-ttu-id="902a6-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="902a6-130">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   | <span data-ttu-id="902a6-131">**信号 URL**</span><span class="sxs-lookup"><span data-stu-id="902a6-131">**Signal URL**</span></span> | <span data-ttu-id="902a6-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="902a6-132">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |
   |  <span data-ttu-id="902a6-133">**同步 URL**</span><span class="sxs-lookup"><span data-stu-id="902a6-133">**Sync URL**</span></span>  | <span data-ttu-id="902a6-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span><span class="sxs-lookup"><span data-stu-id="902a6-134">Type **https://<fabrikam_machine>/BTARNApp/RNIFReceive.aspx**</span></span> |


4. <span data-ttu-id="902a6-135">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="902a6-135">Click **OK**.</span></span>  

5. <span data-ttu-id="902a6-136">右键单击**Fabrikam_To_Contoso_3A4**协议，然后单击**激活**。</span><span class="sxs-lookup"><span data-stu-id="902a6-136">Right-click the **Fabrikam_To_Contoso_3A4** agreement and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="902a6-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="902a6-137">See Also</span></span>  
 [<span data-ttu-id="902a6-138">步骤 7：生成和部署 DoubleAction SDK 示例</span><span class="sxs-lookup"><span data-stu-id="902a6-138">Step 7: Building and Deploying the DoubleAction SDK Sample</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-7-building-and-deploying-the-doubleaction-sdk-sample.md)