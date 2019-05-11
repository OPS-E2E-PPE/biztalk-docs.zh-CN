---
title: 教程 2:员工-采购订单流程使用 SQL 适配器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eeb4dd1e-209a-47eb-9c0e-a138e02f0ff2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fa2e0968743f88c9ae7d5b5ca683f0fb46d81f5c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65367489"
---
# <a name="tutorial-2-employee---purchase-order-process-using-the-sql-adapter"></a><span data-ttu-id="61d21-102">教程 2:员工-采购订单流程使用 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="61d21-102">Tutorial 2: Employee - Purchase Order Process using the SQL adapter</span></span>
<span data-ttu-id="61d21-103">在本教程中，将自动在其中放置设备的采购部门订购每次新员工加入组织的过程。</span><span class="sxs-lookup"><span data-stu-id="61d21-103">In this tutorial, you are automating the process where the Purchases department that places an equipment order every time a new employee joins the organization.</span></span> <span data-ttu-id="61d21-104">在中维护员工详细信息和采购订单详细信息**员工**并**Purchase_Order**表分别，SQL Server 数据库中。</span><span class="sxs-lookup"><span data-stu-id="61d21-104">Both employee details and purchase order details are maintained in **Employee** and **Purchase_Order** tables respectively, in a SQL Server database.</span></span> <span data-ttu-id="61d21-105">通过更新 SQL Server 数据库中的 Purchase_Order 表并发送一封电子邮件，采购部门将得到通知。</span><span class="sxs-lookup"><span data-stu-id="61d21-105">The Purchases department is informed by updating the Purchase_Order table in the SQL Server database and by sending an e-mail.</span></span> <span data-ttu-id="61d21-106">在进程中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="61d21-106">Within the process, the following actions occur:</span></span>  
  
1. <span data-ttu-id="61d21-107">适配器接收的通知每次**员工**更新表。</span><span class="sxs-lookup"><span data-stu-id="61d21-107">The adapter receives a notification each time the **Employee** table is updated.</span></span> <span data-ttu-id="61d21-108">然后，适配器向 BizTalk 业务流程发送通知。</span><span class="sxs-lookup"><span data-stu-id="61d21-108">The adapter then sends a notification to the BizTalk orchestration.</span></span>  
  
2. <span data-ttu-id="61d21-109">BizTalk 业务流程计算出通知是一条新记录插入到**员工**表。</span><span class="sxs-lookup"><span data-stu-id="61d21-109">The BizTalk orchestration figures out whether the notification is for a new record inserted into the **Employee** table.</span></span> <span data-ttu-id="61d21-110">如果通知是任何其他操作上**员工**表中，业务流程不会执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="61d21-110">If the notification is for any other operation on the **Employee** table, the orchestration does not perform any operation.</span></span>  
  
3. <span data-ttu-id="61d21-111">如果通知是插入操作上**员工**表中，通知已添加一个新雇员记录，该业务流程使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]读取新记录的详细信息。</span><span class="sxs-lookup"><span data-stu-id="61d21-111">If the notification is for an Insert operation on the **Employee** table, notifying that a new employee record was added, the orchestration uses the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to read the details of the new record.</span></span>  
  
4. <span data-ttu-id="61d21-112">业务流程收到响应，其中包含新添加的员工记录的详细信息。</span><span class="sxs-lookup"><span data-stu-id="61d21-112">The orchestration receives a response that contains the details of the new added employee record.</span></span> <span data-ttu-id="61d21-113">业务流程映射**Employee_ID**并**指定**插入操作的请求消息的响应中字段上**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="61d21-113">The orchestration maps the **Employee_ID** and **Designation** fields in the response to the request message for the Insert operation on the **Purchase_Order** table.</span></span>  
  
5. <span data-ttu-id="61d21-114">该业务流程将使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上执行插入操作**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="61d21-114">The orchestration then uses the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform an Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="61d21-115">插入操作的响应作为电子邮件发送给采购部门。</span><span class="sxs-lookup"><span data-stu-id="61d21-115">The response for the Insert operation is sent to the Purchases department as an e-mail.</span></span>  
  
