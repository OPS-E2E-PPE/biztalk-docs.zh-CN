---
title: 步骤 2： 为 BizTalk 业务流程创建消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 47a4fb98-6085-4aeb-ab39-2f2c3858d4e0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9bad2f052efa561020ba04060a8290137a08f542
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36995358"
---
# <a name="step-2-create-messages-for-biztalk-orchestrations"></a><span data-ttu-id="2b4d3-102">步骤 2： 为 BizTalk 业务流程创建消息</span><span class="sxs-lookup"><span data-stu-id="2b4d3-102">Step 2: Create Messages for BizTalk Orchestrations</span></span>
<span data-ttu-id="2b4d3-103">![步骤 2 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span><span class="sxs-lookup"><span data-stu-id="2b4d3-103">![Step 2 of 2](../../adapters-and-accelerators/adapter-sql/media/step-2of2.gif "Step_2of2")</span></span>  
  
 <span data-ttu-id="2b4d3-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="2b4d3-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="2b4d3-105">**目标：** 在此步骤中，将向 BizTalk 项目添加业务流程和为在生成的架构创建消息[步骤 1： 为操作生成架构](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-105">**Objective:** In this step, you add an orchestration to the BizTalk project and create messages for the schemas you generated in [Step 1: Generate Schema for Operations](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2b4d3-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="2b4d3-106">Prerequisites</span></span>  
 <span data-ttu-id="2b4d3-107">你必须已完成[步骤 1： 为操作生成架构](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-107">You must have completed [Step 1: Generate Schema for Operations](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md).</span></span>  
  
### <a name="to-create-messages-in-an-orchestration"></a><span data-ttu-id="2b4d3-108">若要在业务流程中创建消息</span><span class="sxs-lookup"><span data-stu-id="2b4d3-108">To create messages in an orchestration</span></span>  
  
1. <span data-ttu-id="2b4d3-109">将 BizTalk 业务流程添加到 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="2b4d3-109">Add a BizTalk orchestration to the BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]:</span></span>  
  
   1.  <span data-ttu-id="2b4d3-110">从解决方案资源管理器，右键单击 BizTalk 项目名称，指向**外**，然后单击**新项**。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-110">From Solution Explorer, right-click the BizTalk project name, point to **Add**, and then click **New Item**.</span></span>  
  
   2.  <span data-ttu-id="2b4d3-111">在中**添加新项**对话框中，从**类别**框中，单击**业务流程文件**。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-111">In the **Add New Item** dialog box, from the **Categories** box, click **Orchestration Files**.</span></span> <span data-ttu-id="2b4d3-112">从**模板**框中，单击**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-112">From the **Templates** box, click **BizTalk Orchestration**.</span></span>  
  
   3.  <span data-ttu-id="2b4d3-113">键入 BizTalk 业务流程的名称，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-113">Type a name for the BizTalk orchestration, and then click **Add**.</span></span> <span data-ttu-id="2b4d3-114">对于本教程中，输入名称`EmployeeOrch.odx`。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-114">For this tutorial, enter the name `EmployeeOrch.odx`.</span></span>  
  
2. <span data-ttu-id="2b4d3-115">打开**业务流程视图**BizTalk 项目，如果已打开的窗口。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-115">Open the **Orchestration View** window of the BizTalk project, if it is not already open.</span></span> <span data-ttu-id="2b4d3-116">若要执行此操作，请单击**视图**，依次指向**其他 Windows**，然后单击**业务流程视图**。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-116">To do so, click **View**, point to **Other Windows**, and then click **Orchestration View**.</span></span>  
  
3. <span data-ttu-id="2b4d3-117">将消息添加到业务流程。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-117">Add messages to the orchestration.</span></span>  
  
   1.  <span data-ttu-id="2b4d3-118">在中**业务流程视图**，右键单击**消息**，然后单击**新消息**。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-118">In the **Orchestration View**, right-click **Messages**, and then click **New Message**.</span></span>  
  
   2.  <span data-ttu-id="2b4d3-119">右键单击新创建的消息，然后依次**属性窗口**。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-119">Right-click the newly created message, and then select **Properties Window**.</span></span>  
  
   3.  <span data-ttu-id="2b4d3-120">在中**属性**窗格**Message_1**，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="2b4d3-120">In the **Properties** pane for **Message_1**, do the following:</span></span>  
  
       |<span data-ttu-id="2b4d3-121">使用此选项</span><span class="sxs-lookup"><span data-stu-id="2b4d3-121">Use this</span></span>|<span data-ttu-id="2b4d3-122">执行的操作</span><span class="sxs-lookup"><span data-stu-id="2b4d3-122">To do this</span></span>|  
       |--------------|----------------|  
       |<span data-ttu-id="2b4d3-123">Identifier</span><span class="sxs-lookup"><span data-stu-id="2b4d3-123">Identifier</span></span>|<span data-ttu-id="2b4d3-124">键入 `NotifyReceive`。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-124">Type `NotifyReceive`.</span></span>|  
       |<span data-ttu-id="2b4d3-125">消息类型</span><span class="sxs-lookup"><span data-stu-id="2b4d3-125">Message Type</span></span>|<span data-ttu-id="2b4d3-126">从下拉列表中，展开**架构**，然后选择**Employee_PurchaseOrder.Notification**，其中 Employee_PurchaseOrder 是 BizTalk 项目的名称。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-126">From the drop-down list, expand **Schemas**, and select **Employee_PurchaseOrder.Notification**, where Employee_PurchaseOrder is the name of your BizTalk project.</span></span> <span data-ttu-id="2b4d3-127">通知是为生成的架构**通知**操作。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-127">Notification is the schema generated for the **Notification** operation.</span></span>|  
  
   4.  <span data-ttu-id="2b4d3-128">重复上述步骤添加四个新消息，请求-响应消息设置为调用 UPDATE_EMPLOYEE 存储过程和为执行设置的另一个请求-响应消息**插入**上的操作**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-128">Repeat the previous step to add four new messages—a request-response message set for invoking the UPDATE_EMPLOYEE stored procedure and another request-response message set for performing the **Insert** operation on **Purchase_Order** table.</span></span>  
  
       |<span data-ttu-id="2b4d3-129">将标识符设置为</span><span class="sxs-lookup"><span data-stu-id="2b4d3-129">Set Identifier to</span></span>|<span data-ttu-id="2b4d3-130">将消息类型设置为</span><span class="sxs-lookup"><span data-stu-id="2b4d3-130">Set Message Type to</span></span>|  
       |-----------------------|-------------------------|  
       |<span data-ttu-id="2b4d3-131">UpdateEmployee</span><span class="sxs-lookup"><span data-stu-id="2b4d3-131">UpdateEmployee</span></span>|<span data-ttu-id="2b4d3-132">*Employee_PurchaseOrder.TypedProcedure_dbo。UPDATE_EMPLOYEE*，其中 TypedProcedure_dbo。UPDATE_EMPLOYEE 是 UPDATE_EMPLOYEE 的架构存储过程。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-132">*Employee_PurchaseOrder.TypedProcedure_dbo.UPDATE_EMPLOYEE*, where TypedProcedure_dbo.UPDATE_EMPLOYEE is the schema for the UPDATE_EMPLOYEE stored procedure.</span></span>|  
       |<span data-ttu-id="2b4d3-133">UpdateEmployeeResponse</span><span class="sxs-lookup"><span data-stu-id="2b4d3-133">UpdateEmployeeResponse</span></span>|<span data-ttu-id="2b4d3-134">*Employee_PurchaseOrder.TypedProcedure_dbo。UPDATE_EMPLOYEEResponse*</span><span class="sxs-lookup"><span data-stu-id="2b4d3-134">*Employee_PurchaseOrder.TypedProcedure_dbo.UPDATE_EMPLOYEEResponse*</span></span>|  
       |<span data-ttu-id="2b4d3-135">InsertPO</span><span class="sxs-lookup"><span data-stu-id="2b4d3-135">InsertPO</span></span>|<span data-ttu-id="2b4d3-136">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*TableOperation_dbo_Purchase_Order.Insert 所在 Purchase_Order 表上的插入操作的架构。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-136">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.Insert*, where TableOperation_dbo_Purchase_Order.Insert is the schema for the Insert operation on the Purchase_Order table.</span></span>|  
       |<span data-ttu-id="2b4d3-137">InsertPOResponse</span><span class="sxs-lookup"><span data-stu-id="2b4d3-137">InsertPOResponse</span></span>|<span data-ttu-id="2b4d3-138">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*</span><span class="sxs-lookup"><span data-stu-id="2b4d3-138">*Employee_PurchaseOrder.TableOperation_dbo_Purchase_Order.InsertResponse*</span></span>|  
  
   5.  <span data-ttu-id="2b4d3-139">保存业务流程文件和 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-139">Save the orchestration file and the BizTalk project.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="2b4d3-140">内容回顾</span><span class="sxs-lookup"><span data-stu-id="2b4d3-140">What did I just do?</span></span>  
 <span data-ttu-id="2b4d3-141">在此步骤中，创建用于调用上使用 SQL Server 执行入站和出站操作消息[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-141">In this step, you created messages for invoking performing inbound and outbound operations on SQL Server using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="2b4d3-142">后续步骤</span><span class="sxs-lookup"><span data-stu-id="2b4d3-142">Next Steps</span></span>  
 <span data-ttu-id="2b4d3-143">您将添加业务流程形状从 SQL Server 和筛选器的插入操作的通知接收通知，如中所述[第 2 课： 接收和筛选器通知](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)。</span><span class="sxs-lookup"><span data-stu-id="2b4d3-143">You add orchestration shapes to receive notification from SQL Server and filter notifications for Insert operation, as described in [Lesson 2: Receive and Filter Notifications](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b4d3-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b4d3-144">See Also</span></span>  
 <span data-ttu-id="2b4d3-145">[第 1 课： 生成架构并创建消息](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md) </span><span class="sxs-lookup"><span data-stu-id="2b4d3-145">[Lesson 1: Generate Schemas and Create Messages](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md) </span></span>  
 [<span data-ttu-id="2b4d3-146">步骤 1：为操作生成架构</span><span class="sxs-lookup"><span data-stu-id="2b4d3-146">Step 1: Generate Schema for Operations</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-generate-schema-for-operations.md)