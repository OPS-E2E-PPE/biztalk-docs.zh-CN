---
title: 教程 2:迁移 SAP RFC BizTalk 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, BizTalk project from previous version of the SAP adapter
- migration
- migrating, SAP RFC BizTalk project
ms.assetid: b4943613-23d2-4869-b033-ec07daabfac5
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 76eee4656808c56664f23cd216afeef5f564f9b0
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372319"
---
# <a name="tutorial-2-migrating-an-sap-rfc-biztalk-project"></a><span data-ttu-id="b304e-102">教程 2:迁移 SAP RFC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="b304e-102">Tutorial 2: Migrating an SAP RFC BizTalk Project</span></span>
<span data-ttu-id="b304e-103">SAP 适配器随 Microsoft BizTalk Server 的以前版本不同于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在许多方面，包括：</span><span class="sxs-lookup"><span data-stu-id="b304e-103">The previous version of the SAP adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="b304e-104">创建 BizTalk 项目的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="b304e-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="b304e-105">元数据检索体验。</span><span class="sxs-lookup"><span data-stu-id="b304e-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="b304e-106">架构文件的名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="b304e-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="b304e-107">数据类型映射。</span><span class="sxs-lookup"><span data-stu-id="b304e-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="b304e-108">可以使用适配器执行的操作。</span><span class="sxs-lookup"><span data-stu-id="b304e-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="b304e-109">在 BizTalk Server 管理控制台中的物理端口配置。</span><span class="sxs-lookup"><span data-stu-id="b304e-109">Physical port configuration in the BizTalk Server Administration console.</span></span>  
  
  <span data-ttu-id="b304e-110">在中的主题解释了这些差异[迁移 BizTalk 项目创建使用 SAP 适配器的上一步版本](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)。</span><span class="sxs-lookup"><span data-stu-id="b304e-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the SAP Adapter](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span></span>  
  
  <span data-ttu-id="b304e-111">但是，可以创建使用以前版本的适配器的 BizTalk 项目进行更改并使其适用于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b304e-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
  <span data-ttu-id="b304e-112">本教程说明了您应该对使用以前版本的适配器创建的现有 BizTalk 项目的更改。</span><span class="sxs-lookup"><span data-stu-id="b304e-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b304e-113">本教程中，为了简洁起见，在以前版本的 SAP 适配器称为 vPrev SAP 适配器。</span><span class="sxs-lookup"><span data-stu-id="b304e-113">In this tutorial, for the sake of brevity, the previous version of the SAP adapter will be referred to as vPrev SAP adapter.</span></span> <span data-ttu-id="b304e-114">同样，使用 vPrev SAP 适配器的 BizTalk 项目将引用为 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="b304e-114">Similarly, a BizTalk project that uses the vPrev SAP adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="b304e-115">本教程使用示例</span><span class="sxs-lookup"><span data-stu-id="b304e-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="b304e-116">基于本教程演示如何将 SAP 系统中调用 RFC vPrev BizTalk 项目迁移的示例 (SAP_RFC_Migration)。</span><span class="sxs-lookup"><span data-stu-id="b304e-116">This tutorial is based upon a sample (SAP_RFC_Migration) that demonstrates how to migrate a vPrev BizTalk project that invokes an RFC in an SAP system.</span></span> <span data-ttu-id="b304e-117">使用提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b304e-117">The sample is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="b304e-118">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="b304e-118">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b304e-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="b304e-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="b304e-120">必须有一个 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="b304e-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="b304e-121">本教程涉及调用 SD_RFC_CUSTOMER_GET RFC BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="b304e-121">This tutorial involves a BizTalk project that invokes the SD_RFC_CUSTOMER_GET RFC.</span></span>  
  
-   <span data-ttu-id="b304e-122">您必须具有执行，以调用 SD_RFC_CUSTOMER_GET RFC 使用 vPrev SAP 适配器的请求消息。</span><span class="sxs-lookup"><span data-stu-id="b304e-122">You must have a request message to perform to invoke the SD_RFC_CUSTOMER_GET RFC using the vPrev SAP adapter.</span></span> <span data-ttu-id="b304e-123">请求消息必须符合 RFC 使用 vPrev SAP 适配器生成的架构。</span><span class="sxs-lookup"><span data-stu-id="b304e-123">The request message must conform to the schema of the RFC generated using the vPrev SAP adapter.</span></span> <span data-ttu-id="b304e-124">对于本教程提供的示例包含此请求消息。</span><span class="sxs-lookup"><span data-stu-id="b304e-124">The sample provided for this tutorial contains this request message.</span></span>  
  
