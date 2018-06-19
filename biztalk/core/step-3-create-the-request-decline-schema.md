---
title: 步骤 3： 创建请求拒绝架构 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e1ce166c-1be1-4ef4-9d00-3da7038d4ada
caps.latest.revision: 39
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ff343c58e836bc0738f0200016308eb7a4d90b9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278549"
---
# <a name="step-3-create-the-request-decline-schema"></a><span data-ttu-id="9eee1-102">步骤 3： 创建请求拒绝架构</span><span class="sxs-lookup"><span data-stu-id="9eee1-102">Step 3: Create the Request Decline Schema</span></span>
<span data-ttu-id="9eee1-103">![步骤 5 的 3](../core/media/step-3of5.gif "Step_3of5")</span><span class="sxs-lookup"><span data-stu-id="9eee1-103">![Step 3 of 5](../core/media/step-3of5.gif "Step_3of5")</span></span>  
  
 <span data-ttu-id="9eee1-104">**完成时间：** 7 分钟</span><span class="sxs-lookup"><span data-stu-id="9eee1-104">**Time to complete:** 7 minutes</span></span>  
  
 <span data-ttu-id="9eee1-105">**目标：** 在此步骤中，创建消息的架构[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]发回到仓库如果业务流程拒绝库存补货请求。</span><span class="sxs-lookup"><span data-stu-id="9eee1-105">**Objective:** In this step, you create the schema for the message [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends back to the warehouse if the business process rejects the inventory replenishment request.</span></span>  
  
 <span data-ttu-id="9eee1-106">**用途：** 架构定义的数据和请求拒绝消息的结构。</span><span class="sxs-lookup"><span data-stu-id="9eee1-106">**Purpose:** The schema defines the data and the structure of the request decline message.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="9eee1-107">使用架构来识别并与消息中的数据进行交互。</span><span class="sxs-lookup"><span data-stu-id="9eee1-107"> uses the schema to identify and interact with the data in the message.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="9eee1-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="9eee1-108">Prerequisites</span></span>  
 <span data-ttu-id="9eee1-109">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="9eee1-109">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="9eee1-110">在开始此步骤之前必须完成[步骤 1： 创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md)。</span><span class="sxs-lookup"><span data-stu-id="9eee1-110">Before you begin this step you must complete [Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="9eee1-111">过程</span><span class="sxs-lookup"><span data-stu-id="9eee1-111">Procedures</span></span>  
  
#### <a name="to-create-the-request-decline-schema"></a><span data-ttu-id="9eee1-112">创建“请求拒绝”架构</span><span class="sxs-lookup"><span data-stu-id="9eee1-112">To create the Request Decline schema</span></span>  
  
1.  <span data-ttu-id="9eee1-113">在解决方案资源管理器，右键单击**EAISchemas**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="9eee1-113">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="9eee1-114">在**添加新项-EAISchemas**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="9eee1-114">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="9eee1-115">使用此选项</span><span class="sxs-lookup"><span data-stu-id="9eee1-115">Use this</span></span>|<span data-ttu-id="9eee1-116">执行的操作</span><span class="sxs-lookup"><span data-stu-id="9eee1-116">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="9eee1-117">**已安装的模板**</span><span class="sxs-lookup"><span data-stu-id="9eee1-117">**Installed Templates**</span></span>|<span data-ttu-id="9eee1-118">单击**架构文件**，然后单击**架构**。</span><span class="sxs-lookup"><span data-stu-id="9eee1-118">Click **Schema Files**, and then click **Schema**.</span></span>|  
    |<span data-ttu-id="9eee1-119">**名称**</span><span class="sxs-lookup"><span data-stu-id="9eee1-119">**Name**</span></span>|<span data-ttu-id="9eee1-120">键入 `RequestDecline.xsd`。</span><span class="sxs-lookup"><span data-stu-id="9eee1-120">Type `RequestDecline.xsd`.</span></span>|  
  
3.  <span data-ttu-id="9eee1-121">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="9eee1-121">Click **Add**.</span></span>  
  
4.  <span data-ttu-id="9eee1-122">在 BizTalk 编辑器中，从架构树中，单击**根**节点以选择它。</span><span class="sxs-lookup"><span data-stu-id="9eee1-122">In BizTalk Editor, from schema tree, click the **Root** node to select it.</span></span>  
  
5.  <span data-ttu-id="9eee1-123">在属性窗格中，将的值更改**节点名称**属性`DeclineReq`，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="9eee1-123">In the Properties pane, change the value of the **Node Name** property to `DeclineReq`, and then press ENTER.</span></span>  
  
6.  <span data-ttu-id="9eee1-124">在架构树中，右键单击**DeclineReq**节点，指向**插入架构节点**，然后单击**子字段元素**。</span><span class="sxs-lookup"><span data-stu-id="9eee1-124">In schema tree, right-click the **DeclineReq** node, point to **Insert Schema Node**, and then click **Child Field Element**.</span></span>  
  
7.  <span data-ttu-id="9eee1-125">类型`ReqID`作为以及该元素，然后按 enter 键的新名称。</span><span class="sxs-lookup"><span data-stu-id="9eee1-125">Type `ReqID` as the new name for the element, and then press ENTER.</span></span>  
  
8.  <span data-ttu-id="9eee1-126">添加名为的第二个子字段元素`GrandTotal`。</span><span class="sxs-lookup"><span data-stu-id="9eee1-126">Add a second child field element named `GrandTotal`.</span></span>  
  
9. <span data-ttu-id="9eee1-127">在“文件”  菜单上，单击“全部保存” 。</span><span class="sxs-lookup"><span data-stu-id="9eee1-127">On the **File** menu, click **Save All**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="9eee1-128">内容回顾</span><span class="sxs-lookup"><span data-stu-id="9eee1-128">What did I just do?</span></span>  
 <span data-ttu-id="9eee1-129">在此步骤中，您为 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 在业务流程拒绝库存请求时发送回仓库的消息创建了架构。</span><span class="sxs-lookup"><span data-stu-id="9eee1-129">In this step, you created the schema for the message that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] sends back to the warehouse if the business process rejects the inventory request.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="9eee1-130">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9eee1-130">Next Steps</span></span>  
 <span data-ttu-id="9eee1-131">您将通过重新格式化请求消息来创建业务流程所需要用于创建请求拒绝消息的映射。</span><span class="sxs-lookup"><span data-stu-id="9eee1-131">You create the map needed by the orchestration to create request decline message by reformatting request message.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eee1-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9eee1-132">See Also</span></span>  
 [<span data-ttu-id="9eee1-133">步骤 1： 创建 EAISchemas 项目</span><span class="sxs-lookup"><span data-stu-id="9eee1-133">Step 1: Create EAISchemas Project</span></span>](../core/step-1-create-eaischemas-project.md)  
 <span data-ttu-id="9eee1-134">[步骤 2： 创建清单请求架构](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="9eee1-134">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="9eee1-135">[步骤 4： 创建代码图](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="9eee1-135">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="9eee1-136">[步骤 5： 生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="9eee1-136">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 [<span data-ttu-id="9eee1-137">创建使用 BizTalk 编辑器的架构</span><span class="sxs-lookup"><span data-stu-id="9eee1-137">Creating Schemas Using BizTalk Editor</span></span>](../core/creating-schemas-using-biztalk-editor.md)