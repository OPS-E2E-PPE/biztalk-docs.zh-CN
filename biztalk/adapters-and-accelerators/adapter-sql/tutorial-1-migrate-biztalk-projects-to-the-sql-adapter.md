---
title: 教程 1： 迁移到 SQL 适配器的 BizTalk 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b4d2dbb-e37c-4d70-831f-3bdac3c28c97
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ea64d98404d247a47e8cad8df421c81752fe63e0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013302"
---
# <a name="tutorial-1-migrate-biztalk-projects-to-the-sql-adapter"></a><span data-ttu-id="e2202-102">教程 1： 将 BizTalk 项目迁移到 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="e2202-102">Tutorial 1: Migrate BizTalk Projects to the SQL adapter</span></span>
<span data-ttu-id="e2202-103">以前版本的 SQL 适配器随 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]不同于基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]在许多方面，包括：</span><span class="sxs-lookup"><span data-stu-id="e2202-103">The previous version of the SQL adapter that shipped with Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] differs from the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="e2202-104">创建 BizTalk 项目的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="e2202-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="e2202-105">元数据检索体验。</span><span class="sxs-lookup"><span data-stu-id="e2202-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="e2202-106">架构文件的名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="e2202-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="e2202-107">数据类型映射。</span><span class="sxs-lookup"><span data-stu-id="e2202-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="e2202-108">可以使用适配器执行的操作。</span><span class="sxs-lookup"><span data-stu-id="e2202-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="e2202-109">在 BizTalk Server 管理控制台中的物理端口配置</span><span class="sxs-lookup"><span data-stu-id="e2202-109">Physical port configuration in the BizTalk Server Administration console</span></span>  
  
  <span data-ttu-id="e2202-110">迁移 BizTalk 项目创建使用 SQLadapter 前一个版本中的主题介绍了这些差异。</span><span class="sxs-lookup"><span data-stu-id="e2202-110">These differences are explained in the topics within Migrating BizTalk Projects Created Using the Previous Version of the SQLadapter.</span></span>  
  
  <span data-ttu-id="e2202-111">但是，可以使用以前版本的适配器创建的 BizTalk 项目进行更改并使其适用于基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e2202-111">However, you can make changes to the BizTalk project that was created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
  <span data-ttu-id="e2202-112">本教程说明了您应该对使用以前版本的适配器创建的现有 BizTalk 项目的更改。</span><span class="sxs-lookup"><span data-stu-id="e2202-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e2202-113">本教程中，为了简洁起见，在以前版本的 SQL 适配器称为 vPrev SQL 适配器。</span><span class="sxs-lookup"><span data-stu-id="e2202-113">In this tutorial, for the sake of brevity, the previous version of the SQL adapter will be referred to as vPrev SQL adapter.</span></span> <span data-ttu-id="e2202-114">同样，使用 vPrev SQL 适配器的 BizTalk 项目将引用为 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="e2202-114">Similarly, a BizTalk project that uses the vPrev SQL adapter will be referred to as vPrev BizTalk project.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="e2202-115">本教程提供有关如何执行基本的 insert 操作上的 SQL Server 数据库表的 vPrev SQL 适配器 BizTalk 项目迁移指南。</span><span class="sxs-lookup"><span data-stu-id="e2202-115">This tutorial provides guidance on how to migrate a vPrev SQL adapter BizTalk project that performs a basic insert operation on a SQL Server database table.</span></span> <span data-ttu-id="e2202-116">本教程不涵盖所有可能的方案从 vPrev SQL 适配器迁移到新的基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e2202-116">This tutorial does not cover all possible scenarios for migration from the vPrev SQL adapter to the new WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="e2202-117">必须使用此迁移教程的基础，并相应修改，以进行与你现有的项目相关的更改。</span><span class="sxs-lookup"><span data-stu-id="e2202-117">You must use this migration tutorial as a foundation and modify accordingly to make changes that are relevant to your existing project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="e2202-118">本教程使用示例</span><span class="sxs-lookup"><span data-stu-id="e2202-118">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="e2202-119">基于本教程演示如何迁移 vPrev BizTalk 项目的示例 (SQL_Migration)。</span><span class="sxs-lookup"><span data-stu-id="e2202-119">This tutorial is based upon a sample (SQL_Migration) that demonstrates how to migrate a vPrev BizTalk project.</span></span> <span data-ttu-id="e2202-120">与 Microsoft 提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e2202-120">The sample is provided with Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="e2202-121">有关详细信息，请参阅示例。</span><span class="sxs-lookup"><span data-stu-id="e2202-121">For more information, see Samples.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e2202-122">必要條件</span><span class="sxs-lookup"><span data-stu-id="e2202-122">Prerequisites</span></span>  
  
