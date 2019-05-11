---
title: 教程 2:Siebel 中的迁移 BizTalk 项目 |Microsoft Docs
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
ms.openlocfilehash: 477a23c571333fb609987bf0060c92c6e6348ea9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65370380"
---
# <a name="tutorial-2-migrating-biztalk-projects-in-siebel"></a><span data-ttu-id="8264a-102">教程 2:在 Siebel 的 BizTalk 项目迁移</span><span class="sxs-lookup"><span data-stu-id="8264a-102">Tutorial 2: Migrating BizTalk Projects in Siebel</span></span>
<span data-ttu-id="8264a-103">Siebel 适配器随 Microsoft BizTalk Server 的以前版本不同于基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]在许多方面，包括：</span><span class="sxs-lookup"><span data-stu-id="8264a-103">The previous version of the Siebel adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="8264a-104">创建 BizTalk 项目的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="8264a-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="8264a-105">元数据检索体验。</span><span class="sxs-lookup"><span data-stu-id="8264a-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="8264a-106">架构文件的名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="8264a-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="8264a-107">数据类型映射。</span><span class="sxs-lookup"><span data-stu-id="8264a-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="8264a-108">可以使用适配器执行的操作。</span><span class="sxs-lookup"><span data-stu-id="8264a-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="8264a-109">在 BizTalk Server 管理控制台中的物理端口配置</span><span class="sxs-lookup"><span data-stu-id="8264a-109">Physical port configuration in the BizTalk Server Administration console</span></span>  
  
  <span data-ttu-id="8264a-110">在中的主题解释了这些差异[迁移 BizTalk 项目创建使用 Siebel 适配器的上一步版本](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)。</span><span class="sxs-lookup"><span data-stu-id="8264a-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the Siebel Adapter](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).</span></span>  
  
  <span data-ttu-id="8264a-111">但是，可以创建使用以前版本的适配器的 BizTalk 项目进行更改并使其适用于基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8264a-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
  <span data-ttu-id="8264a-112">本教程说明了您应该对使用以前版本的适配器创建的现有 BizTalk 项目的更改。</span><span class="sxs-lookup"><span data-stu-id="8264a-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8264a-113">本教程中，为了简洁起见，在以前版本的 Siebel 适配器称为 vPrev Siebel 适配器。</span><span class="sxs-lookup"><span data-stu-id="8264a-113">In this tutorial, for the sake of brevity, the previous version of the Siebel adapter will be referred to as vPrev Siebel adapter.</span></span> <span data-ttu-id="8264a-114">同样，使用 vPrev Siebel 适配器的 BizTalk 项目将引用为 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="8264a-114">Similarly, a BizTalk project that uses the vPrev Siebel adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="8264a-115">本教程使用示例</span><span class="sxs-lookup"><span data-stu-id="8264a-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="8264a-116">基于本教程演示如何迁移执行插入操作帐户 Siebel 业务组件上的 vPrev BizTalk 项目的示例 (Siebel_BussComp_Migration)。</span><span class="sxs-lookup"><span data-stu-id="8264a-116">This tutorial is based upon a sample (Siebel_BussComp_Migration) that demonstrates how to migrate a vPrev BizTalk project that performs an Insert operation on the Account Siebel business component.</span></span> <span data-ttu-id="8264a-117">与 Microsoft 提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8264a-117">The sample is provided with Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="8264a-118">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="8264a-118">For more information, see [Adapter Sample](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8264a-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="8264a-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="8264a-120">必须有一个 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="8264a-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="8264a-121">本教程涉及到执行插入操作帐户业务组件上的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="8264a-121">This tutorial involves a BizTalk project that performs an Insert operation on the Account business component.</span></span>  
  
-   <span data-ttu-id="8264a-122">您必须具有要执行插入操作帐户业务组件使用 vPrev Siebel 适配器上的请求消息。</span><span class="sxs-lookup"><span data-stu-id="8264a-122">You must have a request message to perform an Insert operation on the Account business component using the vPrev Siebel adapter.</span></span> <span data-ttu-id="8264a-123">请求消息必须符合使用 vPrev Siebel 适配器生成的插入操作的架构。</span><span class="sxs-lookup"><span data-stu-id="8264a-123">The request message must conform to the schema of the Insert operation generated using the vPrev Siebel adapter.</span></span>  
  
-   <span data-ttu-id="8264a-124">你必须完成中的步骤[创建 Siebel 应用程序的先决条件](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="8264a-124">You must have completed the steps in [Prerequisites to create Siebel applications](../../adapters-and-accelerators/adapter-siebel/prerequisites-to-create-siebel-applications.md).</span></span>  
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="8264a-125">了解 BizTalk 项目创建使用以前版本的适配器</span><span class="sxs-lookup"><span data-stu-id="8264a-125">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="8264a-126">创建的 vPrev BizTalk 项目的关键组成部分包括：</span><span class="sxs-lookup"><span data-stu-id="8264a-126">The key constituents of a vPrev BizTalk project created are:</span></span>  
  
- <span data-ttu-id="8264a-127">**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="8264a-127">**BizTalk orchestration**.</span></span> <span data-ttu-id="8264a-128">这是一个简单的业务流程提取请求消息从一个文件位置，将发送到使用 Siebel 的 Siebel 系统的请求消息发送接收端口、 接收响应，并将其保存到另一个文件位置。</span><span class="sxs-lookup"><span data-stu-id="8264a-128">This is a simple orchestration that picks request messages from a file location, sends the request message to the Siebel system using a Siebel send-receive port, receives the response, and saves it to another file location.</span></span>  
  
- <span data-ttu-id="8264a-129">**你想要在 Siebel 业务组件上执行的操作架构**。</span><span class="sxs-lookup"><span data-stu-id="8264a-129">**Schema for the operation you wish to perform on the Siebel business component**.</span></span> <span data-ttu-id="8264a-130">本教程涉及到执行插入操作帐户业务组件上的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="8264a-130">This tutorial involves a BizTalk project that performs an Insert operation on the Account business component.</span></span> <span data-ttu-id="8264a-131">为帐户业务组件生成的架构是 AccountService_Account_x5d.xsd。</span><span class="sxs-lookup"><span data-stu-id="8264a-131">The schema generated for the Account business component is AccountService_Account_x5d.xsd.</span></span> <span data-ttu-id="8264a-132">此架构是使用 vPrev Siebel 适配器生成的。</span><span class="sxs-lookup"><span data-stu-id="8264a-132">This schema is generated using the vPrev Siebel adapter.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="8264a-133">与基于 WCF 的不同[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，vPrev Siebel 适配器不支持在业务组件上的特定操作生成的元数据。</span><span class="sxs-lookup"><span data-stu-id="8264a-133">Unlike the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], the vPrev Siebel adapter does not support generating metadata for specific operations on a business component.</span></span> <span data-ttu-id="8264a-134">默认情况下，适配器生成的在业务组件上受支持的所有操作的架构。</span><span class="sxs-lookup"><span data-stu-id="8264a-134">By default, the adapter generates schema for all the operations supported on the business component.</span></span> <span data-ttu-id="8264a-135">有关 vPrev Siebel 适配器和基于 WCF 的更多此类差异[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，请参阅[迁移 BizTalk 项目创建使用 Siebel 适配器的上一步版本](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e)。</span><span class="sxs-lookup"><span data-stu-id="8264a-135">For more such differences between the vPrev Siebel adapter and the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], see [Migrating BizTalk Projects Created Using the Previous Version of the Siebel Adapter](http://msdn.microsoft.com/library/ae61d3df-c5ca-4891-86b1-9f0dd6d3a59e).</span></span>  
  
- <span data-ttu-id="8264a-136">**请求消息**。</span><span class="sxs-lookup"><span data-stu-id="8264a-136">**Request message**.</span></span> <span data-ttu-id="8264a-137">要执行插入操作帐户业务组件上的请求消息。</span><span class="sxs-lookup"><span data-stu-id="8264a-137">The request message to perform an Insert operation on the Account business component.</span></span> <span data-ttu-id="8264a-138">请求消息的架构符合插入操作的架构，如 vPrev Siebel 适配器提供的。</span><span class="sxs-lookup"><span data-stu-id="8264a-138">The schema of the request message conforms to the schema of the Insert operation as surfaced by the vPrev Siebel adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="8264a-139">使用以前版本的适配器如何迁移 BizTalk 项目创建</span><span class="sxs-lookup"><span data-stu-id="8264a-139">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="8264a-140">此迁移教程的目的是使您能够将请求消息，符合架构生成 vPrev Siebel 适配器，使用可以只处理符合基于 WCF 的消息的 WCF 自定义端口的发送[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8264a-140">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by the vPrev Siebel adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="8264a-141">因此，简单地说，迁移活动包括： 配置 WCF 自定义端口来处理消息的不符合基于 WCF 的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]的架构。</span><span class="sxs-lookup"><span data-stu-id="8264a-141">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="8264a-142">但是，若要能够适当地配置 WCF 自定义端口，必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="8264a-142">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
- <span data-ttu-id="8264a-143">为使用基于 WCF 的帐户业务组件上的插入操作生成元数据[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8264a-143">Generate metadata for the Insert operation on the Account business component using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
- <span data-ttu-id="8264a-144">执行插入操作执行 Insert 操作使用基于 WCF 的使用 vPrev Siebel 适配器添加到请求消息的请求消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="8264a-144">Map the request message for performing an Insert operation using the vPrev Siebel adapter to a request message for performing an Insert operation using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
- <span data-ttu-id="8264a-145">使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]到 vPrev Siebel 适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="8264a-145">Map the response message received using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] to the response message for the vPrev Siebel adapter.</span></span>  
  
- <span data-ttu-id="8264a-146">创建自定义 WCF 的 Siebel 发送接收端口在 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="8264a-146">Create a WCF-Custom Siebel send-receive port in the BizTalk Server Administration console.</span></span>  
  
- <span data-ttu-id="8264a-147">配置要使用的请求和响应的映射的 WCF 自定义端口。</span><span class="sxs-lookup"><span data-stu-id="8264a-147">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8264a-148">本节内容</span><span class="sxs-lookup"><span data-stu-id="8264a-148">In This Section</span></span>  
  
-   [<span data-ttu-id="8264a-149">步骤 1：修改 vPrev BizTalk 项目中 Oracle 数据库</span><span class="sxs-lookup"><span data-stu-id="8264a-149">Step 1: Modify the vPrev BizTalk Project in Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/step-1-modify-the-vprev-biztalk-project-in-oracle-database.md)  
  
-   [<span data-ttu-id="8264a-150">步骤 2：若要使用 ORacle 数据库适配器的 BizTalk Server 管理控制台中配置业务流程</span><span class="sxs-lookup"><span data-stu-id="8264a-150">Step 2: Configure the Orchestration in BizTalk Server Administration Console to use the ORacle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/step-2-configure-an-orchestration-to-use-the-oracle-db-adapter-in-biztalk.md)  
  
-   [<span data-ttu-id="8264a-151">步骤 3：测试迁移应用程序使用 Siebel 适配器</span><span class="sxs-lookup"><span data-stu-id="8264a-151">Step 3: Test the Migrated Application with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/step-3-test-the-migrated-application-with-the-siebel-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="8264a-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="8264a-152">See Also</span></span>  
 [<span data-ttu-id="8264a-153">Siebel 适配器教程</span><span class="sxs-lookup"><span data-stu-id="8264a-153">Siebel Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-siebel/siebel-adapter-tutorials.md)