---
title: "教程 1： 将 BizTalk 项目迁移到 SQL 适配器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0b4d2dbb-e37c-4d70-831f-3bdac3c28c97
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5ca17095841fb154be9ec34766a34f174414cd82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="tutorial-1-migrate-biztalk-projects-to-the-sql-adapter"></a><span data-ttu-id="b007e-102">教程 1： 将 BizTalk 项目迁移到 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="b007e-102">Tutorial 1: Migrate BizTalk Projects to the SQL adapter</span></span>
<span data-ttu-id="b007e-103">以前版本的 SQL 适配器随 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]不同于基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在许多方面，包括：</span><span class="sxs-lookup"><span data-stu-id="b007e-103">The previous version of the SQL adapter that shipped with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] differs from the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in many aspects, including:</span></span>  
  
-   <span data-ttu-id="b007e-104">创建 BizTalk 项目的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="b007e-104">The design-time experience of creating a BizTalk project.</span></span>  
  
-   <span data-ttu-id="b007e-105">元数据检索体验。</span><span class="sxs-lookup"><span data-stu-id="b007e-105">The metadata retrieval experience.</span></span>  
  
-   <span data-ttu-id="b007e-106">架构文件名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="b007e-106">Schema file name and namespace.</span></span>  
  
-   <span data-ttu-id="b007e-107">数据类型映射。</span><span class="sxs-lookup"><span data-stu-id="b007e-107">Data type mappings.</span></span>  
  
-   <span data-ttu-id="b007e-108">可以使用该适配器执行的操作。</span><span class="sxs-lookup"><span data-stu-id="b007e-108">The operations that can be performed using the adapter.</span></span>  
  
-   <span data-ttu-id="b007e-109">在 BizTalk Server 管理控制台中的物理端口配置</span><span class="sxs-lookup"><span data-stu-id="b007e-109">Physical port configuration in the BizTalk Server Administration console</span></span>  
  
 <span data-ttu-id="b007e-110">在迁移 BizTalk 项目创建使用 SQLadapter 的上一个版本中的主题解释了这些差异。</span><span class="sxs-lookup"><span data-stu-id="b007e-110">These differences are explained in the topics within Migrating BizTalk Projects Created Using the Previous Version of the SQLadapter.</span></span>  
  
 <span data-ttu-id="b007e-111">但是，你可以使用以前版本的适配器已创建 BizTalk 项目进行更改，并使其适用于基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b007e-111">However, you can make changes to the BizTalk project that was created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
 <span data-ttu-id="b007e-112">本教程将说明了你应创建使用以前的版本的适配器的现有 BizTalk 项目的更改。</span><span class="sxs-lookup"><span data-stu-id="b007e-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b007e-113">在本教程中，由于篇幅所限，以前版本的 SQL 适配器称为 vPrev SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="b007e-113">In this tutorial, for the sake of brevity, the previous version of the SQL adapter will be referred to as vPrev SQL adapter.</span></span> <span data-ttu-id="b007e-114">同样，使用 vPrev SQL 适配器的 BizTalk 项目将被称为 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="b007e-114">Similarly, a BizTalk project that uses the vPrev SQL adapter will be referred to as vPrev BizTalk project.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b007e-115">本教程提供有关如何将执行的 SQL Server 数据库表上的基本插入操作 vPrev SQL 适配器 BizTalk 项目迁移指南。</span><span class="sxs-lookup"><span data-stu-id="b007e-115">This tutorial provides guidance on how to migrate a vPrev SQL adapter BizTalk project that performs a basic insert operation on a SQL Server database table.</span></span> <span data-ttu-id="b007e-116">本教程不涉及从 vPrev SQL 适配器迁移到新的所有可能的方案基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b007e-116">This tutorial does not cover all possible scenarios for migration from the vPrev SQL adapter to the new WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="b007e-117">必须使用此迁移教程为基础，并相应地修改以使与你的现有项目相关的更改。</span><span class="sxs-lookup"><span data-stu-id="b007e-117">You must use this migration tutorial as a foundation and modify accordingly to make changes that are relevant to your existing project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="b007e-118">使用本教程的示例</span><span class="sxs-lookup"><span data-stu-id="b007e-118">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="b007e-119">本教程基于演示如何将 vPrev BizTalk 项目迁移的示例 (SQL_Migration)。</span><span class="sxs-lookup"><span data-stu-id="b007e-119">This tutorial is based upon a sample (SQL_Migration) that demonstrates how to migrate a vPrev BizTalk project.</span></span> <span data-ttu-id="b007e-120">与 Microsoft 提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b007e-120">The sample is provided with Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="b007e-121">有关详细信息，请参阅示例。</span><span class="sxs-lookup"><span data-stu-id="b007e-121">For more information, see Samples.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b007e-122">先决条件</span><span class="sxs-lookup"><span data-stu-id="b007e-122">Prerequisites</span></span>  
  