## <a name="about-the-database-objects-used-in-this-sample"></a><span data-ttu-id="61d21-116">在此示例中使用的数据库对象</span><span class="sxs-lookup"><span data-stu-id="61d21-116">About the Database Objects Used in this Sample</span></span>  
 <span data-ttu-id="61d21-117">本教程使用示例随附的 SQL 脚本创建的数据库对象。</span><span class="sxs-lookup"><span data-stu-id="61d21-117">This tutorial uses the database objects created by the SQL script shipped with the samples.</span></span> <span data-ttu-id="61d21-118">有关脚本和示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="61d21-118">For more information about the script and the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="61d21-119">将在本教程中使用的数据库对象包括：</span><span class="sxs-lookup"><span data-stu-id="61d21-119">The database objects that you will use in this tutorial are:</span></span>  
  
- <span data-ttu-id="61d21-120">**ADAPTER_SAMPLES**数据库。</span><span class="sxs-lookup"><span data-stu-id="61d21-120">**ADAPTER_SAMPLES** database.</span></span>  
  
- <span data-ttu-id="61d21-121">**员工**并**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="61d21-121">**Employee** and **Purchase_Order** tables.</span></span>  
  
- <span data-ttu-id="61d21-122">**UPDATE_EMPLOYEE**存储过程。</span><span class="sxs-lookup"><span data-stu-id="61d21-122">**UPDATE_EMPLOYEE** stored procedure.</span></span>  
  
  <span data-ttu-id="61d21-123">在运行 SQL 脚本的示例时创建所有这些数据库对象。</span><span class="sxs-lookup"><span data-stu-id="61d21-123">All these database objects are created when you run the SQL script provided with the sample.</span></span> <span data-ttu-id="61d21-124">请确保在开始本教程之前运行脚本。</span><span class="sxs-lookup"><span data-stu-id="61d21-124">Make sure you run the script before you start with the tutorial.</span></span>  
  
## <a name="sample-based-on-this-tutorial"></a><span data-ttu-id="61d21-125">基于本教程的示例</span><span class="sxs-lookup"><span data-stu-id="61d21-125">Sample Based on This Tutorial</span></span>  
 <span data-ttu-id="61d21-126">示例中， **Employee_PurchaseOrder**，后者基于本教程还提供与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="61d21-126">A sample, **Employee_PurchaseOrder**, which is based on this tutorial is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="61d21-127">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="61d21-127">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
 <span data-ttu-id="61d21-128">我们建议你完成本教程中，完全以了解如何创建使用该适配器的 BizTalk 项目，然后查看作为参考示例。</span><span class="sxs-lookup"><span data-stu-id="61d21-128">We recommend that you go through the tutorial completely to understand how to create BizTalk projects using the adapter, and then look at the sample as a reference.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="61d21-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="61d21-129">In This Section</span></span>  
  
-   [<span data-ttu-id="61d21-130">第 1 课：生成架构并创建消息</span><span class="sxs-lookup"><span data-stu-id="61d21-130">Lesson 1: Generate Schemas and Create Messages</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)  
  
-   [<span data-ttu-id="61d21-131">第 2 课：接收和筛选通知</span><span class="sxs-lookup"><span data-stu-id="61d21-131">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)  
  
-   [<span data-ttu-id="61d21-132">第 3 课：执行存储过程以选择新添加的员工</span><span class="sxs-lookup"><span data-stu-id="61d21-132">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)  
  
-   [<span data-ttu-id="61d21-133">第 4 课：在采购订单表中执行插入操作</span><span class="sxs-lookup"><span data-stu-id="61d21-133">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)  
  
-   [<span data-ttu-id="61d21-134">第 5 课：部署解决方案</span><span class="sxs-lookup"><span data-stu-id="61d21-134">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)