---
title: 教程 4： 迁移 SAP 接收 IDOC BizTalk 项目 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migration, SAP Receive IDOC BizTalk project
- migrating, SAP Receive IDOC BizTalk project
- migration
ms.assetid: 74b667d8-2d8c-4c15-9dd2-f13521404b85
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 943c80e84bc192330fd870a45c0b5fb60761a33d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22217885"
---
# <a name="tutorial-4-migrating-an-sap-receive-idoc-biztalk-project"></a><span data-ttu-id="6c068-102">教程 4： 迁移 SAP 接收 IDOC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="6c068-102">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>
<span data-ttu-id="6c068-103">SAP 适配器随 Microsoft BizTalk Server 以前版本的基于 WCF 的不同[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在许多方面，包括：</span><span class="sxs-lookup"><span data-stu-id="6c068-103">The previous version of the SAP adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in many aspects, including:</span></span>  
  
-   <span data-ttu-id="6c068-104">创建 BizTalk 项目的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="6c068-104">The design-time experience of creating a BizTalk project.</span></span>  
  
-   <span data-ttu-id="6c068-105">元数据检索体验。</span><span class="sxs-lookup"><span data-stu-id="6c068-105">The metadata retrieval experience.</span></span>  
  
-   <span data-ttu-id="6c068-106">架构文件名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="6c068-106">Schema file name and namespace.</span></span>  
  
-   <span data-ttu-id="6c068-107">数据类型映射。</span><span class="sxs-lookup"><span data-stu-id="6c068-107">Data type mappings.</span></span>  
  
-   <span data-ttu-id="6c068-108">可以使用该适配器执行的操作。</span><span class="sxs-lookup"><span data-stu-id="6c068-108">The operations that can be performed using the adapter.</span></span>  
  
-   <span data-ttu-id="6c068-109">在 BizTalk Server 管理控制台中的物理端口配置。</span><span class="sxs-lookup"><span data-stu-id="6c068-109">Physical port configuration in the BizTalk Server Administration console.</span></span>  
  
 <span data-ttu-id="6c068-110">在中的主题解释了这些差异[迁移 BizTalk 项目创建使用上一步版本的 SAP 适配器](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)。</span><span class="sxs-lookup"><span data-stu-id="6c068-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the SAP Adapter](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span></span>  
  
 <span data-ttu-id="6c068-111">但是，你可以使用以前版本的适配器创建 BizTalk 项目进行更改，并使其适用于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6c068-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
 <span data-ttu-id="6c068-112">本教程将说明了你应创建使用以前的版本的适配器的现有 BizTalk 项目的更改。</span><span class="sxs-lookup"><span data-stu-id="6c068-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6c068-113">在本教程中，由于篇幅所限，以前版本的 SAP 适配器称为 vPrev SAP 适配器。</span><span class="sxs-lookup"><span data-stu-id="6c068-113">In this tutorial, for the sake of brevity, the previous version of the SAP adapter will be referred to as vPrev SAP adapter.</span></span> <span data-ttu-id="6c068-114">同样，使用 vPrev SAP 适配器的 BizTalk 项目将被称为 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6c068-114">Similarly, a BizTalk project that uses the vPrev SAP adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="6c068-115">使用本教程的示例</span><span class="sxs-lookup"><span data-stu-id="6c068-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="6c068-116">本教程基于演示如何将某个 SAP 系统从接收平面文件 IDOC vPrev BizTalk 项目迁移的示例 (ReceiveIDOC_Migration)。</span><span class="sxs-lookup"><span data-stu-id="6c068-116">This tutorial is based upon a sample (ReceiveIDOC_Migration) that demonstrates how to migrate a vPrev BizTalk project that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="6c068-117">使用提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6c068-117">The sample is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="6c068-118">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="6c068-118">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6c068-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="6c068-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="6c068-120">你必须有 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6c068-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="6c068-121">本教程涉及从某个 SAP 系统接收 ORDERS03 IDOC BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6c068-121">This tutorial involves a BizTalk project that receives an ORDERS03 IDOC from an SAP system.</span></span>  
  
-   [<span data-ttu-id="6c068-122">创建强名称密钥文件，并了解工具</span><span class="sxs-lookup"><span data-stu-id="6c068-122">Create strong-name key file, and learn the tools</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)

  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="6c068-123">了解 BizTalk 项目创建使用以前的版本的适配器</span><span class="sxs-lookup"><span data-stu-id="6c068-123">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="6c068-124">若要接收 IDOC vPrev BizTalk 项目的关键组成部分是：</span><span class="sxs-lookup"><span data-stu-id="6c068-124">The key constituents of a vPrev BizTalk project to receive an IDOC are:</span></span>  
  
-   <span data-ttu-id="6c068-125">**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="6c068-125">**BizTalk orchestration**.</span></span> <span data-ttu-id="6c068-126">这是一个简单包含一个 SAP 的业务流程接收平面文件 IDOC 收到某个 SAP 系统的端口。</span><span class="sxs-lookup"><span data-stu-id="6c068-126">This is a simple orchestration that consists of an SAP receive port that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="6c068-127">BizTalk 项目包含平面文件反汇编程序中，将平面文件 IDOC 转换为 XML，以便可在业务流程。</span><span class="sxs-lookup"><span data-stu-id="6c068-127">The BizTalk project contains a flat-file disassembler to convert the flat-file IDOC to an XML, so that it can be used in an orchestration.</span></span> <span data-ttu-id="6c068-128">XML IDOC 复制到文件位置通过文件端口之前，会将它转换为回使用平面文件汇编平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="6c068-128">Before the XML IDOC is copied to a file location through a file port, it is converted back into a flat-file IDOC using a flat-file assembler.</span></span>  
  
-   <span data-ttu-id="6c068-129">**你想要将发送到 SAP 系统 IDOC 架构**。</span><span class="sxs-lookup"><span data-stu-id="6c068-129">**Schema for the IDOC you want to send to the SAP system**.</span></span> <span data-ttu-id="6c068-130">本教程涉及从 SAP 系统接收 ORDERS03 IDOC BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6c068-130">This tutorial involves a BizTalk project that receives ORDERS03 IDOC from the SAP system.</span></span> <span data-ttu-id="6c068-131">为 IDOC 生成的架构是 ORDERS03.xsd。</span><span class="sxs-lookup"><span data-stu-id="6c068-131">The schema generated for the IDOC is ORDERS03.xsd.</span></span> <span data-ttu-id="6c068-132">使用 vPrev SAP 适配器生成此架构。</span><span class="sxs-lookup"><span data-stu-id="6c068-132">This schema is generated using the vPrev SAP adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="6c068-133">如何迁移 BizTalk 项目创建使用以前的版本的适配器</span><span class="sxs-lookup"><span data-stu-id="6c068-133">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="6c068-134">本教程中迁移的目标是使您能够从 SAP 系统 WCF 自定义发送端口而不发送端口用于 vPrev SAP 适配器接收平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="6c068-134">The goal of this migration tutorial is to enable you to receive a flat-file IDOC from an SAP system using a WCF-Custom send port instead of the send port for the vPrev SAP adapter.</span></span> <span data-ttu-id="6c068-135">了解哪些设置所需的 WCF 自定义发送端口之前, 必须先了解哪些物理端口是必需的 vPrev 发送 IDOC 业务流程。</span><span class="sxs-lookup"><span data-stu-id="6c068-135">Before understanding what settings are required for the WCF-Custom send port, you must first understand what physical ports are required for the vPrev send IDOC orchestration.</span></span>  
  
-   <span data-ttu-id="6c068-136">VPrev SAP 接收平面文件 IDOC 收到某个 SAP 系统的端口。</span><span class="sxs-lookup"><span data-stu-id="6c068-136">A vPrev SAP receive port that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="6c068-137">端口也将此转换为 XML IDOC 使用平面文件反汇编程序，它位于 vPrev BizTalk 应用程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="6c068-137">The port also converts this to an XML IDOC using a flat-file disassembler, which is available as part of the vPrev BizTalk application.</span></span> <span data-ttu-id="6c068-138">XML IDOC 符合使用 vPrev SAP 适配器生成的架构 (ORDERS03.xsd)。</span><span class="sxs-lookup"><span data-stu-id="6c068-138">The XML IDOC conforms to the schema (ORDERS03.xsd) that you generated using the vPrev SAP adapter.</span></span>  
  
-   <span data-ttu-id="6c068-139">用于复制到文件夹的 IDOC 的文件发送端口。</span><span class="sxs-lookup"><span data-stu-id="6c068-139">A file send port which copies the IDOC to folder.</span></span> <span data-ttu-id="6c068-140">此端口也使用平面文件汇编器管道的 BizTalk 应用程序，可将 XML IDOC 转换为平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="6c068-140">This port also uses the flat-file assembler pipeline, available in the BizTalk application, to convert the XML IDOC to a flat-file IDOC.</span></span>  
  
 <span data-ttu-id="6c068-141">若要迁移现有 vPrev BizTalk 项目，你不必更改文件发送端口，将平面文件 IDOC 复制到一个文件夹。</span><span class="sxs-lookup"><span data-stu-id="6c068-141">To migrate your existing vPrev BizTalk project, you do not need to change the file send port that copies the flat-file IDOC to a folder.</span></span> <span data-ttu-id="6c068-142">你只需以配置一个新 WCF 自定义接收具有正确的配置设置的端口。</span><span class="sxs-lookup"><span data-stu-id="6c068-142">You only need to configure a new WCF-Custom receive port with the right configuration settings.</span></span> <span data-ttu-id="6c068-143">本教程演示如何配置 WCF 自定义接收端口从使用基于 WCF 的 SAP 系统接收到的 Idoc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6c068-143">This tutorial demonstrates how to configure the WCF-Custom receive port to receive IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c068-144">本节内容</span><span class="sxs-lookup"><span data-stu-id="6c068-144">In This Section</span></span>  
  
-   [<span data-ttu-id="6c068-145">步骤 1： 生成并部署用于接收 IDOC vPrev BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="6c068-145">Step 1: Build and Deploy the vPrev BizTalk Project for Receiving an IDOC</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc.md)  
  
-   [<span data-ttu-id="6c068-146">步骤 2： 配置 WCF 自定义单向接收端口</span><span class="sxs-lookup"><span data-stu-id="6c068-146">Step 2: Configure a WCF-Custom One-way Receive Port</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)  
  
-   [<span data-ttu-id="6c068-147">步骤 3： 测试已迁移的应用程序</span><span class="sxs-lookup"><span data-stu-id="6c068-147">Step 3: Test the Migrated Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)  
  
## <a name="see-also"></a><span data-ttu-id="6c068-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c068-148">See Also</span></span>  
 [<span data-ttu-id="6c068-149">SAP 适配器教程</span><span class="sxs-lookup"><span data-stu-id="6c068-149">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)