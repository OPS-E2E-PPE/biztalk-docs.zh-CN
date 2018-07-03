---
title: 教程 4： 迁移 SAP 接收 IDOC BizTalk 项目 |Microsoft Docs
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
ms.openlocfilehash: e943c3663767d2b684b0f4657f639d752705b86f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011254"
---
# <a name="tutorial-4-migrating-an-sap-receive-idoc-biztalk-project"></a><span data-ttu-id="00288-102">教程 4： 迁移 SAP 接收 IDOC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="00288-102">Tutorial 4: Migrating an SAP Receive IDOC BizTalk Project</span></span>
<span data-ttu-id="00288-103">SAP 适配器随 Microsoft BizTalk Server 的以前版本不同于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在许多方面，包括：</span><span class="sxs-lookup"><span data-stu-id="00288-103">The previous version of the SAP adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="00288-104">创建 BizTalk 项目的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="00288-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="00288-105">元数据检索体验。</span><span class="sxs-lookup"><span data-stu-id="00288-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="00288-106">架构文件的名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="00288-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="00288-107">数据类型映射。</span><span class="sxs-lookup"><span data-stu-id="00288-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="00288-108">可以使用适配器执行的操作。</span><span class="sxs-lookup"><span data-stu-id="00288-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="00288-109">在 BizTalk Server 管理控制台中的物理端口配置。</span><span class="sxs-lookup"><span data-stu-id="00288-109">Physical port configuration in the BizTalk Server Administration console.</span></span>  
  
  <span data-ttu-id="00288-110">在中的主题解释了这些差异[迁移 BizTalk 项目创建使用 SAP 适配器的上一步版本](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)。</span><span class="sxs-lookup"><span data-stu-id="00288-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the SAP Adapter](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span></span>  
  
  <span data-ttu-id="00288-111">但是，可以创建使用以前版本的适配器的 BizTalk 项目进行更改并使其适用于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00288-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
  <span data-ttu-id="00288-112">本教程说明了您应该对使用以前版本的适配器创建的现有 BizTalk 项目的更改。</span><span class="sxs-lookup"><span data-stu-id="00288-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00288-113">本教程中，为了简洁起见，在以前版本的 SAP 适配器称为 vPrev SAP 适配器。</span><span class="sxs-lookup"><span data-stu-id="00288-113">In this tutorial, for the sake of brevity, the previous version of the SAP adapter will be referred to as vPrev SAP adapter.</span></span> <span data-ttu-id="00288-114">同样，使用 vPrev SAP 适配器的 BizTalk 项目将引用为 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="00288-114">Similarly, a BizTalk project that uses the vPrev SAP adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="00288-115">本教程使用示例</span><span class="sxs-lookup"><span data-stu-id="00288-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="00288-116">基于本教程演示如何从 SAP 系统接收平面文件 IDOC 的 vPrev BizTalk 项目迁移的示例 (ReceiveIDOC_Migration)。</span><span class="sxs-lookup"><span data-stu-id="00288-116">This tutorial is based upon a sample (ReceiveIDOC_Migration) that demonstrates how to migrate a vPrev BizTalk project that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="00288-117">使用提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00288-117">The sample is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="00288-118">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="00288-118">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="00288-119">必要條件</span><span class="sxs-lookup"><span data-stu-id="00288-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="00288-120">必须有一个 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="00288-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="00288-121">本教程涉及到从 SAP 系统接收 ORDERS03 IDOC BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="00288-121">This tutorial involves a BizTalk project that receives an ORDERS03 IDOC from an SAP system.</span></span>  
  
-   [<span data-ttu-id="00288-122">创建强名称密钥文件并了解相关工具</span><span class="sxs-lookup"><span data-stu-id="00288-122">Create strong-name key file, and learn the tools</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)

  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="00288-123">了解 BizTalk 项目创建使用以前版本的适配器</span><span class="sxs-lookup"><span data-stu-id="00288-123">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="00288-124">关键组成部分 vPrev BizTalk 项目以接收 IDOC 是：</span><span class="sxs-lookup"><span data-stu-id="00288-124">The key constituents of a vPrev BizTalk project to receive an IDOC are:</span></span>  
  
-   <span data-ttu-id="00288-125">**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="00288-125">**BizTalk orchestration**.</span></span> <span data-ttu-id="00288-126">这是一个简单包含一个 SAP 的业务流程接收端口接收来自 SAP 系统的平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="00288-126">This is a simple orchestration that consists of an SAP receive port that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="00288-127">BizTalk 项目包含平面文件拆装器将平面文件 IDOC 转换为 XML，以便可以在业务流程中使用它。</span><span class="sxs-lookup"><span data-stu-id="00288-127">The BizTalk project contains a flat-file disassembler to convert the flat-file IDOC to an XML, so that it can be used in an orchestration.</span></span> <span data-ttu-id="00288-128">XML IDOC 复制到文件位置通过 file 端口之前，它将转换回使用平面文件组装器平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="00288-128">Before the XML IDOC is copied to a file location through a file port, it is converted back into a flat-file IDOC using a flat-file assembler.</span></span>  
  
