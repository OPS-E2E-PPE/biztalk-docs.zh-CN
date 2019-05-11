---
title: 步骤 4：创建映射 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2f7f1f6d-0e57-4a65-b91d-c81fcc832961
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6cf9def7682b9334af451b5230cc2790fb7a6021
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392544"
---
# <a name="step-4-create-the-map"></a><span data-ttu-id="e0126-102">步骤 4：创建映射</span><span class="sxs-lookup"><span data-stu-id="e0126-102">Step 4: Create the Map</span></span>
<span data-ttu-id="e0126-103">![步骤 4 5](../core/media/step-4of5.gif "Step_4of5")</span><span class="sxs-lookup"><span data-stu-id="e0126-103">![Step 4 of 5](../core/media/step-4of5.gif "Step_4of5")</span></span>  
  
 <span data-ttu-id="e0126-104">**若要完成的时间：** 6 分钟</span><span class="sxs-lookup"><span data-stu-id="e0126-104">**Time to complete:** 6 minutes</span></span>  
  
 <span data-ttu-id="e0126-105">**目标：** 在此步骤中，创建请求消息转换为 RequestDecline 消息的映射。</span><span class="sxs-lookup"><span data-stu-id="e0126-105">**Objective:** In this step, you create a map that transforms Request message to RequestDecline message.</span></span>  
  
 <span data-ttu-id="e0126-106">**目的：** 此映射确保返回到仓库库存系统的请求拒绝消息中包含请求 ID 号和总计。</span><span class="sxs-lookup"><span data-stu-id="e0126-106">**Purpose:** The map ensures that the request ID number and the grand total are included in the request decline message returned to the warehouse inventory system.</span></span> <span data-ttu-id="e0126-107">使用 BizTalk 映射器将传入消息中的字段链接到传出消息定义的字段。</span><span class="sxs-lookup"><span data-stu-id="e0126-107">You use BizTalk Mapper to link fields in an incoming message to fields defined for the outgoing message.</span></span> <span data-ttu-id="e0126-108">这是必需的因为这两条消息不具有相同的架构结构。</span><span class="sxs-lookup"><span data-stu-id="e0126-108">This is necessary because these two messages do not have the same schema structure.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e0126-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="e0126-109">Prerequisites</span></span>  
 <span data-ttu-id="e0126-110">在开始此步骤之前，请注意以下要求：</span><span class="sxs-lookup"><span data-stu-id="e0126-110">Note the following requirements before you begin this step:</span></span>  
  
-   <span data-ttu-id="e0126-111">在开始此步骤之前，必须完成[步骤 2:创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md)和[步骤 3:创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md)。</span><span class="sxs-lookup"><span data-stu-id="e0126-111">Before you begin this step you must complete [Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) and [Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md).</span></span>  
  
## <a name="procedures"></a><span data-ttu-id="e0126-112">过程</span><span class="sxs-lookup"><span data-stu-id="e0126-112">Procedures</span></span>  
 <span data-ttu-id="e0126-113">此映射依赖于 Request 架构和 RequestDecline 架构。</span><span class="sxs-lookup"><span data-stu-id="e0126-113">The map depends on the Request schema and the RequestDecline schema.</span></span>  <span data-ttu-id="e0126-114">在地图上使用它们之前，您得多编译具有架构的项目。</span><span class="sxs-lookup"><span data-stu-id="e0126-114">You much compile the project with the schema before you can use them on a map.</span></span>  
  
#### <a name="to-compile-the-eaischemas-project"></a><span data-ttu-id="e0126-115">若要编译 EAISchemas 项目</span><span class="sxs-lookup"><span data-stu-id="e0126-115">To compile the EAISchemas project</span></span>  
  
-   <span data-ttu-id="e0126-116">在解决方案资源管理器中右键单击**EAISchemas**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="e0126-116">In Solution Explorer, right-click **EAISchemas**, and then click **Build**.</span></span>  
  