-   <span data-ttu-id="e2202-123">必须有一个 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="e2202-123">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="e2202-124">本教程涉及 SQL Server 数据库中执行插入操作客户表上的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="e2202-124">This tutorial involves a BizTalk project that performs an Insert operation on a Customer table in the SQL Server database.</span></span> <span data-ttu-id="e2202-125">Customer 表具有以下设计：</span><span class="sxs-lookup"><span data-stu-id="e2202-125">The Customer table has the following design:</span></span>  
  
    |<span data-ttu-id="e2202-126">列名</span><span class="sxs-lookup"><span data-stu-id="e2202-126">Column Name</span></span>|<span data-ttu-id="e2202-127">Description</span><span class="sxs-lookup"><span data-stu-id="e2202-127">Description</span></span>|  
    |-----------------|-----------------|  
    |<span data-ttu-id="e2202-128">v_custid</span><span class="sxs-lookup"><span data-stu-id="e2202-128">v_custid</span></span>|<span data-ttu-id="e2202-129">主键，整数类型，标识字段</span><span class="sxs-lookup"><span data-stu-id="e2202-129">Primary key, integer type, identity field</span></span>|  
    |<span data-ttu-id="e2202-130">“属性”</span><span class="sxs-lookup"><span data-stu-id="e2202-130">Name</span></span>|<span data-ttu-id="e2202-131">nchar(10) 类型</span><span class="sxs-lookup"><span data-stu-id="e2202-131">nchar(10) type</span></span>|  
  
-   <span data-ttu-id="e2202-132">您必须具有要执行插入操作使用 vPrev SQL 适配器在 SQL Server 数据库上的请求消息。</span><span class="sxs-lookup"><span data-stu-id="e2202-132">You must have a request message to perform an Insert operation on the SQL Server database using the vPrev SQL adapter.</span></span> <span data-ttu-id="e2202-133">请求消息必须符合使用 vPrev SQL 适配器生成的插入操作的架构。</span><span class="sxs-lookup"><span data-stu-id="e2202-133">The request message must conform to the schema of the Insert operation generated using the vPrev SQL adapter.</span></span>  
  
