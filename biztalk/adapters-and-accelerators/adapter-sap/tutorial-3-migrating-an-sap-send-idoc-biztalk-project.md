---
title: 教程 3:迁移 SAP 发送 IDOC BizTalk 项目 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- migrating, SAP Send IDOC BizTalk project
- migration
ms.assetid: c0a11432-5388-4054-8996-08a957cc02eb
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 524e6fd3bbd793f318013c55da0a8987244aa682
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372289"
---
# <a name="tutorial-3-migrating-an-sap-send-idoc-biztalk-project"></a><span data-ttu-id="6f385-102">教程 3:迁移 SAP 发送 IDOC BizTalk 项目</span><span class="sxs-lookup"><span data-stu-id="6f385-102">Tutorial 3: Migrating an SAP Send IDOC BizTalk Project</span></span>
<span data-ttu-id="6f385-103">SAP 适配器随 Microsoft BizTalk Server 的以前版本不同于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在许多方面，包括：</span><span class="sxs-lookup"><span data-stu-id="6f385-103">The previous version of the SAP adapter that shipped with Microsoft BizTalk Server differs from the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] in many aspects, including:</span></span>  
  
- <span data-ttu-id="6f385-104">创建 BizTalk 项目的设计时体验。</span><span class="sxs-lookup"><span data-stu-id="6f385-104">The design-time experience of creating a BizTalk project.</span></span>  
  
- <span data-ttu-id="6f385-105">元数据检索体验。</span><span class="sxs-lookup"><span data-stu-id="6f385-105">The metadata retrieval experience.</span></span>  
  
- <span data-ttu-id="6f385-106">架构文件的名称和命名空间。</span><span class="sxs-lookup"><span data-stu-id="6f385-106">Schema file name and namespace.</span></span>  
  
- <span data-ttu-id="6f385-107">数据类型映射。</span><span class="sxs-lookup"><span data-stu-id="6f385-107">Data type mappings.</span></span>  
  
- <span data-ttu-id="6f385-108">可以使用适配器执行的操作。</span><span class="sxs-lookup"><span data-stu-id="6f385-108">The operations that can be performed using the adapter.</span></span>  
  
