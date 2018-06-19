---
title: 教程： 将 BizTalk 项目迁移到 Oracle 数据库适配器 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9a393219-bae8-4e08-acc8-76986600d0de
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0948e79b7f236bb20bbff9101195809bcc921a68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22215341"
---
# <a name="tutorial-migrate-biztalk-projects-to-the-oracle-database-adapter"></a><span data-ttu-id="78454-102">教程： 将 BizTalk 项目迁移到 Oracle 数据库适配器</span><span class="sxs-lookup"><span data-stu-id="78454-102">Tutorial: Migrate BizTalk Projects to the Oracle Database adapter</span></span>
<span data-ttu-id="78454-103">包含 Microsoft BizTalk Server 提供的 Oracle Database BizTalk ODBC 适配器不同于基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]在许多方面，包括：</span><span class="sxs-lookup"><span data-stu-id="78454-103">The BizTalk ODBC Adapter for Oracle Database that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] in many aspects, including:</span></span>  
  
-   <span data-ttu-id="78454-104">创建 BizTalk 项目的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="78454-104">The design-time experience of creating a BizTalk project.</span></span>  
  
-   <span data-ttu-id="78454-105">元数据检索体验。</span><span class="sxs-lookup"><span data-stu-id="78454-105">The metadata retrieval experience.</span></span>  
  
-   <span data-ttu-id="78454-106">架构文件名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="78454-106">Schema file name and namespace.</span></span>  
  
-   <span data-ttu-id="78454-107">数据类型映射。</span><span class="sxs-lookup"><span data-stu-id="78454-107">Data type mappings.</span></span>  
  
-   <span data-ttu-id="78454-108">可以使用该适配器执行的操作。</span><span class="sxs-lookup"><span data-stu-id="78454-108">The operations that can be performed using the adapter.</span></span>  
  