#### <a name="to-create-the-map"></a><span data-ttu-id="e0126-117">若要创建映射</span><span class="sxs-lookup"><span data-stu-id="e0126-117">To create the map</span></span>  
  
1.  <span data-ttu-id="e0126-118">在解决方案资源管理器中右键单击**EAISchemas**项目，指向**添加**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="e0126-118">In Solution Explorer, right-click the **EAISchemas** project, point to **Add**, and then click **New Item**.</span></span>  
  
2.  <span data-ttu-id="e0126-119">在中**添加新项-EAISchemas**对话框框中，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e0126-119">In the **Add New Item - EAISchemas** dialog box, do the following:</span></span>  
  
    |<span data-ttu-id="e0126-120">使用此选项</span><span class="sxs-lookup"><span data-stu-id="e0126-120">Use this</span></span>|<span data-ttu-id="e0126-121">执行的操作</span><span class="sxs-lookup"><span data-stu-id="e0126-121">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="e0126-122">**已安装的模板**</span><span class="sxs-lookup"><span data-stu-id="e0126-122">**Installed Templates**</span></span>|<span data-ttu-id="e0126-123">单击**地图文件**，然后单击**映射**。</span><span class="sxs-lookup"><span data-stu-id="e0126-123">Click **Map Files**, and then click **Map**.</span></span>|  
    |<span data-ttu-id="e0126-124">**名称**</span><span class="sxs-lookup"><span data-stu-id="e0126-124">**Name**</span></span>|<span data-ttu-id="e0126-125">类型**MapToReqDecline.btm**。</span><span class="sxs-lookup"><span data-stu-id="e0126-125">Type **MapToReqDecline.btm**.</span></span>|  
  
