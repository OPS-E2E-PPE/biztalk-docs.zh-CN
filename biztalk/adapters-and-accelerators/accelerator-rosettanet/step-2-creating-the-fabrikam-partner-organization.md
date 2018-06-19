---
title: 步骤 2： 创建 Fabrikam 合作伙伴组织 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, trading partners
- double action tutorial, creating partner organizations
- trading partners, partner organization
ms.assetid: 4d2ddc4c-2275-4faf-9a36-8a912cc06527
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: de00977edecb97420742a6510c3290cfe3c76ea5
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964963"
---
# <a name="step-2-creating-the-fabrikam-partner-organization"></a><span data-ttu-id="4bffd-102">步骤 2： 创建 Fabrikam 伙伴组织</span><span class="sxs-lookup"><span data-stu-id="4bffd-102">Step 2: Creating the Fabrikam Partner Organization</span></span>
<span data-ttu-id="4bffd-103">在此步骤中，将使用 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] 管理控制台创建新的贸易合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="4bffd-103">In this step, you use the [!INCLUDE[btsCoName](../../includes/btsconame-md.md)]® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] Management Console to create a new trading partner.</span></span> <span data-ttu-id="4bffd-104">此教程中的贸易合作伙伴为 Fabrikam 组织。</span><span class="sxs-lookup"><span data-stu-id="4bffd-104">The trading partner for this tutorial is the Fabrikam organization.</span></span>  
  
### <a name="to-start-the-btarn-management-console"></a><span data-ttu-id="4bffd-105">启动 BTARN 管理控制台</span><span class="sxs-lookup"><span data-stu-id="4bffd-105">To start the BTARN Management Console</span></span>  
  
-   <span data-ttu-id="4bffd-106">Contoso 计算机上，单击**启动**，指向**所有程序**，指向**Microsoft BizTalk\<版本\>Accelerator for RosettaNet**，然后单击 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="4bffd-106">On the Contoso computer, click **Start**, point to **All Programs**, point to **Microsoft BizTalk \<version\> Accelerator for RosettaNet**, and then click **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console.</span></span>  
  
### <a name="to-create-fabrikam-as-a-trading-partner"></a><span data-ttu-id="4bffd-107">创建 Fabrikam 作为贸易合作伙伴</span><span class="sxs-lookup"><span data-stu-id="4bffd-107">To create Fabrikam as a trading partner</span></span>  
  
1.  <span data-ttu-id="4bffd-108">在 **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** 管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，右键单击**合作伙伴**，指向**新建**，然后单击**合作伙伴**.</span><span class="sxs-lookup"><span data-stu-id="4bffd-108">In the **[!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)]** Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], right-click **Partners**, point to **New**, and then click **Partner**.</span></span>  
  
2.  <span data-ttu-id="4bffd-109">在新的合作伙伴属性对话框中，在**常规**选项卡上，执行以下 **:**</span><span class="sxs-lookup"><span data-stu-id="4bffd-109">In the New Partner Properties dialog box, on the **General** tab, do the following **:**</span></span>  
  
    |<span data-ttu-id="4bffd-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4bffd-110">Use this</span></span>|<span data-ttu-id="4bffd-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4bffd-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4bffd-112">**名称**</span><span class="sxs-lookup"><span data-stu-id="4bffd-112">**Name**</span></span>|<span data-ttu-id="4bffd-113">类型**FABRIKAM**。</span><span class="sxs-lookup"><span data-stu-id="4bffd-113">Type **FABRIKAM**.</span></span>|  
    |<span data-ttu-id="4bffd-114">**GBI**</span><span class="sxs-lookup"><span data-stu-id="4bffd-114">**GBI**</span></span>|<span data-ttu-id="4bffd-115">类型**987654321**。</span><span class="sxs-lookup"><span data-stu-id="4bffd-115">Type **987654321**.</span></span> <span data-ttu-id="4bffd-116">**注意：** 如果你已在同一台计算机上运行环回教程，你将需要输入 GBI 将不同于"987654321"的值。</span><span class="sxs-lookup"><span data-stu-id="4bffd-116">**Note:**  If you have run the Loopback tutorial on the same computer, you will have to enter a value for GBI that is different than "987654321".</span></span>|  
    |<span data-ttu-id="4bffd-117">**合作伙伴分类**</span><span class="sxs-lookup"><span data-stu-id="4bffd-117">**Partner Classification**</span></span>|<span data-ttu-id="4bffd-118">选择**购物者**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4bffd-118">Select **Shopper** from the drop-down list.</span></span>|  
    |<span data-ttu-id="4bffd-119">**签名证书**</span><span class="sxs-lookup"><span data-stu-id="4bffd-119">**Signature Certificate**</span></span>|<span data-ttu-id="4bffd-120">选择**Fabrikam 签名 [指纹]** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4bffd-120">Select **Fabrikam Signature [Thumbprint]** from the drop-down list.</span></span>|  
    |<span data-ttu-id="4bffd-121">**加密证书**</span><span class="sxs-lookup"><span data-stu-id="4bffd-121">**Encryption Certificate**</span></span>|<span data-ttu-id="4bffd-122">选择**Fabrikam 加密 [指纹]** 从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="4bffd-122">Select **Fabrikam Encryption [Thumbprint]** from the drop-down list.</span></span>|  
  
