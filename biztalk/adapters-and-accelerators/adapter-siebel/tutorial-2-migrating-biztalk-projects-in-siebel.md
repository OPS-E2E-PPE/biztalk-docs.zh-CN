---
title: 教程 2： 迁移 BizTalk 项目中 Siebel |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a2a1828-8cc8-4b80-99bd-c083c04e5d04
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b8d138d348e750102d82a4aba2e39bc7d119c8c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223005"
---
# <a name="tutorial-2-migrating-biztalk-projects-in-siebel"></a><span data-ttu-id="2218a-102">教程 2： 迁移中 Siebel 的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="2218a-102">Tutorial 2: Migrating BizTalk Projects in Siebel</span></span>
<span data-ttu-id="2218a-103">Microsoft BizTalk 服务器随附的 Siebel 适配器以前版本的基于 WCF 的不同[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在许多方面，包括：</span><span class="sxs-lookup"><span data-stu-id="2218a-103">The previous version of the Siebel adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in many aspects, including:</span></span>  
  
-   <span data-ttu-id="2218a-104">创建 BizTalk 项目的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="2218a-104">The design-time experience of creating a BizTalk project.</span></span>  
  
-   <span data-ttu-id="2218a-105">元数据检索体验。</span><span class="sxs-lookup"><span data-stu-id="2218a-105">The metadata retrieval experience.</span></span>  
  
-   <span data-ttu-id="2218a-106">架构文件名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="2218a-106">Schema file name and namespace.</span></span>  
  
-   <span data-ttu-id="2218a-107">数据类型映射。</span><span class="sxs-lookup"><span data-stu-id="2218a-107">Data type mappings.</span></span>  
  
-   <span data-ttu-id="2218a-108">可以使用该适配器执行的操作。</span><span class="sxs-lookup"><span data-stu-id="2218a-108">The operations that can be performed using the adapter.</span></span>  
  
-   <span data-ttu-id="2218a-109">在 BizTalk Server 管理控制台中的物理端口配置</span><span class="sxs-lookup"><span data-stu-id="2218a-109">Physical port configuration in the BizTalk Server Administration console</span></span>  
  
 <span data-ttu-id="2218a-110">在中的主题解释了这些差异[迁移 BizTalk 项目创建使用 Siebel 适配器的上一步版本](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)。</span><span class="sxs-lookup"><span data-stu-id="2218a-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the Siebel Adapter](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).</span></span>  
  
 <span data-ttu-id="2218a-111">但是，你可以使用以前版本的适配器创建 BizTalk 项目进行更改，并使其适用于基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2218a-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
 <span data-ttu-id="2218a-112">本教程将说明了你应创建使用以前的版本的适配器的现有 BizTalk 项目的更改。</span><span class="sxs-lookup"><span data-stu-id="2218a-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2218a-113">在本教程中，由于篇幅所限，以前版本的 Siebel 适配器称为 vPrev Siebel 适配器。</span><span class="sxs-lookup"><span data-stu-id="2218a-113">In this tutorial, for the sake of brevity, the previous version of the Siebel adapter will be referred to as vPrev Siebel adapter.</span></span> <span data-ttu-id="2218a-114">同样，使用 vPrev Siebel 适配器的 BizTalk 项目将被称为 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="2218a-114">Similarly, a BizTalk project that uses the vPrev Siebel adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="2218a-115">使用本教程的示例</span><span class="sxs-lookup"><span data-stu-id="2218a-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="2218a-116">本教程基于演示如何将执行插入操作帐户 Siebel 业务组件上的 vPrev BizTalk 项目迁移的示例 (Siebel_BussComp_Migration)。</span><span class="sxs-lookup"><span data-stu-id="2218a-116">This tutorial is based upon a sample (Siebel_BussComp_Migration) that demonstrates how to migrate a vPrev BizTalk project that performs an Insert operation on the Account Siebel business component.</span></span> <span data-ttu-id="2218a-117">与 Microsoft 提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2218a-117">The sample is provided with Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="2218a-118">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="2218a-118">For more information, see [Adapter Sample](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2218a-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="2218a-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="2218a-120">你必须有 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="2218a-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="2218a-121">本教程涉及执行插入操作帐户在业务组件上的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="2218a-121">This tutorial involves a BizTalk project that performs an Insert operation on the Account business component.</span></span>  
  
-   <span data-ttu-id="2218a-122">你必须具有要执行插入操作帐户在业务组件使用 vPrev Siebel 适配器上的请求消息。</span><span class="sxs-lookup"><span data-stu-id="2218a-122">You must have a request message to perform an Insert operation on the Account business component using the vPrev Siebel adapter.</span></span> <span data-ttu-id="2218a-123">请求消息必须符合使用 vPrev Siebel 适配器所生成的 Insert 操作的架构。</span><span class="sxs-lookup"><span data-stu-id="2218a-123">The request message must conform to the schema of the Insert operation generated using the vPrev Siebel adapter.</span></span>  
  
-   <span data-ttu-id="2218a-124">你必须已完成中的步骤[创建 Siebel 应用程序的先决条件](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="2218a-124">You must have completed the steps in [Prerequisites to create Siebel applications](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md).</span></span>  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="2218a-125">了解 BizTalk 项目创建使用以前的版本的适配器</span><span class="sxs-lookup"><span data-stu-id="2218a-125">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="2218a-126">VPrev BizTalk 项目创建的关键组成部分是：</span><span class="sxs-lookup"><span data-stu-id="2218a-126">The key constituents of a vPrev BizTalk project created are:</span></span>  
  
-   <span data-ttu-id="2218a-127">**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="2218a-127">**BizTalk orchestration**.</span></span> <span data-ttu-id="2218a-128">这是简单的业务流程选取端口的文件位置，发送到 Siebel 系统使用 Siebel 请求消息发送接收的请求消息、 接收响应，并将其保存到另一个文件位置。</span><span class="sxs-lookup"><span data-stu-id="2218a-128">This is a simple orchestration that picks request messages from a file location, sends the request message to the Siebel system using a Siebel send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="2218a-129">**你想要在 Siebel 在业务组件上执行的操作的架构**。</span><span class="sxs-lookup"><span data-stu-id="2218a-129">**Schema for the operation you wish to perform on the Siebel business component**.</span></span> <span data-ttu-id="2218a-130">本教程涉及执行插入操作帐户在业务组件上的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="2218a-130">This tutorial involves a BizTalk project that performs an Insert operation on the Account business component.</span></span> <span data-ttu-id="2218a-131">为帐户在业务组件生成的架构是 AccountService_Account_x5d.xsd。</span><span class="sxs-lookup"><span data-stu-id="2218a-131">The schema generated for the Account business component is AccountService_Account_x5d.xsd.</span></span> <span data-ttu-id="2218a-132">使用 vPrev Siebel 适配器生成此架构。</span><span class="sxs-lookup"><span data-stu-id="2218a-132">This schema is generated using the vPrev Siebel adapter.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="2218a-133">与不同的是基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，vPrev Siebel 适配器不支持在业务组件上的特定操作生成的元数据。</span><span class="sxs-lookup"><span data-stu-id="2218a-133">Unlike the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], the vPrev Siebel adapter does not support generating metadata for specific operations on a business component.</span></span> <span data-ttu-id="2218a-134">默认情况下，适配器生成的业务组件支持的所有操作的架构。</span><span class="sxs-lookup"><span data-stu-id="2218a-134">By default, the adapter generates schema for all the operations supported on the business component.</span></span> <span data-ttu-id="2218a-135">多此类之间的差异 vPrev Siebel 适配器和基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[迁移 BizTalk 项目创建使用 Siebel 适配器的上一步版本](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)。</span><span class="sxs-lookup"><span data-stu-id="2218a-135">For more such differences between the vPrev Siebel adapter and the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Migrating BizTalk Projects Created Using the Previous Version of the Siebel Adapter](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).</span></span>  
  
-   <span data-ttu-id="2218a-136">**请求消息**。</span><span class="sxs-lookup"><span data-stu-id="2218a-136">**Request message**.</span></span> <span data-ttu-id="2218a-137">要执行插入操作帐户在业务组件上的请求消息。</span><span class="sxs-lookup"><span data-stu-id="2218a-137">The request message to perform an Insert operation on the Account business component.</span></span> <span data-ttu-id="2218a-138">请求消息的架构符合插入操作的架构，如显示 vPrev Siebel 适配器。</span><span class="sxs-lookup"><span data-stu-id="2218a-138">The schema of the request message conforms to the schema of the Insert operation as surfaced by the vPrev Siebel adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="2218a-139">如何迁移 BizTalk 项目创建使用以前的版本的适配器</span><span class="sxs-lookup"><span data-stu-id="2218a-139">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="2218a-140">本教程中迁移的目标是使您能够发送请求消息符合架构生成的使用只能处理符合基于 WCF 的消息的 WCF 自定义端口和 vPrev Siebel 适配器[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2218a-140">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by the vPrev Siebel adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="2218a-141">因此，简单地说，迁移练习涉及配置基于 WCF 的不符合的处理消息的 WCF 自定义端口[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]的架构。</span><span class="sxs-lookup"><span data-stu-id="2218a-141">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="2218a-142">但是，若要能够相应地配置 WCF 自定义端口，必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="2218a-142">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
-   <span data-ttu-id="2218a-143">生成使用基于 WCF 的帐户在业务组件上的插入操作的元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2218a-143">Generate metadata for the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
-   <span data-ttu-id="2218a-144">用于执行插入操作执行使用基于 WCF 的插入操作使用请求消息的 vPrev Siebel 适配器将请求消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2218a-144">Map the request message for performing an Insert operation using the vPrev Siebel adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
-   <span data-ttu-id="2218a-145">将使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到 vPrev Siebel 适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="2218a-145">Map the response message received using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to the response message for the vPrev Siebel adapter.</span></span>  
  
-   <span data-ttu-id="2218a-146">创建 WCF 自定义 Siebel 发送接收 BizTalk Server 管理控制台中的端口。</span><span class="sxs-lookup"><span data-stu-id="2218a-146">Create a WCF-Custom Siebel send-receive port in the BizTalk Server Administration console.</span></span>  
  
-   <span data-ttu-id="2218a-147">配置要使用的请求和响应的映射的 WCF 自定义端口。</span><span class="sxs-lookup"><span data-stu-id="2218a-147">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2218a-148">本节内容</span><span class="sxs-lookup"><span data-stu-id="2218a-148">In This Section</span></span>  
  
-   [<span data-ttu-id="2218a-149">步骤 1： 修改 vPrev Oracle 数据库中的 BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="2218a-149">Step 1: Modify the vPrev BizTalk Project in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/step-1-modify-the-vprev-biztalk-project-in-oracle-database.md)  
  
-   [<span data-ttu-id="2218a-150">步骤 2： 在 BizTalk Server 管理控制台，以使用 ORacle 数据库适配器中配置业务流程</span><span class="sxs-lookup"><span data-stu-id="2218a-150">Step 2: Configure the Orchestration in BizTalk Server Administration Console to use the ORacle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)  
  
-   [<span data-ttu-id="2218a-151">步骤 3： 测试与 Siebel 适配器迁移应用程序</span><span class="sxs-lookup"><span data-stu-id="2218a-151">Step 3: Test the Migrated Application with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="2218a-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2218a-152">See Also</span></span>  
 [<span data-ttu-id="2218a-153">Siebel 适配器教程</span><span class="sxs-lookup"><span data-stu-id="2218a-153">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)