-   <span data-ttu-id="78454-109">在 BizTalk Server 管理控制台中的物理端口配置</span><span class="sxs-lookup"><span data-stu-id="78454-109">Physical port configuration in the BizTalk Server Administration console</span></span>  
  
 <span data-ttu-id="78454-110">在中的主题解释了这些差异[迁移 BizTalk 项目创建使用 Oracle 数据库的 BizTalk ODBC 适配器](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)。</span><span class="sxs-lookup"><span data-stu-id="78454-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the BizTalk ODBC Adapter for Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e).</span></span>  
  
 <span data-ttu-id="78454-111">但是，你可以使用用于 Oracle 数据库的 BizTalk ODBC 适配器已创建 BizTalk 项目进行更改，并使其适用于基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="78454-111">However, you can make changes to the BizTalk project that was created using the BizTalk ODBC Adapter for Oracle Database and make it work with the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
 <span data-ttu-id="78454-112">本教程将说明了你应使用用于 Oracle 数据库的 BizTalk ODBC 适配器创建的现有 BizTalk 项目进行的更改。</span><span class="sxs-lookup"><span data-stu-id="78454-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the BizTalk ODBC Adapter for Oracle Database.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="78454-113">在本教程中，由于篇幅所限，Oracle 数据库 BizTalk ODBC 适配器将被称为"vPrev Oracle 数据库适配器"。</span><span class="sxs-lookup"><span data-stu-id="78454-113">In this tutorial, for the sake of brevity, the BizTalk ODBC Adapter for Oracle Database  will be referred to as “vPrev Oracle Database adapter.”</span></span> <span data-ttu-id="78454-114">同样，使用 vPrev Oracle 数据库适配器的 BizTalk 项目将称为"vPrev BizTalk 项目"。</span><span class="sxs-lookup"><span data-stu-id="78454-114">Similarly, a BizTalk project that uses the vPrev Oracle Database adapter will be referred to as “vPrev BizTalk project.”</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="78454-115">使用本教程的示例</span><span class="sxs-lookup"><span data-stu-id="78454-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="78454-116">本教程基于演示如何将 vPrev BizTalk 项目迁移的示例 (Oracle_Migration)。</span><span class="sxs-lookup"><span data-stu-id="78454-116">This tutorial is based upon a sample (Oracle_Migration) that demonstrates how to migrate a vPrev BizTalk project.</span></span> <span data-ttu-id="78454-117">与 Microsoft 提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="78454-117">The sample is provided with Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="78454-118">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="78454-118">For more information, see [Adapter samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="78454-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="78454-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="78454-120">你必须有 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="78454-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="78454-121">本教程涉及 BizTalk 项目执行对 CUSTOMER 表的插入操作。</span><span class="sxs-lookup"><span data-stu-id="78454-121">This tutorial involves a BizTalk project that performs an Insert operation on a CUSTOMER table.</span></span> <span data-ttu-id="78454-122">通过运行提供的 SQL 脚本在 SCOTT 架构下创建客户表[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="78454-122">The CUSTOMER table is created under the SCOTT schema by running the SQL scripts provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span>  
  
-   <span data-ttu-id="78454-123">你必须具有要执行插入操作使用 vPrev Oracle 数据库适配器对 Oracle 数据库的请求消息。</span><span class="sxs-lookup"><span data-stu-id="78454-123">You must have a request message to perform an Insert operation on the Oracle database using the vPrev Oracle Database adapter.</span></span> <span data-ttu-id="78454-124">请求消息必须符合使用 vPrev Oracle 数据库适配器所生成的 Insert 操作的架构。</span><span class="sxs-lookup"><span data-stu-id="78454-124">The request message must conform to the schema of the Insert operation generated using the vPrev Oracle Database adapter.</span></span>  
  
-   <span data-ttu-id="78454-125">你必须已完成中的步骤[先决条件](../../adapters-and-accelerators/adapter-oracle-database/prerequisites-to-create-oracle-database-applications.md)</span><span class="sxs-lookup"><span data-stu-id="78454-125">You must have completed the steps in [Prerequisites](../../adapters-and-accelerators/adapter-oracle-database/prerequisites-to-create-oracle-database-applications.md)</span></span> 
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="78454-126">了解 BizTalk 项目创建使用以前的版本的适配器</span><span class="sxs-lookup"><span data-stu-id="78454-126">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="78454-127">VPrev BizTalk 项目创建的关键组成部分是：</span><span class="sxs-lookup"><span data-stu-id="78454-127">The key constituents of a vPrev BizTalk project created are:</span></span>  
  
-   <span data-ttu-id="78454-128">**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="78454-128">**BizTalk orchestration**.</span></span> <span data-ttu-id="78454-129">这是简单的业务流程选取端口的文件位置，发送到使用 Oracle 的 Oracle 数据库的请求消息发送接收的请求消息、 接收响应，并将其保存到另一个文件位置。</span><span class="sxs-lookup"><span data-stu-id="78454-129">This is a simple orchestration that picks request messages from a file location, sends the request message to the Oracle database using an Oracle send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="78454-130">**你想要对 Oracle 数据库执行的操作架构**。</span><span class="sxs-lookup"><span data-stu-id="78454-130">**Schema for the operation you wish to perform on the Oracle database**.</span></span> <span data-ttu-id="78454-131">本教程涉及 SCOTT 架构中执行插入操作 CUSTOMER 表中的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="78454-131">This tutorial involves a BizTalk project that performs an Insert operation on the CUSTOMER table in the SCOTT schema.</span></span> <span data-ttu-id="78454-132">通过运行提供的 SQL 脚本在 SCOTT 架构下创建客户表[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="78454-132">The CUSTOMER table is created under the SCOTT schema by running the SQL scripts provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] samples.</span></span> <span data-ttu-id="78454-133">为客户表生成的架构是 CUSTOMERService_CUSTOMER_x5d.xsd。</span><span class="sxs-lookup"><span data-stu-id="78454-133">The schema generated for the CUSTOMER table is CUSTOMERService_CUSTOMER_x5d.xsd.</span></span> <span data-ttu-id="78454-134">使用 vPrev Oracle 数据库适配器生成此架构。</span><span class="sxs-lookup"><span data-stu-id="78454-134">This schema is generated using the vPrev Oracle Database adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="78454-135">与不同的是基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，vPrev Oracle 数据库适配器不支持 Oracle 数据库表上的特定操作生成的元数据。</span><span class="sxs-lookup"><span data-stu-id="78454-135">Unlike the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], the vPrev Oracle Database adapter does not support generating metadata for specific operations on an Oracle database table.</span></span> <span data-ttu-id="78454-136">默认情况下，适配器生成架构的表支持的所有操作。</span><span class="sxs-lookup"><span data-stu-id="78454-136">By default, the adapter generates schema for all the operations supported on the table.</span></span> <span data-ttu-id="78454-137">多此类之间的差异 vPrev Oracle 数据库适配器和基于 WCF 的[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，请参阅[迁移 BizTalk 项目创建使用 Oracle 数据库的 BizTalk ODBC 适配器](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e)。</span><span class="sxs-lookup"><span data-stu-id="78454-137">For more such differences between the vPrev Oracle Database adapter and the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], see [Migrating BizTalk Projects Created Using the BizTalk ODBC Adapter for Oracle Database](http://msdn.microsoft.com/library/18f40265-c7f3-44a1-99b6-1b1dc800561e).</span></span>  
  
-   <span data-ttu-id="78454-138">**请求消息**。</span><span class="sxs-lookup"><span data-stu-id="78454-138">**Request message**.</span></span> <span data-ttu-id="78454-139">要执行对 CUSTOMER 表的插入操作的请求消息。</span><span class="sxs-lookup"><span data-stu-id="78454-139">The request message to perform an Insert operation on the CUSTOMER table.</span></span> <span data-ttu-id="78454-140">请求消息的架构符合插入操作的架构，如以前版本的 Oracle 数据库适配器显示。</span><span class="sxs-lookup"><span data-stu-id="78454-140">The schema of the request message conforms to the schema of the Insert operation as surfaced by the previous version of the Oracle Database adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="78454-141">如何迁移 BizTalk 项目创建使用以前的版本的适配器</span><span class="sxs-lookup"><span data-stu-id="78454-141">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="78454-142">本教程中迁移的目标是使你可以发送请求消息，符合架构生成的 vPrev Oracle 数据库适配器，使用只能处理符合基于 WCF 的消息的 WCF 自定义端口[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="78454-142">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by vPrev Oracle Database adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="78454-143">因此，简单地说，迁移练习涉及配置基于 WCF 的不符合的处理消息的 WCF 自定义端口[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]的架构。</span><span class="sxs-lookup"><span data-stu-id="78454-143">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="78454-144">但是，若要能够相应地配置 WCF 自定义端口，必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="78454-144">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="78454-145">生成 SCOTT 上的插入操作的元数据。使用基于 WCF 的 CUSTOMER 表[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="78454-145">Generate metadata for the Insert operation on the SCOTT.CUSTOMER table using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
-   <span data-ttu-id="78454-146">用于执行插入操作执行使用基于 WCF 的插入操作使用请求消息的 vPrev Oracle 数据库适配器将请求消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="78454-146">Map the request message for performing an Insert operation using the vPrev Oracle Database adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
-   <span data-ttu-id="78454-147">将使用基于 WCF 的接收响应消息映射[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]到 vPrev Oracle 数据库适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="78454-147">Map the response message received using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] to the response message for the vPrev Oracle Database adapter.</span></span>  
  
-   <span data-ttu-id="78454-148">创建 WCF 自定义 Oracle 发送接收 BizTalk Server 管理控制台中的端口。</span><span class="sxs-lookup"><span data-stu-id="78454-148">Create a WCF-Custom Oracle send-receive port in the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="78454-149">配置要使用的请求和响应的映射的 WCF 自定义端口。</span><span class="sxs-lookup"><span data-stu-id="78454-149">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="78454-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78454-150">See Also</span></span>  
[<span data-ttu-id="78454-151">Biztalk Server 入门</span><span class="sxs-lookup"><span data-stu-id="78454-151">Getting started with Biztalk Server</span></span>](../../core/getting-started-with-biztalk-server.md)