-   <span data-ttu-id="b007e-123">你必须有 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="b007e-123">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="b007e-124">本教程涉及 SQL Server 数据库中执行插入操作客户表上的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="b007e-124">This tutorial involves a BizTalk project that performs an Insert operation on a Customer table in the SQL Server database.</span></span> <span data-ttu-id="b007e-125">Customer 表具有以下设计：</span><span class="sxs-lookup"><span data-stu-id="b007e-125">The Customer table has the following design:</span></span>  
  
    |<span data-ttu-id="b007e-126">列名</span><span class="sxs-lookup"><span data-stu-id="b007e-126">Column Name</span></span>|<span data-ttu-id="b007e-127">Description</span><span class="sxs-lookup"><span data-stu-id="b007e-127">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="b007e-128">v_custid</span><span class="sxs-lookup"><span data-stu-id="b007e-128">v_custid</span></span>|<span data-ttu-id="b007e-129">主键，整数类型，标识字段</span><span class="sxs-lookup"><span data-stu-id="b007e-129">Primary key, integer type, identity field</span></span>|  
    |<span data-ttu-id="b007e-130">Name</span><span class="sxs-lookup"><span data-stu-id="b007e-130">Name</span></span>|<span data-ttu-id="b007e-131">nchar(10) 类型</span><span class="sxs-lookup"><span data-stu-id="b007e-131">nchar(10) type</span></span>|  
  
-   <span data-ttu-id="b007e-132">你必须具有要执行插入操作使用 vPrev SQL 适配器的 SQL Server 数据库的请求消息。</span><span class="sxs-lookup"><span data-stu-id="b007e-132">You must have a request message to perform an Insert operation on the SQL Server database using the vPrev SQL adapter.</span></span> <span data-ttu-id="b007e-133">请求消息必须符合使用 vPrev SQL 适配器所生成的 Insert 操作的架构。</span><span class="sxs-lookup"><span data-stu-id="b007e-133">The request message must conform to the schema of the Insert operation generated using the vPrev SQL adapter.</span></span>  
  
-   <span data-ttu-id="b007e-134">你应完成中的步骤[之前你开发 BizTalk 应用程序](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)。</span><span class="sxs-lookup"><span data-stu-id="b007e-134">You should have completed the steps in [Before You Develop BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6).</span></span>  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="b007e-135">了解 BizTalk 项目创建使用以前的版本的适配器</span><span class="sxs-lookup"><span data-stu-id="b007e-135">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="b007e-136">VPrev BizTalk 项目创建的关键组成部分是：</span><span class="sxs-lookup"><span data-stu-id="b007e-136">The key constituents of a vPrev BizTalk project created are:</span></span>  
  