-   [<span data-ttu-id="b304e-125">创建强名称密钥文件并了解相关工具</span><span class="sxs-lookup"><span data-stu-id="b304e-125">Create strong-name key file, and learn the tools</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="b304e-126">了解 BizTalk 项目创建使用以前版本的适配器</span><span class="sxs-lookup"><span data-stu-id="b304e-126">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="b304e-127">是的关键组成部分 vPrev BizTalk 项目以调用 RFC:</span><span class="sxs-lookup"><span data-stu-id="b304e-127">The key constituents of a vPrev BizTalk project to invoke an RFC are:</span></span>  
  
-   <span data-ttu-id="b304e-128">**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="b304e-128">**BizTalk orchestration**.</span></span> <span data-ttu-id="b304e-129">这是一个简单的业务流程提取请求消息从一个文件位置，将发送到使用 SAP 的 SAP 系统的请求消息发送接收端口、 接收响应，并将其保存到另一个文件位置。</span><span class="sxs-lookup"><span data-stu-id="b304e-129">This is a simple orchestration that picks request messages from a file location, sends the request message to the SAP system using an SAP send-receive port, receives the response, and saves it to another file location.</span></span>  
  
-   <span data-ttu-id="b304e-130">**你想要在 SAP 系统中调用 rfc 架构**。</span><span class="sxs-lookup"><span data-stu-id="b304e-130">**Schema for the RFC you want to invoke in the SAP system**.</span></span> <span data-ttu-id="b304e-131">本教程涉及调用 SD_RFC_CUSTOMER_GET RFC BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="b304e-131">This tutorial involves a BizTalk project that invokes the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="b304e-132">为 RFC 生成的架构是 SD_RFC_CUSTOMER_GET__x32003.xsd。</span><span class="sxs-lookup"><span data-stu-id="b304e-132">The schema generated for the RFC is SD_RFC_CUSTOMER_GET__x32003.xsd.</span></span> <span data-ttu-id="b304e-133">此架构是使用 vPrev SAP 适配器生成的。</span><span class="sxs-lookup"><span data-stu-id="b304e-133">This schema is generated using the vPrev SAP adapter.</span></span>  
  
-   <span data-ttu-id="b304e-134">**请求消息**。</span><span class="sxs-lookup"><span data-stu-id="b304e-134">**Request message**.</span></span> <span data-ttu-id="b304e-135">要调用 SD_RFC_CUSTOMER_GET RFC 的请求消息。</span><span class="sxs-lookup"><span data-stu-id="b304e-135">The request message to invoke the SD_RFC_CUSTOMER_GET RFC.</span></span> <span data-ttu-id="b304e-136">请求消息的架构符合 SD_RFC_CUSTOMER_GET RFC 的架构，如 vPrev SAP 适配器提供的。</span><span class="sxs-lookup"><span data-stu-id="b304e-136">The schema of the request message conforms to the schema of the SD_RFC_CUSTOMER_GET RFC as surfaced by the vPrev SAP adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="b304e-137">使用以前版本的适配器如何迁移 BizTalk 项目创建</span><span class="sxs-lookup"><span data-stu-id="b304e-137">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="b304e-138">此迁移教程的目的是使您能够将请求消息，符合架构生成 vPrev SAP 适配器，使用可以只处理符合基于 WCF 的消息的 WCF 自定义端口的发送[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b304e-138">The goal of this migration tutorial is to enable you to send a request message, which conforms to schema generated by the vPrev SAP adapter, using a WCF-Custom port that can only process messages conforming to the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="b304e-139">因此，简单地说，迁移活动包括： 配置 WCF 自定义端口来处理消息的不符合基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]的架构。</span><span class="sxs-lookup"><span data-stu-id="b304e-139">So, in short, the migration exercise involves configuring the WCF-Custom port to process messages that do not conform to the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]'s schema.</span></span>  
  
 <span data-ttu-id="b304e-140">但是，若要能够适当地配置 WCF 自定义端口，必须执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="b304e-140">However, to be able to configure the WCF-Custom port appropriately, you must perform the following tasks:</span></span>  
  
- <span data-ttu-id="b304e-141">为使用基于 WCF 的 SD_RFC_CUSTOMER_GET RFC 生成元数据[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b304e-141">Generate metadata for the SD_RFC_CUSTOMER_GET RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="b304e-142">用于调用 RFC 调用使用基于 WCF 的在 RFC 使用 vPrev SAP 适配器添加到请求消息请求消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b304e-142">Map the request message for invoking the RFC using the vPrev SAP adapter to a request message for invoking the RFC using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
- <span data-ttu-id="b304e-143">使用基于 WCF 的接收响应消息映射[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]到 vPrev SAP 适配器的响应消息。</span><span class="sxs-lookup"><span data-stu-id="b304e-143">Map the response message received using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] to the response message for the vPrev SAP adapter.</span></span>  
  
- <span data-ttu-id="b304e-144">创建 WCF 自定义 SAP 发送接收端口在 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b304e-144">Create a WCF-Custom SAP send-receive port in the BizTalk Server Administration console.</span></span>  
  
- <span data-ttu-id="b304e-145">配置要使用的请求和响应的映射的 WCF 自定义端口。</span><span class="sxs-lookup"><span data-stu-id="b304e-145">Configure the WCF-Custom port to use the request and response mappings.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b304e-146">本节内容</span><span class="sxs-lookup"><span data-stu-id="b304e-146">In This Section</span></span>  
  
-   [<span data-ttu-id="b304e-147">步骤 1：修改 vPrev BizTalk 项目以调用 RFC</span><span class="sxs-lookup"><span data-stu-id="b304e-147">Step 1: Modify the vPrev BizTalk Project for Invoking an RFC</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-modify-the-vprev-biztalk-project-for-invoking-an-rfc.md)  
  
-   [<span data-ttu-id="b304e-148">步骤 2：在 BizTalk Server 管理控制台中配置业务流程</span><span class="sxs-lookup"><span data-stu-id="b304e-148">Step 2: Configure the Orchestration in BizTalk Server Administration Console</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-configure-the-orchestration-in-biztalk-server-administration-console1.md)  
  
-   [<span data-ttu-id="b304e-149">步骤 3：测试已迁移的应用程序</span><span class="sxs-lookup"><span data-stu-id="b304e-149">Step 3: Test the Migrated Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application6.md)  
  
## <a name="see-also"></a><span data-ttu-id="b304e-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="b304e-150">See Also</span></span>  
 [<span data-ttu-id="b304e-151">SAP 适配器教程</span><span class="sxs-lookup"><span data-stu-id="b304e-151">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)