3.  <span data-ttu-id="4bffd-123">单击**联系人属性**选项卡，然后执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4bffd-123">Click the **Contact Properties** tab, and then do the following:</span></span>  
  
    |<span data-ttu-id="4bffd-124">使用此选项</span><span class="sxs-lookup"><span data-stu-id="4bffd-124">Use this</span></span>|<span data-ttu-id="4bffd-125">执行的操作</span><span class="sxs-lookup"><span data-stu-id="4bffd-125">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="4bffd-126">**联系人姓名**</span><span class="sxs-lookup"><span data-stu-id="4bffd-126">**Contact Name**</span></span>|<span data-ttu-id="4bffd-127">类型**Jane Doe**。</span><span class="sxs-lookup"><span data-stu-id="4bffd-127">Type **Jane Doe**.</span></span>|  
    |<span data-ttu-id="4bffd-128">**E-mail Address**</span><span class="sxs-lookup"><span data-stu-id="4bffd-128">**E-mail Address**</span></span>|<span data-ttu-id="4bffd-129">类型 **jdoe@fabrikam.com** 。</span><span class="sxs-lookup"><span data-stu-id="4bffd-129">Type **jdoe@fabrikam.com**.</span></span>|  
    |<span data-ttu-id="4bffd-130">**电话号码**</span><span class="sxs-lookup"><span data-stu-id="4bffd-130">**Telephone Number**</span></span>|<span data-ttu-id="4bffd-131">类型**555-555-5555**。</span><span class="sxs-lookup"><span data-stu-id="4bffd-131">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="4bffd-132">**传真号码**</span><span class="sxs-lookup"><span data-stu-id="4bffd-132">**Fax Number**</span></span>|<span data-ttu-id="4bffd-133">类型**555-555-5555**。</span><span class="sxs-lookup"><span data-stu-id="4bffd-133">Type **555-555-5555**.</span></span>|  
    |<span data-ttu-id="4bffd-134">**供应链代码**</span><span class="sxs-lookup"><span data-stu-id="4bffd-134">**Supply chain code**</span></span>|<span data-ttu-id="4bffd-135">类型**电子元件**。</span><span class="sxs-lookup"><span data-stu-id="4bffd-135">Type **Electronic Components**.</span></span>|  
  
4.  <span data-ttu-id="4bffd-136">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="4bffd-136">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bffd-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4bffd-137">See Also</span></span>  
 [<span data-ttu-id="4bffd-138">步骤 3：创建 Contoso 0C2 贸易合作伙伴协议</span><span class="sxs-lookup"><span data-stu-id="4bffd-138">Step 3: Creating the Contoso 0C2 Trading Partner Agreement</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/step-3-creating-the-contoso-0c2-trading-partner-agreement.md)