-   <span data-ttu-id="b007e-137">**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="b007e-137">**BizTalk orchestration**.</span></span> <span data-ttu-id="b007e-138">这是简单的业务流程选取端口的文件位置，发送到使用 WCF 自定义 SQL Server 数据库的请求消息发送接收的请求消息、 接收响应，并将其保存到另一个文件位置。</span><span class="sxs-lookup"><span data-stu-id="b007e-138">This is a simple orchestration that picks request messages from a file location, sends the request message to the SQL Server database using a WCF-Custom send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="b007e-139">**你想要在 SQL Server 数据库上执行的操作的架构**。</span><span class="sxs-lookup"><span data-stu-id="b007e-139">**Schema for the operation you wish to perform on the SQL Server database**.</span></span> <span data-ttu-id="b007e-140">本教程涉及执行插入操作 Customer 表中的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="b007e-140">This tutorial involves a BizTalk project that performs an Insert operation on the Customer table.</span></span> <span data-ttu-id="b007e-141">为客户表生成的架构是 InsertCustomerService.xsd。</span><span class="sxs-lookup"><span data-stu-id="b007e-141">The schema generated for the Customer table is InsertCustomerService.xsd.</span></span> <span data-ttu-id="b007e-142">使用 vPrev SQL 适配器生成此架构。</span><span class="sxs-lookup"><span data-stu-id="b007e-142">This schema is generated using the vPrev SQL adapter.</span></span>  
  
-   <span data-ttu-id="b007e-143">**请求消息**。</span><span class="sxs-lookup"><span data-stu-id="b007e-143">**Request message**.</span></span> <span data-ttu-id="b007e-144">要执行对 Customer 表的插入操作的请求消息。</span><span class="sxs-lookup"><span data-stu-id="b007e-144">The request message to perform an Insert operation on the Customer table.</span></span> <span data-ttu-id="b007e-145">请求消息的架构符合插入操作的架构，如显示以前版本的 SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="b007e-145">The schema of the request message conforms to the schema of the Insert operation as surfaced by the previous version of the SQL adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="b007e-146">如何迁移 BizTalk 项目创建使用以前的版本的适配器</span><span class="sxs-lookup"><span data-stu-id="b007e-146">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="b007e-147">本教程中迁移的目标是使你可以发送请求消息，符合架构生成的 vPrev SQL 适配器，使用只能处理符合基于 WCF 的消息的 WCF 自定义端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b007e-147">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by vPrev SQL adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="b007e-148">因此，简单地说，迁移练习涉及配置基于 WCF 的不符合的处理消息的 WCF 自定义端口[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]的架构。</span><span class="sxs-lookup"><span data-stu-id="b007e-148">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="b007e-149">但是，若要能够相应地配置 WCF 自定义端口，必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="b007e-149">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="b007e-150">生成上使用基于 WCF 的 Customer 表的插入操作的元数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b007e-150">Generate metadata for the Insert operation on the Customer table using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="b007e-151">用于执行插入操作执行使用基于 WCF 的插入操作使用请求消息的 vPrev SQL 适配器将请求消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b007e-151">Map the request message for performing an Insert operation using the vPrev SQL adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
-   <span data-ttu-id="b007e-152">将使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到 vPrev SQL 适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="b007e-152">Map the response message received using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to the response message for the vPrev SQL adapter.</span></span>  
  
-   <span data-ttu-id="b007e-153">创建 WCF 自定义 SQL 发送接收中的端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b007e-153">Create a WCF-Custom SQL send-receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
-   <span data-ttu-id="b007e-154">配置要使用的请求和响应的映射的 WCF 自定义端口。</span><span class="sxs-lookup"><span data-stu-id="b007e-154">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b007e-155">本节内容</span><span class="sxs-lookup"><span data-stu-id="b007e-155">In This Section</span></span>  
  
-   [<span data-ttu-id="b007e-156">步骤 1： 修改 vPrev BizTalk 项目使用的 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="b007e-156">Step 1: Modify the vPrev BizTalk Project using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="b007e-157">步骤 2： 在 BizTalk Server 管理控制台中使用的 SQL 适配器配置业务流程</span><span class="sxs-lookup"><span data-stu-id="b007e-157">Step 2: Configure the Orchestration in BizTalk Server Administration Console using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)  
  
-   [<span data-ttu-id="b007e-158">步骤 3： 测试迁移使用的应用程序的 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="b007e-158">Step 3: Test the Migrated Application that uses the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="b007e-159">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b007e-159">See Also</span></span>  
 [<span data-ttu-id="b007e-160">SQL 适配器教程</span><span class="sxs-lookup"><span data-stu-id="b007e-160">SQL Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)