3.  <span data-ttu-id="e0126-126">单击 **“添加”**。</span><span class="sxs-lookup"><span data-stu-id="e0126-126">Click **Add**.</span></span>  
  
     <span data-ttu-id="e0126-127">下图显示了源架构、 目标架构和映射器网格。</span><span class="sxs-lookup"><span data-stu-id="e0126-127">The following figure shows the Source Schema, Destination Schema, and Mapper Grid.</span></span>  
  
     <span data-ttu-id="e0126-128">![MapToReqDenied map](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")</span><span class="sxs-lookup"><span data-stu-id="e0126-128">![MapToReqDenied map](../core/media/tut1-maptoreqden1.jpg "Tut1_MapToReqDen1")</span></span>  
  
4.  <span data-ttu-id="e0126-129">在中**源架构**窗格中，单击**打开源架构**。</span><span class="sxs-lookup"><span data-stu-id="e0126-129">In the **Source Schema** pane, click **Open Source Schema**.</span></span>  
  
5.  <span data-ttu-id="e0126-130">在中**BizTalk 类型选取器**对话框框中，展开**EAISchemas**，展开**架构**，单击**EAISchemas.Request**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e0126-130">In the **BizTalk Type Picker** dialog box, expand **EAISchemas**, expand **Schemas**, click **EAISchemas.Request**, and then click **OK**.</span></span>  
  
6.  <span data-ttu-id="e0126-131">在中**源架构**窗格中，右键单击**\<架构\>**，然后单击**展开树节点**。</span><span class="sxs-lookup"><span data-stu-id="e0126-131">In the **Source Schema** pane, right-click **\<Schema\>**, and then click **Expand Tree Node**.</span></span>  
  
7.  <span data-ttu-id="e0126-132">在中**目标架构**窗格中，单击**打开目标架构**。</span><span class="sxs-lookup"><span data-stu-id="e0126-132">In the **Destination Schema** pane, click **Open Destination Schema**.</span></span>  
  
8.  <span data-ttu-id="e0126-133">在中**BizTalk 类型选取器**对话框框中，展开**EAISchemas**，展开**架构**，单击**EAISchemas.RequestDecline**，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="e0126-133">In the **BizTalk Type Picker** dialog box, expand **EAISchemas**, expand **Schemas**, click **EAISchemas.RequestDecline**, and then click **OK**.</span></span>  
  
9. <span data-ttu-id="e0126-134">在中**目标架构**窗格中，右键单击**\<架构\>**，然后单击**展开树节点**。</span><span class="sxs-lookup"><span data-stu-id="e0126-134">In the **Destination Schema** pane, right-click **\<Schema\>**, and then click **Expand Tree Node**.</span></span>  
  
10. <span data-ttu-id="e0126-135">在中**源架构**窗格中，拖动**ReqID**字段**ReqID**中**目标架构**窗格。</span><span class="sxs-lookup"><span data-stu-id="e0126-135">In the **Source Schema** pane, drag the **ReqID** field to the **ReqID** in the **Destination Schema** pane.</span></span> <span data-ttu-id="e0126-136">连接两个元素将显示的行。</span><span class="sxs-lookup"><span data-stu-id="e0126-136">A line appears connecting the two elements.</span></span>  
  
11. <span data-ttu-id="e0126-137">在中**源架构**窗格中，拖动**GrandTotal**字段**GrandTotal**字段中**目标架构**窗格，可以将数据映射从另一个架构。</span><span class="sxs-lookup"><span data-stu-id="e0126-137">In the **Source Schema** pane, drag the **GrandTotal** field to the **GrandTotal** field in the **Destination Schema** pane to map the data from one schema to the other.</span></span>  
  
12. <span data-ttu-id="e0126-138">上**文件**菜单上，单击**全部保存**以保存所做的工作。</span><span class="sxs-lookup"><span data-stu-id="e0126-138">On the **File** menu, click **Save All** to save your work.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="e0126-139">我只需做了什么？</span><span class="sxs-lookup"><span data-stu-id="e0126-139">What did I just do?</span></span>  
 <span data-ttu-id="e0126-140">在此步骤中，创建的是请求消息转换为 RequestDecline 消息的映射。</span><span class="sxs-lookup"><span data-stu-id="e0126-140">In this step, you created a map that transforms Request message to RequestDecline message.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="e0126-141">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e0126-141">Next Steps</span></span>  
 <span data-ttu-id="e0126-142">生成 EAISchemas 项目。</span><span class="sxs-lookup"><span data-stu-id="e0126-142">You build the EAISchemas project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0126-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0126-143">See Also</span></span>  
 <span data-ttu-id="e0126-144">[步骤 1：创建 EAISchemas 项目](../core/step-1-create-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="e0126-144">[Step 1: Create EAISchemas Project](../core/step-1-create-eaischemas-project.md) </span></span>  
 <span data-ttu-id="e0126-145">[步骤 2：创建库存请求架构](../core/step-2-create-the-inventory-request-schema.md) </span><span class="sxs-lookup"><span data-stu-id="e0126-145">[Step 2: Create the Inventory Request Schema](../core/step-2-create-the-inventory-request-schema.md) </span></span>  
 <span data-ttu-id="e0126-146">[步骤 3：创建请求拒绝架构](../core/step-3-create-the-request-decline-schema.md) </span><span class="sxs-lookup"><span data-stu-id="e0126-146">[Step 3: Create the Request Decline Schema](../core/step-3-create-the-request-decline-schema.md) </span></span>  
 <span data-ttu-id="e0126-147">[步骤 4：创建映射](../core/step-4-create-the-map.md) </span><span class="sxs-lookup"><span data-stu-id="e0126-147">[Step 4: Create the Map](../core/step-4-create-the-map.md) </span></span>  
 <span data-ttu-id="e0126-148">[步骤 5：生成 EAISchemas 项目](../core/step-5-build-the-eaischemas-project.md) </span><span class="sxs-lookup"><span data-stu-id="e0126-148">[Step 5: Build the EAISchemas Project](../core/step-5-build-the-eaischemas-project.md) </span></span>  
 [<span data-ttu-id="e0126-149">使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="e0126-149">Creating Maps Using BizTalk Mapper</span></span>](../core/creating-maps-using-biztalk-mapper.md)