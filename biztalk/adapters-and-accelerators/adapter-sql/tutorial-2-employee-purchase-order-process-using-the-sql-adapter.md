---
title: 教程 2： 员工-采购订单过程使用 SQL 适配器 |Microsoft 文档
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
ms.openlocfilehash: 8fca0c11aeb1f84a5e9f05a4df4f995b7c2b52e5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223229"
---
# <a name="tutorial-2-employee---purchase-order-process-using-the-sql-adapter"></a><span data-ttu-id="f1aad-102">教程 2： 员工-采购订单过程使用 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="f1aad-102">Tutorial 2: Employee - Purchase Order Process using the SQL adapter</span></span>
<span data-ttu-id="f1aad-103">在本教程中，你要实现自动化其中将设备的购买部门排序每次新员工加入企业组织的过程。</span><span class="sxs-lookup"><span data-stu-id="f1aad-103">In this tutorial, you are automating the process where the Purchases department that places an equipment order every time a new employee joins the organization.</span></span> <span data-ttu-id="f1aad-104">员工详细信息和购买订单详细信息保留在**员工**和**Purchase_Order**分别，表中的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="f1aad-104">Both employee details and purchase order details are maintained in **Employee** and **Purchase_Order** tables respectively, in a SQL Server database.</span></span> <span data-ttu-id="f1aad-105">通过更新 SQL Server 数据库中的 Purchase_Order 表并发送一封电子邮件，购买部门将得到通知。</span><span class="sxs-lookup"><span data-stu-id="f1aad-105">The Purchases department is informed by updating the Purchase_Order table in the SQL Server database and by sending an e-mail.</span></span> <span data-ttu-id="f1aad-106">在此过程中，将出现以下操作：</span><span class="sxs-lookup"><span data-stu-id="f1aad-106">Within the process, the following actions occur:</span></span>  
  
1.  <span data-ttu-id="f1aad-107">适配器将接收通知每次**员工**更新表。</span><span class="sxs-lookup"><span data-stu-id="f1aad-107">The adapter receives a notification each time the **Employee** table is updated.</span></span> <span data-ttu-id="f1aad-108">然后，适配器将通知发送到 BizTalk 业务流程。</span><span class="sxs-lookup"><span data-stu-id="f1aad-108">The adapter then sends a notification to the BizTalk orchestration.</span></span>  
  
2.  <span data-ttu-id="f1aad-109">BizTalk 业务流程指出是否通知是一条新记录插入到**员工**表。</span><span class="sxs-lookup"><span data-stu-id="f1aad-109">The BizTalk orchestration figures out whether the notification is for a new record inserted into the **Employee** table.</span></span> <span data-ttu-id="f1aad-110">如果通知适用于任何其他操作上**员工**表，业务流程不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="f1aad-110">If the notification is for any other operation on the **Employee** table, the orchestration does not perform any operation.</span></span>  
  
3.  <span data-ttu-id="f1aad-111">如果通知为插入操作上**员工**表，通知已添加新的员工记录、 业务流程使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]读取新记录的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f1aad-111">If the notification is for an Insert operation on the **Employee** table, notifying that a new employee record was added, the orchestration uses the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to read the details of the new record.</span></span>  
  
4.  <span data-ttu-id="f1aad-112">业务流程接收响应，其中包含新添加的员工记录的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f1aad-112">The orchestration receives a response that contains the details of the new added employee record.</span></span> <span data-ttu-id="f1aad-113">业务流程地图**Employee_ID**和**代码**中插入操作的请求消息的响应上的字段**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="f1aad-113">The orchestration maps the **Employee_ID** and **Designation** fields in the response to the request message for the Insert operation on the **Purchase_Order** table.</span></span>  
  
5.  <span data-ttu-id="f1aad-114">然后，业务流程使用[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]上执行插入操作**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="f1aad-114">The orchestration then uses the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to perform an Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="f1aad-115">插入操作的响应作为电子邮件发送到购买部门。</span><span class="sxs-lookup"><span data-stu-id="f1aad-115">The response for the Insert operation is sent to the Purchases department as an e-mail.</span></span>  
  