-   <span data-ttu-id="e2202-134">您应当已完成中的步骤[之前在开发 BizTalk 应用程序](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6)。</span><span class="sxs-lookup"><span data-stu-id="e2202-134">You should have completed the steps in [Before You Develop BizTalk Applications](http://msdn.microsoft.com/library/3539741d-5266-43d4-9b7b-73e82f0ed4f6).</span></span>  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="e2202-135">了解 BizTalk 项目创建使用以前版本的适配器</span><span class="sxs-lookup"><span data-stu-id="e2202-135">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="e2202-136">创建的 vPrev BizTalk 项目的关键组成部分包括：</span><span class="sxs-lookup"><span data-stu-id="e2202-136">The key constituents of a vPrev BizTalk project created are:</span></span>  
  
-   <span data-ttu-id="e2202-137">**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="e2202-137">**BizTalk orchestration**.</span></span> <span data-ttu-id="e2202-138">这是一个简单的业务流程提取请求消息从一个文件位置，将发送到使用 WCF 自定义 SQL Server 数据库的请求消息发送接收端口、 接收响应，并将其保存到另一个文件位置。</span><span class="sxs-lookup"><span data-stu-id="e2202-138">This is a simple orchestration that picks request messages from a file location, sends the request message to the SQL Server database using a WCF-Custom send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="e2202-139">**您想要在 SQL Server 数据库上执行的操作架构**。</span><span class="sxs-lookup"><span data-stu-id="e2202-139">**Schema for the operation you wish to perform on the SQL Server database**.</span></span> <span data-ttu-id="e2202-140">本教程涉及到执行插入操作的客户表上的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="e2202-140">This tutorial involves a BizTalk project that performs an Insert operation on the Customer table.</span></span> <span data-ttu-id="e2202-141">生成的 Customer 表的架构是 InsertCustomerService.xsd。</span><span class="sxs-lookup"><span data-stu-id="e2202-141">The schema generated for the Customer table is InsertCustomerService.xsd.</span></span> <span data-ttu-id="e2202-142">此架构是使用 vPrev SQL 适配器生成的。</span><span class="sxs-lookup"><span data-stu-id="e2202-142">This schema is generated using the vPrev SQL adapter.</span></span>  
  
-   <span data-ttu-id="e2202-143">**请求消息**。</span><span class="sxs-lookup"><span data-stu-id="e2202-143">**Request message**.</span></span> <span data-ttu-id="e2202-144">要执行客户表上的插入操作的请求消息。</span><span class="sxs-lookup"><span data-stu-id="e2202-144">The request message to perform an Insert operation on the Customer table.</span></span> <span data-ttu-id="e2202-145">显示以前版本的 SQL 适配器插入操作的架构符合请求消息的架构。</span><span class="sxs-lookup"><span data-stu-id="e2202-145">The schema of the request message conforms to the schema of the Insert operation as surfaced by the previous version of the SQL adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="e2202-146">使用以前版本的适配器如何迁移 BizTalk 项目创建</span><span class="sxs-lookup"><span data-stu-id="e2202-146">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="e2202-147">此迁移教程的目的是使您能够将请求消息，符合架构生成 vPrev SQL 适配器，使用可以只处理符合基于 WCF 的消息的 WCF 自定义端口的发送[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e2202-147">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by vPrev SQL adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="e2202-148">因此，简单地说，迁移活动包括： 配置 WCF 自定义端口来处理消息的不符合基于 WCF 的[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]的架构。</span><span class="sxs-lookup"><span data-stu-id="e2202-148">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="e2202-149">但是，若要能够适当地配置 WCF 自定义端口，必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="e2202-149">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
- <span data-ttu-id="e2202-150">生成上使用基于 WCF 的 Customer 表的插入操作的元数据[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e2202-150">Generate metadata for the Insert operation on the Customer table using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
- <span data-ttu-id="e2202-151">执行插入操作执行 Insert 操作使用基于 WCF 的使用 vPrev SQL 适配器添加到请求消息的请求消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e2202-151">Map the request message for performing an Insert operation using the vPrev SQL adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
- <span data-ttu-id="e2202-152">使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]到 vPrev SQL 适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="e2202-152">Map the response message received using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] to the response message for the vPrev SQL adapter.</span></span>  
  
- <span data-ttu-id="e2202-153">创建 WCF 自定义 SQL 发送接收端口中的[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e2202-153">Create a WCF-Custom SQL send-receive port in the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
- <span data-ttu-id="e2202-154">配置要使用的请求和响应的映射的 WCF 自定义端口。</span><span class="sxs-lookup"><span data-stu-id="e2202-154">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e2202-155">本节内容</span><span class="sxs-lookup"><span data-stu-id="e2202-155">In This Section</span></span>  
  
-   [<span data-ttu-id="e2202-156">步骤 1： 修改 vPrev BizTalk 项目使用 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="e2202-156">Step 1: Modify the vPrev BizTalk Project using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-1-modify-the-vprev-biztalk-project-using-the-sql-adapter.md)  
  
-   [<span data-ttu-id="e2202-157">步骤 2： 使用 SQL 适配器的 BizTalk Server 管理控制台中配置业务流程</span><span class="sxs-lookup"><span data-stu-id="e2202-157">Step 2: Configure the Orchestration in BizTalk Server Administration Console using the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-2-configure-the-orchestration-to-use-the-sql-adapter-in-biztalk-server.md)  
  
-   [<span data-ttu-id="e2202-158">步骤 3： 测试迁移应用程序使用 SQL 适配器</span><span class="sxs-lookup"><span data-stu-id="e2202-158">Step 3: Test the Migrated Application that uses the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/step-3-test-the-migrated-application-that-uses-the-sql-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2202-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2202-159">See Also</span></span>  
 [<span data-ttu-id="e2202-160">SQL 适配器教程</span><span class="sxs-lookup"><span data-stu-id="e2202-160">SQL Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sql/sql-adapter-tutorials.md)