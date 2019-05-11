---
title: 设置 CIDX eStandards 消息交换 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- CIDX, configuring message exchange
ms.assetid: 90468459-cef7-436b-8c0b-3a7455a091c3
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c6f1045e3a9562821c64e74df300ccbf9ab279d7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65281727"
---
# <a name="setting-up-cidx-estandards-message-exchange"></a><span data-ttu-id="8a708-102">设置 CIDX eStandards 消息交换</span><span class="sxs-lookup"><span data-stu-id="8a708-102">Setting Up CIDX eStandards Message Exchange</span></span>
<span data-ttu-id="8a708-103">本主题介绍如何设置化工数据交换 (CIDX) eStandards 消息交换。</span><span class="sxs-lookup"><span data-stu-id="8a708-103">This topic describes how to set up Chemical Data Exchange (CIDX) eStandards message exchange.</span></span> <span data-ttu-id="8a708-104">CIDX 需要设置以下三个属性：</span><span class="sxs-lookup"><span data-stu-id="8a708-104">CIDX requires that you set the following three properties:</span></span>  
  
- <span data-ttu-id="8a708-105">`Standard` 为流程配置设置中的属性**CIDX**</span><span class="sxs-lookup"><span data-stu-id="8a708-105">`Standard` property in the process configuration settings to **CIDX**</span></span>  
  
- <span data-ttu-id="8a708-106">`Is Single Action` 为流程配置设置中的属性 `True`</span><span class="sxs-lookup"><span data-stu-id="8a708-106">`Is Single Action` property in the process configuration settings to `True`</span></span>  
  
- <span data-ttu-id="8a708-107">`0A1 agreement` 在贸易合作伙伴协议中为属性**非 0A1**</span><span class="sxs-lookup"><span data-stu-id="8a708-107">`0A1 agreement` property in the trading partner agreement to **No 0A1**</span></span>  
  
  <span data-ttu-id="8a708-108">有关 CIDX 与 RosettaNet 之间的差异的信息，请参阅[CIDX 支持](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md)。</span><span class="sxs-lookup"><span data-stu-id="8a708-108">For information about the differences between CIDX and RosettaNet, see [CIDX Support](../../adapters-and-accelerators/accelerator-rosettanet/cidx-support.md).</span></span>  
  
### <a name="to-set-up-cidx-message-exchange"></a><span data-ttu-id="8a708-109">若要设置 CIDX 消息交换</span><span class="sxs-lookup"><span data-stu-id="8a708-109">To set up CIDX message exchange</span></span>  
  
1. <span data-ttu-id="8a708-110">单击**启动**，依次指向**所有程序**，指向**Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]，然后单击[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]**管理控制台**.</span><span class="sxs-lookup"><span data-stu-id="8a708-110">Click **Start**, point to **All Programs**, point to **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)], and then click [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **Management Console**.</span></span>  
  
2. <span data-ttu-id="8a708-111">在中[!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]管理控制台中，展开[!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8a708-111">In the [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] Management Console, expand [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].</span></span>  
  
3. <span data-ttu-id="8a708-112">右键单击**流程配置设置**，依次指向**新建**，然后单击**过程配置**。</span><span class="sxs-lookup"><span data-stu-id="8a708-112">Right-click **Process Configuration Settings**, point to **New**, and then click **Process Configuration**.</span></span>  
  
4. <span data-ttu-id="8a708-113">在新流程配置属性对话框中，在**常规**选项卡上，对于**标准**属性中，选择**CIDX**。</span><span class="sxs-lookup"><span data-stu-id="8a708-113">In the New Process Configuration Properties dialog box, on the **General** tab, for the **Standard** property, select **CIDX**.</span></span>  
  
5. <span data-ttu-id="8a708-114">上**活动**选项卡上，对于**是否为单一操作**属性中，选择**True**。</span><span class="sxs-lookup"><span data-stu-id="8a708-114">On the **Activity** tab, for the **Is Single Action** property, select **True**.</span></span>  
  
6. <span data-ttu-id="8a708-115">根据需要请输入其他流程配置设置。</span><span class="sxs-lookup"><span data-stu-id="8a708-115">Enter other process configuration settings as needed.</span></span> <span data-ttu-id="8a708-116">有关这些设置的信息，请参阅中的表[如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="8a708-116">For information about these settings, see the table in [How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md).</span></span>  
  
7. <span data-ttu-id="8a708-117">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="8a708-117">Click **OK**.</span></span>  
  
8. <span data-ttu-id="8a708-118">右键单击**协议**，依次指向**新建**，然后单击**协议**。</span><span class="sxs-lookup"><span data-stu-id="8a708-118">Right-click **Agreements**, point to **New**, and then click **Agreement**.</span></span>  
  
9. <span data-ttu-id="8a708-119">上**常规**，**端口**，**协议**，以及**自定义属性**选项卡上，输入的各种设置的值。</span><span class="sxs-lookup"><span data-stu-id="8a708-119">On the **General**, **Ports**, **Protocol**, and **Custom Properties** tabs, enter the values for the various settings.</span></span> <span data-ttu-id="8a708-120">有关这些设置的信息，请参阅中的表[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md)。</span><span class="sxs-lookup"><span data-stu-id="8a708-120">For information about these settings, see the table in [Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md).</span></span>  
  
10. <span data-ttu-id="8a708-121">在新协议属性对话框中，在**常规**选项卡上，对于**0A1 协议**属性中，选择**非 0A1**。</span><span class="sxs-lookup"><span data-stu-id="8a708-121">In the New Agreement Properties dialog box, on the **General** tab, for the **0A1 agreement** property, select **No 0A1**.</span></span>  
  
11. <span data-ttu-id="8a708-122">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="8a708-122">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a708-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8a708-123">See Also</span></span>  
 <span data-ttu-id="8a708-124">[如何创建或编辑流程配置](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span><span class="sxs-lookup"><span data-stu-id="8a708-124">[How to Create or Edit a Process Configuration](../../adapters-and-accelerators/accelerator-rosettanet/how-to-create-or-edit-a-process-configuration.md) </span></span>  
 <span data-ttu-id="8a708-125">[创建或编辑协议](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span><span class="sxs-lookup"><span data-stu-id="8a708-125">[Creating or Editing an Agreement](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-an-agreement.md) </span></span>  
 <span data-ttu-id="8a708-126">[创建或编辑本组织](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span><span class="sxs-lookup"><span data-stu-id="8a708-126">[Creating or Editing a Home Organization](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-home-organization.md) </span></span>  
 [<span data-ttu-id="8a708-127">创建或编辑合作伙伴</span><span class="sxs-lookup"><span data-stu-id="8a708-127">Creating or Editing a Partner</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/creating-or-editing-a-partner.md)