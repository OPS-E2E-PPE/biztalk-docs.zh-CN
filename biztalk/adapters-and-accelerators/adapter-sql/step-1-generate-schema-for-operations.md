---
title: 步骤 1： 为操作生成架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63218a5e-9af2-40af-9992-ac5e204d2832
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6eb6de636ba2ee587fa1da3720c38ef517f0ba01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997854"
---
# <a name="step-1-generate-schema-for-operations"></a><span data-ttu-id="8c48a-102">步骤 1： 为操作生成架构</span><span class="sxs-lookup"><span data-stu-id="8c48a-102">Step 1: Generate Schema for Operations</span></span>
<span data-ttu-id="8c48a-103">![2 的第 1 步](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span><span class="sxs-lookup"><span data-stu-id="8c48a-103">![Step 1 of 2](../../adapters-and-accelerators/adapter-sql/media/step-1of2.gif "Step_1of2")</span></span>  
  
 <span data-ttu-id="8c48a-104">**完成时间：** 5 分钟</span><span class="sxs-lookup"><span data-stu-id="8c48a-104">**Time to complete:** 5 minutes</span></span>  
  
 <span data-ttu-id="8c48a-105">**目标：** 在此步骤中，生成使用 SQL Server 数据库执行操作的架构[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8c48a-105">**Objective:** In this step, you generate schemas for the operations that you perform on the SQL Server database using the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="8c48a-106">对于本教程中，必须生成以下架构：</span><span class="sxs-lookup"><span data-stu-id="8c48a-106">For this tutorial, you must generate schema for the following:</span></span>  
  
-   <span data-ttu-id="8c48a-107">**通知**（入站操作）。</span><span class="sxs-lookup"><span data-stu-id="8c48a-107">**Notification** (inbound operation).</span></span>  
  
-   <span data-ttu-id="8c48a-108">**UPDATE_EMPLOYEE**存储过程 （出站操作）。</span><span class="sxs-lookup"><span data-stu-id="8c48a-108">**UPDATE_EMPLOYEE** stored procedure (outbound operation).</span></span>  
  
-   <span data-ttu-id="8c48a-109">**插入**上的操作**Purchase_Order**表 （出站操作）。</span><span class="sxs-lookup"><span data-stu-id="8c48a-109">**Insert** operation on the **Purchase_Order** table (outbound operation).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8c48a-110">必要條件</span><span class="sxs-lookup"><span data-stu-id="8c48a-110">Prerequisites</span></span>  
 <span data-ttu-id="8c48a-111">您继续阅读本教程之前，请确保：</span><span class="sxs-lookup"><span data-stu-id="8c48a-111">Before you proceed with the tutorial, make sure:</span></span>  
  
-   <span data-ttu-id="8c48a-112">你必须完成中的步骤[之前在开发 BizTalk 应用程序](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)。</span><span class="sxs-lookup"><span data-stu-id="8c48a-112">You must have completed the steps in [Before You Develop BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6).</span></span>  
  
-   <span data-ttu-id="8c48a-113">必须以 BizTalk Server Administrators 组的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="8c48a-113">You must log on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-generate-schema-for-operations"></a><span data-ttu-id="8c48a-114">若要为操作生成架构</span><span class="sxs-lookup"><span data-stu-id="8c48a-114">To generate schema for operations</span></span>  
  
1. <span data-ttu-id="8c48a-115">创建新的 BizTalk 项目中[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8c48a-115">Create a new BizTalk project in [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)].</span></span> <span data-ttu-id="8c48a-116">对于本教程，将项目命名为`Employee_PurchaseOrder`。</span><span class="sxs-lookup"><span data-stu-id="8c48a-116">For this tutorial, name the project as `Employee_PurchaseOrder`.</span></span>  
  
2. <span data-ttu-id="8c48a-117">ADAPTER_SAMPLES SQL Server 数据库使用连接到[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8c48a-117">Connect to the ADAPTER_SAMPLES SQL Server database using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span> <span data-ttu-id="8c48a-118">有关如何使用连接的说明[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，请参阅[连接到 Visual Studio 使用使用适配器服务外接程序中的 SQL Server](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="8c48a-118">For instructions on how to connect using [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], see [Connect to SQL Server in Visual Studio Using Consume Adapter Service Add-in](../../adapters-and-accelerators/adapter-sql/connect-to-sql-server-in-visual-studio-using-the-consume-adapter-service-add-in.md).</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="8c48a-119">此外可以连接到 SQL Server 使用[!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8c48a-119">You can also connect to SQL Server using the [!INCLUDE[addadapterwiz](../../includes/addadapterwiz-md.md)].</span></span> <span data-ttu-id="8c48a-120">但是，对于本教程将使用[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8c48a-120">However, for this tutorial you will use the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
3. <span data-ttu-id="8c48a-121">生成架构**通知**的入站操作。</span><span class="sxs-lookup"><span data-stu-id="8c48a-121">Generate schema for the **Notification** inbound operation.</span></span>  
  
   1. <span data-ttu-id="8c48a-122">连接到 ADAPTER_SAMPLES 数据库中，在以后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]，从**选择协定类型**列表中，选择**服务 （入站操作）**。</span><span class="sxs-lookup"><span data-stu-id="8c48a-122">After connecting to the ADAPTER_SAMPLES database, in the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], from the **Select contract type** list, select **Service (Inbound operations)**.</span></span>  
  
   2. <span data-ttu-id="8c48a-123">从**选择一个类别**框中，单击根节点 (**/**)。</span><span class="sxs-lookup"><span data-stu-id="8c48a-123">From the **Select a category** box, click the root node (**/**).</span></span>  
  
   3. <span data-ttu-id="8c48a-124">从**可用类别和操作**框中，选择**通知**然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="8c48a-124">From the **Available categories and operations** box, select **Notification** and click **Add**.</span></span> <span data-ttu-id="8c48a-125">**通知**操作现在显示在**添加的类别和操作**框。</span><span class="sxs-lookup"><span data-stu-id="8c48a-125">The **Notification** operation is now displayed in the **Added categories and operations** box.</span></span> <span data-ttu-id="8c48a-126">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="8c48a-126">Click **OK**.</span></span>  
  
4. <span data-ttu-id="8c48a-127">生成架构**UPDATE_EMPLOYEE**存储过程和插入操作上**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="8c48a-127">Generate schema for the **UPDATE_EMPLOYEE** stored procedure and the Insert operation on **Purchase_Order** table.</span></span>  
  
   1. <span data-ttu-id="8c48a-128">重复步骤 2 以连接到 SQL Server 使用 ADAPTER_SAMPLES 数据库[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8c48a-128">Repeat step 2 to connect to ADAPTER_SAMPLES database in SQL Server using the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
      > [!NOTE]
      >  <span data-ttu-id="8c48a-129">不能在同一时间生成的入站和出站操作的架构。</span><span class="sxs-lookup"><span data-stu-id="8c48a-129">You cannot generate schema for inbound and outbound operations at the same time.</span></span> <span data-ttu-id="8c48a-130">因此，第 3 步中，单击后**确定**若要生成的架构**通知**操作，[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]关闭。</span><span class="sxs-lookup"><span data-stu-id="8c48a-130">Hence, in step 3, after you click **OK** to generate the schema for **Notification** operation, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] closes.</span></span> <span data-ttu-id="8c48a-131">您必须重新连接到 SQL Server 数据库来为出站操作生成架构。</span><span class="sxs-lookup"><span data-stu-id="8c48a-131">You must reconnect to the SQL Server database to generate schema for outbound operations.</span></span>  
  
   2. <span data-ttu-id="8c48a-132">从**选择协定类型**列表中，选择**客户端 （出站操作）**。</span><span class="sxs-lookup"><span data-stu-id="8c48a-132">From the **Select contract type** list, select **Client (Outbound operations)**.</span></span>  
  
   3. <span data-ttu-id="8c48a-133">从**选择一个类别**框中，单击**Strongly-Typed 过程**节点。</span><span class="sxs-lookup"><span data-stu-id="8c48a-133">From the **Select a category** box, click the **Strongly-Typed Procedures** node.</span></span> <span data-ttu-id="8c48a-134">从**可用类别和操作**s 框中，选择**UPDATE_EMPLOYEE**，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="8c48a-134">From the **Available categories and operation**s box, select **UPDATE_EMPLOYEE**, and then click **Add**.</span></span>  
  
      > [!IMPORTANT]
      >  <span data-ttu-id="8c48a-135">**UPDATE_EMPLOYEE**存储的过程中也有下**过程**节点。</span><span class="sxs-lookup"><span data-stu-id="8c48a-135">The **UPDATE_EMPLOYEE** stored procedure is also available under the **Procedures** node.</span></span> <span data-ttu-id="8c48a-136">但是，如果生成从下的存储过程的架构**过程**节点，响应消息架构在设计时不可用，但收到了响应消息后执行存储的过程。</span><span class="sxs-lookup"><span data-stu-id="8c48a-136">However, if you generate schema for the stored procedure from under the **Procedures** node, the response message schema is not available at design-time but is received with the response message after you execute the stored procedure.</span></span>  
      >   
      >  <span data-ttu-id="8c48a-137">在本教程中，您将映射到插入操作的输入架构的存储过程的响应架构上**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="8c48a-137">In this tutorial, you will map the response schema of the stored procedure to the input schema of the Insert operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="8c48a-138">因此，您将需要的架构**UPDATE_EMPLOYEE**在设计时和你的存储的过程必须选择从下的存储的过程**Strongly-Typed 过程**。</span><span class="sxs-lookup"><span data-stu-id="8c48a-138">Therefore, you will need the schema for the **UPDATE_EMPLOYEE** stored procedure at design-time and you must select the stored procedure from under the **Strongly-Typed Procedures**.</span></span> <span data-ttu-id="8c48a-139">通过此操作，将在设计时获取的存储过程的架构。</span><span class="sxs-lookup"><span data-stu-id="8c48a-139">By doing so, you will get the schema of the stored procedure at design-time.</span></span>  
  
   4. <span data-ttu-id="8c48a-140">从**选择一个类别**框中，展开**表**节点，然后单击的节点**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="8c48a-140">From the **Select a category** box, expand the **Tables** node, and click the node for **Purchase_Order** table.</span></span> <span data-ttu-id="8c48a-141">从**可用类别和操作**s 框中，选择**插入**，单击**添加**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="8c48a-141">From the **Available categories and operation**s box, select **Insert**, click **Add**, and then click **OK**.</span></span>  
  
## <a name="what-did-i-just-do"></a><span data-ttu-id="8c48a-142">内容回顾</span><span class="sxs-lookup"><span data-stu-id="8c48a-142">What did I just do?</span></span>  
 <span data-ttu-id="8c48a-143">在此步骤中，生成的架构**通知**（入站操作）， **UPDATE_EMPLOYEE**存储过程，并**插入**操作**Purchase_Order**表。</span><span class="sxs-lookup"><span data-stu-id="8c48a-143">In this step, you generated schemas for **Notification** (inbound operation), **UPDATE_EMPLOYEE** stored procedure, and **Insert** operation on the **Purchase_Order** table.</span></span> <span data-ttu-id="8c48a-144">生成架构后[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]向 BizTalk 项目中添加以下文件：</span><span class="sxs-lookup"><span data-stu-id="8c48a-144">After you generate the schema, the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] adds the following files to your BizTalk project:</span></span>  
  
- <span data-ttu-id="8c48a-145">包含要调用 SQL Server 上的操作的请求消息的架构的 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="8c48a-145">XSD files that contain schema for the request message to invoke operations on SQL Server.</span></span>  
  
- <span data-ttu-id="8c48a-146">可用于创建 WCF 自定义发送和接收端口中的 XML 绑定文件[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="8c48a-146">XML binding files that you can use to create WCF-Custom send and receive ports in [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
  <span data-ttu-id="8c48a-147">有关生成架构的详细信息，请参阅[浏览、 搜索和获取元数据的 SQL 操作使用 SQL 适配器](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="8c48a-147">For more information about generating schemas, see [Browse, search, and get metadata for SQL operations using the SQL adapter](../../adapters-and-accelerators/adapter-sql/browse-search-and-get-metadata-for-sql-operations-using-the-sql-adapter.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="8c48a-148">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8c48a-148">Next Steps</span></span>  
 <span data-ttu-id="8c48a-149">中的架构在 BizTalk 项目中创建的消息[步骤 2： 创建 BizTalk 业务流程的消息](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="8c48a-149">You create messages in the BizTalk project for the schemas in [Step 2: Create Messages for BizTalk Orchestrations](../../adapters-and-accelerators/adapter-sql/step-2-create-messages-for-biztalk-orchestrations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c48a-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c48a-150">See Also</span></span>  
 [<span data-ttu-id="8c48a-151">第 1 课：生成架构并创建消息</span><span class="sxs-lookup"><span data-stu-id="8c48a-151">Lesson 1: Generate Schemas and Create Messages</span></span>](../../adapters-and-accelerators/adapter-sql/lesson-1-generate-schemas-and-create-messages.md)