## <a name="about-the-database-objects-used-in-this-sample"></a><span data-ttu-id="f1aad-116">有关在此示例中使用的数据库对象</span><span class="sxs-lookup"><span data-stu-id="f1aad-116">About the Database Objects Used in this Sample</span></span>  
 <span data-ttu-id="f1aad-117">本教程使用随示例提供的 SQL 脚本创建的数据库对象。</span><span class="sxs-lookup"><span data-stu-id="f1aad-117">This tutorial uses the database objects created by the SQL script shipped with the samples.</span></span> <span data-ttu-id="f1aad-118">有关脚本和示例的详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="f1aad-118">For more information about the script and the samples, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span> <span data-ttu-id="f1aad-119">将在本教程中使用的数据库对象是：</span><span class="sxs-lookup"><span data-stu-id="f1aad-119">The database objects that you will use in this tutorial are:</span></span>  
  
-   <span data-ttu-id="f1aad-120">**ADAPTER_SAMPLES**数据库。</span><span class="sxs-lookup"><span data-stu-id="f1aad-120">**ADAPTER_SAMPLES** database.</span></span>  
  
-   <span data-ttu-id="f1aad-121">**员工**和**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="f1aad-121">**Employee** and **Purchase_Order** tables.</span></span>  
  
-   <span data-ttu-id="f1aad-122">**UPDATE_EMPLOYEE**存储过程。</span><span class="sxs-lookup"><span data-stu-id="f1aad-122">**UPDATE_EMPLOYEE** stored procedure.</span></span>  
  
 <span data-ttu-id="f1aad-123">当你运行该示例提供的 SQL 脚本创建所有这些数据库对象。</span><span class="sxs-lookup"><span data-stu-id="f1aad-123">All these database objects are created when you run the SQL script provided with the sample.</span></span> <span data-ttu-id="f1aad-124">请确保在开始本教程与之前运行脚本。</span><span class="sxs-lookup"><span data-stu-id="f1aad-124">Make sure you run the script before you start with the tutorial.</span></span>  
  
## <a name="sample-based-on-this-tutorial"></a><span data-ttu-id="f1aad-125">基于本教程的示例</span><span class="sxs-lookup"><span data-stu-id="f1aad-125">Sample Based on This Tutorial</span></span>  
 <span data-ttu-id="f1aad-126">示例中， **Employee_PurchaseOrder**，后者基于本教程还提供了与[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f1aad-126">A sample, **Employee_PurchaseOrder**, which is based on this tutorial is also provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="f1aad-127">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="f1aad-127">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
 <span data-ttu-id="f1aad-128">我们建议你完成本教程完全若要了解如何创建使用该适配器，BizTalk 项目，然后查看作为引用示例。</span><span class="sxs-lookup"><span data-stu-id="f1aad-128">We recommend that you go through the tutorial completely to understand how to create BizTalk projects using the adapter, and then look at the sample as a reference.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1aad-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="f1aad-129">In This Section</span></span>  
  
-   [<span data-ttu-id="f1aad-130">第 1 课： 生成架构，并创建消息</span><span class="sxs-lookup"><span data-stu-id="f1aad-130">Lesson 1: Generate Schemas and Create Messages</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)  
  
-   [<span data-ttu-id="f1aad-131">第 2 课： 接收和筛选器通知</span><span class="sxs-lookup"><span data-stu-id="f1aad-131">Lesson 2: Receive and Filter Notifications</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-2-receive-and-filter-notifications.md)  
  
-   [<span data-ttu-id="f1aad-132">第 3 课： 执行存储的过程以选择新添加的员工</span><span class="sxs-lookup"><span data-stu-id="f1aad-132">Lesson 3: Execute a Stored Procedure to Select New Employees Added</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-3-execute-a-stored-procedure-to-select-new-employees-added.md)  
  
-   [<span data-ttu-id="f1aad-133">第 4 课： 执行插入操作上采购订单表</span><span class="sxs-lookup"><span data-stu-id="f1aad-133">Lesson 4: Perform an Insert Operation on the Purchase Order Table</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-4-perform-an-insert-operation-on-the-purchase-order-table.md)  
  
-   [<span data-ttu-id="f1aad-134">第 5 课： 部署解决方案</span><span class="sxs-lookup"><span data-stu-id="f1aad-134">Lesson 5: Deploy the Solution</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-5-deploy-the-solution.md)