-   <span data-ttu-id="00288-129">**你想要将发送到 SAP 系统的 IDOC 的架构**。</span><span class="sxs-lookup"><span data-stu-id="00288-129">**Schema for the IDOC you want to send to the SAP system**.</span></span> <span data-ttu-id="00288-130">本教程涉及到从 SAP 系统接收 ORDERS03 IDOC BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="00288-130">This tutorial involves a BizTalk project that receives ORDERS03 IDOC from the SAP system.</span></span> <span data-ttu-id="00288-131">生成 IDOC 的架构是 ORDERS03.xsd。</span><span class="sxs-lookup"><span data-stu-id="00288-131">The schema generated for the IDOC is ORDERS03.xsd.</span></span> <span data-ttu-id="00288-132">此架构是使用 vPrev SAP 适配器生成的。</span><span class="sxs-lookup"><span data-stu-id="00288-132">This schema is generated using the vPrev SAP adapter.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="00288-133">使用以前版本的适配器如何迁移 BizTalk 项目创建</span><span class="sxs-lookup"><span data-stu-id="00288-133">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="00288-134">此迁移教程的目的是使您能够从 SAP 系统为 vPrev SAP 适配器使用而不发送端口的 Wcf-custom 发送端口接收平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="00288-134">The goal of this migration tutorial is to enable you to receive a flat-file IDOC from an SAP system using a WCF-Custom send port instead of the send port for the vPrev SAP adapter.</span></span> <span data-ttu-id="00288-135">之前了解哪些设置所需的 Wcf-custom 发送端口，您首先必须了解哪些物理端口所需的 vPrev 发送 IDOC 的业务流程。</span><span class="sxs-lookup"><span data-stu-id="00288-135">Before understanding what settings are required for the WCF-Custom send port, you must first understand what physical ports are required for the vPrev send IDOC orchestration.</span></span>  
  
- <span data-ttu-id="00288-136">VPrev SAP 接收端口接收来自 SAP 系统的平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="00288-136">A vPrev SAP receive port that receives a flat-file IDOC from an SAP system.</span></span> <span data-ttu-id="00288-137">端口还将此转换为 XML IDOC 使用平面文件拆装器，可作为 vPrev BizTalk 应用程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="00288-137">The port also converts this to an XML IDOC using a flat-file disassembler, which is available as part of the vPrev BizTalk application.</span></span> <span data-ttu-id="00288-138">使用 vPrev SAP 适配器生成的架构 (ORDERS03.xsd) 符合 XML IDOC。</span><span class="sxs-lookup"><span data-stu-id="00288-138">The XML IDOC conforms to the schema (ORDERS03.xsd) that you generated using the vPrev SAP adapter.</span></span>  
  
- <span data-ttu-id="00288-139">File 发送端口将 IDOC 复制到文件夹。</span><span class="sxs-lookup"><span data-stu-id="00288-139">A file send port which copies the IDOC to folder.</span></span> <span data-ttu-id="00288-140">此端口还使用平面文件组装器管道的 BizTalk 应用程序，可将 XML IDOC 转换为平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="00288-140">This port also uses the flat-file assembler pipeline, available in the BizTalk application, to convert the XML IDOC to a flat-file IDOC.</span></span>  
  
  <span data-ttu-id="00288-141">若要迁移现有 vPrev BizTalk 项目，你不必更改复制到的文件夹的平面文件 IDOC 的文件发送端口。</span><span class="sxs-lookup"><span data-stu-id="00288-141">To migrate your existing vPrev BizTalk project, you do not need to change the file send port that copies the flat-file IDOC to a folder.</span></span> <span data-ttu-id="00288-142">只需配置一个新 WCF 自定义接收端口使用正确的配置设置。</span><span class="sxs-lookup"><span data-stu-id="00288-142">You only need to configure a new WCF-Custom receive port with the right configuration settings.</span></span> <span data-ttu-id="00288-143">本教程演示如何配置 WCF 自定义接收端口以接收来自 SAP 系统使用基于 WCF 的 Idoc [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="00288-143">This tutorial demonstrates how to configure the WCF-Custom receive port to receive IDOCs from an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="00288-144">本节内容</span><span class="sxs-lookup"><span data-stu-id="00288-144">In This Section</span></span>  
  
-   [<span data-ttu-id="00288-145">步骤 1：生成和部署 vPrev BizTalk 项目来接收 IDOC</span><span class="sxs-lookup"><span data-stu-id="00288-145">Step 1: Build and Deploy the vPrev BizTalk Project for Receiving an IDOC</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-receiving-an-idoc.md)  
  
-   [<span data-ttu-id="00288-146">步骤 2：配置 WCF 自定义单向接收端口</span><span class="sxs-lookup"><span data-stu-id="00288-146">Step 2: Configure a WCF-Custom One-way Receive Port</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-receive-port.md)  
  
-   [<span data-ttu-id="00288-147">步骤 3：测试已迁移的应用程序</span><span class="sxs-lookup"><span data-stu-id="00288-147">Step 3: Test the Migrated Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application5.md)  
  
## <a name="see-also"></a><span data-ttu-id="00288-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="00288-148">See Also</span></span>  
 [<span data-ttu-id="00288-149">SAP 适配器教程</span><span class="sxs-lookup"><span data-stu-id="00288-149">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)