- <span data-ttu-id="6f385-109">在 BizTalk Server 管理控制台中的物理端口配置。</span><span class="sxs-lookup"><span data-stu-id="6f385-109">Physical port configuration in the BizTalk Server Administration console.</span></span>  
  
  <span data-ttu-id="6f385-110">在中的主题解释了这些差异[迁移 BizTalk 项目创建使用 SAP 适配器的上一步版本](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37)。</span><span class="sxs-lookup"><span data-stu-id="6f385-110">These differences are explained in the topics within [Migrating BizTalk Projects Created Using the Previous Version of the SAP Adapter](http://msdn.microsoft.com/library/a486bac9-8952-43fd-8099-413f1491de37).</span></span>  
  
  <span data-ttu-id="6f385-111">但是，可以创建使用以前版本的适配器的 BizTalk 项目进行更改并使其适用于基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6f385-111">However, you can make changes to the BizTalk project created using the previous version of the adapter and make it work with the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
  <span data-ttu-id="6f385-112">本教程说明了您应该对使用以前版本的适配器创建的现有 BizTalk 项目的更改。</span><span class="sxs-lookup"><span data-stu-id="6f385-112">This tutorial provides instructions on the changes you should make to the existing BizTalk project created using the previous version of the adapter.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f385-113">本教程中，为了简洁起见，在以前版本的 SAP 适配器称为 vPrev SAP 适配器。</span><span class="sxs-lookup"><span data-stu-id="6f385-113">In this tutorial, for the sake of brevity, the previous version of the SAP adapter will be referred to as vPrev SAP adapter.</span></span> <span data-ttu-id="6f385-114">同样，使用 vPrev SAP 适配器的 BizTalk 项目将引用为 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6f385-114">Similarly, a BizTalk project that uses the vPrev SAP adapter will be referred to as vPrev BizTalk project.</span></span>  
  
## <a name="sample-used-for-the-tutorial"></a><span data-ttu-id="6f385-115">本教程使用示例</span><span class="sxs-lookup"><span data-stu-id="6f385-115">Sample Used for the Tutorial</span></span>  
 <span data-ttu-id="6f385-116">基于本教程演示如何迁移将 IDOC 发送到 SAP 系统的 vPrev BizTalk 项目的示例 (SendIDOC_Migration)。</span><span class="sxs-lookup"><span data-stu-id="6f385-116">This tutorial is based upon a sample (SendIDOC_Migration) that demonstrates how to migrate a vPrev BizTalk project that sends an IDOC to an SAP system.</span></span> <span data-ttu-id="6f385-117">使用提供了示例[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6f385-117">The sample is provided with the [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)].</span></span> <span data-ttu-id="6f385-118">有关详细信息，请参阅[适配器示例](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="6f385-118">For more information, see [Adapter Samples](../../adapters-and-accelerators/accelerator-rosettanet/adapter-samples.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="6f385-119">先决条件</span><span class="sxs-lookup"><span data-stu-id="6f385-119">Prerequisites</span></span>  
  
-   <span data-ttu-id="6f385-120">必须有一个 vPrev BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6f385-120">You must have a vPrev BizTalk project.</span></span> <span data-ttu-id="6f385-121">本教程涉及到将 BOMDOC IDOC 发送到 SAP 系统的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6f385-121">This tutorial involves a BizTalk project that sends a BOMDOC IDOC to an SAP system.</span></span>  
  
-   <span data-ttu-id="6f385-122">您必须具有平面文件 BOMDOC IDOC 发送到 SAP 系统使用 vPrev SAP 适配器。</span><span class="sxs-lookup"><span data-stu-id="6f385-122">You must have a flat-file BOMDOC IDOC to send to the SAP system using the vPrev SAP adapter.</span></span> <span data-ttu-id="6f385-123">对于本教程提供的示例包含此平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="6f385-123">The sample provided for this tutorial contains this flat-file IDOC.</span></span>  
  
-   [<span data-ttu-id="6f385-124">创建强名称密钥文件并了解相关工具</span><span class="sxs-lookup"><span data-stu-id="6f385-124">Create strong-name key file, and learn the tools</span></span>](../../adapters-and-accelerators/adapter-sap/prerequisites-to-create-sap-applications.md)
  
## <a name="understanding-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="6f385-125">了解 BizTalk 项目创建使用以前版本的适配器</span><span class="sxs-lookup"><span data-stu-id="6f385-125">Understanding a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="6f385-126">是的关键组成部分 vPrev BizTalk 项目以将 IDOC 发送：</span><span class="sxs-lookup"><span data-stu-id="6f385-126">The key constituents of a vPrev BizTalk project to send an IDOC are:</span></span>  
  
-   <span data-ttu-id="6f385-127">**BizTalk 业务流程**。</span><span class="sxs-lookup"><span data-stu-id="6f385-127">**BizTalk orchestration**.</span></span> <span data-ttu-id="6f385-128">这是一个简单的业务流程从文件位置提取平面文件 IDOC 并发送到 SAP 系统使用 SAP IDOC 发送端口。</span><span class="sxs-lookup"><span data-stu-id="6f385-128">This is a simple orchestration that picks a flat-file IDOC from a file location and sends the IDOC to the SAP system using an SAP send port.</span></span> <span data-ttu-id="6f385-129">BizTalk 项目包含平面文件拆装器将平面文件 IDOC 转换为 XML，以便可以在业务流程中使用它。</span><span class="sxs-lookup"><span data-stu-id="6f385-129">The BizTalk project contains a flat-file disassembler to convert the flat-file IDOC to an XML, so that it can be used in an orchestration.</span></span> <span data-ttu-id="6f385-130">XML IDOC 供的 vPrev SAP 发送端口之前，它将转换回使用平面文件组装器平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="6f385-130">Before the XML IDOC is consumed by the vPrev SAP send port, it is converted back into a flat-file IDOC using a flat-file assembler.</span></span>  
  
-   <span data-ttu-id="6f385-131">**你想要将发送到 SAP 系统的 IDOC 的架构**。</span><span class="sxs-lookup"><span data-stu-id="6f385-131">**Schema for the IDOC you want to send to the SAP system**.</span></span> <span data-ttu-id="6f385-132">对于本教程中，您需要将 BOMDOC01 IDOC 发送到 SAP 系统的 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="6f385-132">For this tutorial, you take a BizTalk project that sends BOMDOC01 IDOC to the SAP system.</span></span> <span data-ttu-id="6f385-133">生成 IDOC 的架构是 BOMDOC01.xsd。</span><span class="sxs-lookup"><span data-stu-id="6f385-133">The schema generated for the IDOC is BOMDOC01.xsd.</span></span> <span data-ttu-id="6f385-134">此架构是使用 vPrev SAP 适配器生成的。</span><span class="sxs-lookup"><span data-stu-id="6f385-134">This schema is generated using the vPrev SAP adapter.</span></span>  
  
-   <span data-ttu-id="6f385-135">**平面文件 IDOC**。</span><span class="sxs-lookup"><span data-stu-id="6f385-135">**The flat-file IDOC**.</span></span> <span data-ttu-id="6f385-136">这是发送到 SAP 系统的平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="6f385-136">This is the flat-file IDOC that is sent to the SAP system.</span></span>  
  
## <a name="how-to-migrate-a-biztalk-project-created-using-the-previous-version-of-the-adapter"></a><span data-ttu-id="6f385-137">使用以前版本的适配器如何迁移 BizTalk 项目创建</span><span class="sxs-lookup"><span data-stu-id="6f385-137">How to Migrate a BizTalk Project Created Using the Previous Version of the Adapter</span></span>  
 <span data-ttu-id="6f385-138">此迁移教程的目的是使您能够将平面文件 IDOC 发送到 SAP 系统为 vPrev SAP 适配器使用而不发送端口的 Wcf-custom 发送端口。</span><span class="sxs-lookup"><span data-stu-id="6f385-138">The goal of this migration tutorial is to enable you to send a flat-file IDOC to an SAP system using a WCF-Custom send port instead of the send port for the vPrev SAP adapter.</span></span> <span data-ttu-id="6f385-139">在了解哪些设置所需的 Wcf-custom 发送端口之前, 您首先必须了解哪些物理端口所需的 vPrev 发送 IDOC 的业务流程：</span><span class="sxs-lookup"><span data-stu-id="6f385-139">Before understanding what settings are required for the WCF-Custom send port, you must first understand what physical ports are required for the vPrev send IDOC orchestration:</span></span>  
  
- <span data-ttu-id="6f385-140">File 接收端口提取平面文件 IDOC。</span><span class="sxs-lookup"><span data-stu-id="6f385-140">A file receive port that picks the flat-file IDOC.</span></span> <span data-ttu-id="6f385-141">此端口使用平面文件拆装器管道的 BizTalk 应用程序，可将平面文件转换为符合架构 (BOMDOC01.xsd) 使用 vPrev SAP 适配器生成的 XML。</span><span class="sxs-lookup"><span data-stu-id="6f385-141">This port uses the flat-file disassembler pipeline, available in the BizTalk application, to convert the flat-file into an XML that conforms to the schema (BOMDOC01.xsd) generated using the vPrev SAP adapter.</span></span>  
  
- <span data-ttu-id="6f385-142">VPrev SAP 发送将平面文件 IDOC 发送到 SAP 系统的端口。</span><span class="sxs-lookup"><span data-stu-id="6f385-142">A vPrev SAP send port that sends the flat-file IDOC to the SAP system.</span></span> <span data-ttu-id="6f385-143">在发送前平面文件，该端口使用平面文件组装器将 XML IDOC 平面文件 IDOC 转换。</span><span class="sxs-lookup"><span data-stu-id="6f385-143">Before sending the flat-file, the port uses the flat-file assembler to convert the XML IDOC into a flat-file IDOC.</span></span>  
  
  <span data-ttu-id="6f385-144">若要迁移现有 vPrev BizTalk 项目，你不必更改文件接收端口提取平面文件 IDOC 并将平面文件 IDOC 转换为 XML 使用平面文件拆装器。</span><span class="sxs-lookup"><span data-stu-id="6f385-144">To migrate your existing vPrev BizTalk project, you do not need to change the file receive port that picks the flat-file IDOC and converts the flat-file IDOC to XML using a flat-file disassembler.</span></span> <span data-ttu-id="6f385-145">只需使用正确的配置设置来配置新的 WCF 自定义发送端口。</span><span class="sxs-lookup"><span data-stu-id="6f385-145">You only need to configure a new WCF-Custom send port with the right configuration settings.</span></span> <span data-ttu-id="6f385-146">本教程演示如何配置 Wcf-custom 发送端口以将 Idoc 发送到 SAP 系统使用基于 WCF 的[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="6f385-146">This tutorial demonstrates how to configure the WCF-Custom send port to send IDOCs to an SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6f385-147">本节内容</span><span class="sxs-lookup"><span data-stu-id="6f385-147">In This Section</span></span>  
  
-   [<span data-ttu-id="6f385-148">步骤 1：生成和部署 vPrev BizTalk 项目以发送 IDOC</span><span class="sxs-lookup"><span data-stu-id="6f385-148">Step 1: Build and Deploy the vPrev BizTalk Project for Sending an IDOC</span></span>](../../adapters-and-accelerators/adapter-sap/step-1-build-and-deploy-the-vprev-biztalk-project-for-sending-an-idoc.md)  
  
-   [<span data-ttu-id="6f385-149">步骤 2：配置 WCF 自定义单向发送端口</span><span class="sxs-lookup"><span data-stu-id="6f385-149">Step 2: Configure a WCF-Custom One-way Send Port</span></span>](../../adapters-and-accelerators/adapter-sap/step-2-configure-a-wcf-custom-one-way-send-port.md)  
  
-   [<span data-ttu-id="6f385-150">步骤 3：测试已迁移的应用程序</span><span class="sxs-lookup"><span data-stu-id="6f385-150">Step 3: Test the Migrated Application</span></span>](../../adapters-and-accelerators/adapter-sap/step-3-test-the-migrated-application2.md)  
  
## <a name="see-also"></a><span data-ttu-id="6f385-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f385-151">See Also</span></span>  
 [<span data-ttu-id="6f385-152">SAP 适配器教程</span><span class="sxs-lookup"><span data-stu-id="6f385-152">SAP Adapter Tutorials</span></span>](../../adapters-and-accelerators/adapter-sap/sap-adapter-tutorials.md)