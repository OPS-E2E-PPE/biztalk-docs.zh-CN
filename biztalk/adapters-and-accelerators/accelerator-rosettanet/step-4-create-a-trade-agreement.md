---
title: 步骤 4：创建贸易协议 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, trade agreeements
- loopback tutorial, creating trade agreements
- agreements, creating
ms.assetid: 9bcb80b1-fefc-4f1c-ae03-fb736cdfd524
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2aa9be8b5435b212838a40059e784b0f54c17b36
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65280988"
---
# <a name="step-4-create-a-trade-agreement"></a><span data-ttu-id="6a4b0-102">步骤 4：创建贸易协议</span><span class="sxs-lookup"><span data-stu-id="6a4b0-102">Step 4: Create a Trade Agreement</span></span>
<span data-ttu-id="6a4b0-103">在此步骤中，创建使用 Microsoft® 主页和合作伙伴组织之间的贸易协议[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-103">In this step, you create a trade agreement between the home and partner organization using the Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console.</span></span>  

### <a name="to-create-a-trade-agreement"></a><span data-ttu-id="6a4b0-104">若要创建贸易协议</span><span class="sxs-lookup"><span data-stu-id="6a4b0-104">To create a trade agreement</span></span>  

1. <span data-ttu-id="6a4b0-105">在中**[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开**BizTalk\<版本\>Accelerator for RosettaNet**，右键单击**协议**，单击**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-105">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand **BizTalk \<version\> Accelerator for RosettaNet**, right-click **Agreements**, click **New**, and then click **Agreement**.</span></span>  

2. <span data-ttu-id="6a4b0-106">在中**新协议属性**对话框中，在**常规**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6a4b0-106">In the **New Agreement Properties** dialog box, on the **General** tab, do the following:</span></span>  


   |         <span data-ttu-id="6a4b0-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6a4b0-107">Use this</span></span>          |                     <span data-ttu-id="6a4b0-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6a4b0-108">To do this</span></span>                     |
   |---------------------------|----------------------------------------------------|
   |         <span data-ttu-id="6a4b0-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="6a4b0-109">**Name**</span></span>          |             <span data-ttu-id="6a4b0-110">类型**贸易协议**。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-110">Type **Trade Agreement**.</span></span>              |
   | <span data-ttu-id="6a4b0-111">**过程配置**</span><span class="sxs-lookup"><span data-stu-id="6a4b0-111">**Process Configuration**</span></span> | <span data-ttu-id="6a4b0-112">选择**STD_0C1_R01.02**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-112">Select **STD_0C1_R01.02** from the drop-down list.</span></span> |
   |    <span data-ttu-id="6a4b0-113">**我的组织**</span><span class="sxs-lookup"><span data-stu-id="6a4b0-113">**My organization**</span></span>    |      <span data-ttu-id="6a4b0-114">选择**主页**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-114">Select **HOME** from the drop-down list.</span></span>      |
   | <span data-ttu-id="6a4b0-115">**合作伙伴组织**</span><span class="sxs-lookup"><span data-stu-id="6a4b0-115">**Partner organization**</span></span>  |    <span data-ttu-id="6a4b0-116">选择**合作伙伴**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-116">Select **PARTNER** from the drop-down list.</span></span>     |
   |       <span data-ttu-id="6a4b0-117">**本组织角色**</span><span class="sxs-lookup"><span data-stu-id="6a4b0-117">**Home role**</span></span>       |   <span data-ttu-id="6a4b0-118">选择**发起方**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-118">Select **Initiator** from the drop-down list.</span></span>    |


3. <span data-ttu-id="6a4b0-119">在中**新协议属性**对话框中，在**端口**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6a4b0-119">In the **New Agreement Properties** dialog box, on the **Ports** tab, do the following:</span></span>  


   |    <span data-ttu-id="6a4b0-120">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6a4b0-120">Use this</span></span>    |                                         <span data-ttu-id="6a4b0-121">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6a4b0-121">To do this</span></span>                                         |
   |----------------|--------------------------------------------------------------------------------------------|
   | <span data-ttu-id="6a4b0-122">**操作 URL**</span><span class="sxs-lookup"><span data-stu-id="6a4b0-122">**Action URL**</span></span> |                   <span data-ttu-id="6a4b0-123">类型**<http://localhost/BTARNApp/RNIFReceive.aspx>**。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-123">Type **<http://localhost/BTARNApp/RNIFReceive.aspx>**.</span></span>                   |
   | <span data-ttu-id="6a4b0-124">**信号 URL**</span><span class="sxs-lookup"><span data-stu-id="6a4b0-124">**Signal URL**</span></span> |                   <span data-ttu-id="6a4b0-125">类型**<http://localhost/BTARNApp/RNIFReceive.aspx>**。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-125">Type **<http://localhost/BTARNApp/RNIFReceive.aspx>**.</span></span>                   |
   |  <span data-ttu-id="6a4b0-126">**同步 URL**</span><span class="sxs-lookup"><span data-stu-id="6a4b0-126">**Sync URL**</span></span>  | <span data-ttu-id="6a4b0-127">保留为空。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-127">Leave blank.</span></span> <span data-ttu-id="6a4b0-128">同步 URL 不需要的同步合作伙伴接口流程 (PIP)。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-128">Sync URL is not required for the synchronous Partner Interface Process (PIP).</span></span> |


4. <span data-ttu-id="6a4b0-129">单击**Apply**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-129">Click **Apply**, and then click **OK**.</span></span>  

   <span data-ttu-id="6a4b0-130">创建贸易协议后，必须激活它。</span><span class="sxs-lookup"><span data-stu-id="6a4b0-130">After you create the trade agreement, you must activate it.</span></span>  

### <a name="to-activate-the-trade-agreement"></a><span data-ttu-id="6a4b0-131">若要激活贸易协议</span><span class="sxs-lookup"><span data-stu-id="6a4b0-131">To activate the trade agreement</span></span>  

- <span data-ttu-id="6a4b0-132">在中[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，单击**协议**，右键单击**贸易协议**在结果窗格中，然后单击**激活**.</span><span class="sxs-lookup"><span data-stu-id="6a4b0-132">In the [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], click **Agreements**, right-click **Trade Agreement** in the results pane, and then click **Activate**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="6a4b0-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a4b0-133">See Also</span></span>  
 [<span data-ttu-id="6a4b0-134">步骤 5：创建镜像协议</span><span class="sxs-lookup"><span data-stu-id="6a4b0-134">Step 5: Create a Mirror Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-5-create-a-mirror-agreement.md)