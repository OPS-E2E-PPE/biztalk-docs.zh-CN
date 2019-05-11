---
title: 消息充实教程 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial
- message enrichment tutorial, about the tutorial
- messages, tutorial
- tutorials, message enrichment tutorial
ms.assetid: 4ffb047f-457a-4a80-b7ec-4b61ae16f35f
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2760cfa52fc7e761829d3005bfecbb8bb40a728
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65303691"
---
# <a name="message-enrichment-tutorial"></a><span data-ttu-id="b453b-102">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="b453b-102">Message Enrichment Tutorial</span></span>
<span data-ttu-id="b453b-103">本教程提供了分步过程使用 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]解决特定业务问题： 消息充实问题。</span><span class="sxs-lookup"><span data-stu-id="b453b-103">This tutorial provides step-by-step procedures for using Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to solve a particular business problem: the message enrichment problem.</span></span> <span data-ttu-id="b453b-104">消息充实教程介绍了需要添加或丰富的情况下，一条消息，不符合 HL7 和/或不完整。</span><span class="sxs-lookup"><span data-stu-id="b453b-104">The message enrichment tutorial describes a situation in which you have to add to, or enrich, a message that is not HL7-compliant and/or is incomplete.</span></span> <span data-ttu-id="b453b-105">这可能会出现应用程序，如患者注册应用程序，或您在安装消息与来自 Microsoft 的 XML 数据时可能发生[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b453b-105">This can occur with an application, such as a patient registration application, or it can occur when you are populating a message with XML data from Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b453b-106">在本教程中，将捕获与 BTAHL7，消息和提供任何缺失的数据，例如，从患者记录数据库。</span><span class="sxs-lookup"><span data-stu-id="b453b-106">In this tutorial, you capture the messages with BTAHL7, and provide any missing data, for example, from a patient records database.</span></span> <span data-ttu-id="b453b-107">然后将消息转换，并将其发送到实验室、 保險、 或任何旧的业务线 (LOB) 应用程序使用 （最少的较低层协议） 处的 MLLP 适配器。</span><span class="sxs-lookup"><span data-stu-id="b453b-107">You then convert the message and send it to a laboratory, insurance, or any legacy line-of-business (LOB) application using the MLLP (Minimal Lower Layer Protocol) adapter.</span></span>  
  
 <span data-ttu-id="b453b-108">在本教程中，您使用 Web 服务客户端 (WSClient.exe) 应用程序发送 XML 格式的消息，在此情况下"门铃"注册患者触发器事件，通过 SOAP 适配器到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]BTAHL7 使用。</span><span class="sxs-lookup"><span data-stu-id="b453b-108">In this tutorial, you use a Web service client (WSClient.exe) application to send an XML-formatted message, in this case a "doorbell" Register Patient trigger event, through the SOAP adapter to [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] with BTAHL7.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="b453b-109">接收的消息中 SOAP 接收端口和消息与业务流程发布为 Web 服务的路由。</span><span class="sxs-lookup"><span data-stu-id="b453b-109">receives the message in a SOAP receive port, and routes the message to an orchestration published as a Web service.</span></span> <span data-ttu-id="b453b-110">XML 消息包含患者的名称和社会安全号码。</span><span class="sxs-lookup"><span data-stu-id="b453b-110">The XML message contains a patient name and social security number.</span></span> <span data-ttu-id="b453b-111">增加消息，并使用架构、 映射和转换该消息转换为 HL7 格式。</span><span class="sxs-lookup"><span data-stu-id="b453b-111">You augment the message, and use schemas, a map, and a transform to convert the message into HL7 format.</span></span> <span data-ttu-id="b453b-112">然后会将其通过 MLLP 适配器发送到实验室，保险，，或 LOB 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b453b-112">You will then send it through an MLLP adapter to the laboratory, insurance, or LOB application.</span></span>  
  
 <span data-ttu-id="b453b-113">下图显示了本教程的处理流程。</span><span class="sxs-lookup"><span data-stu-id="b453b-113">The following figure shows the process flow of the tutorial.</span></span>  
  
 <span data-ttu-id="b453b-114">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-msgenrichtutarch.gif "hl7_msgenrichtutarch")</span><span class="sxs-lookup"><span data-stu-id="b453b-114">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-msgenrichtutarch.gif "hl7_msgenrichtutarch")</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b453b-115">本教程需要安装 Windows Server Standard、 Enterprise、 Datacenter、 或 Web Edition 和自定义的 BTAHL7 安装包含 MLLP 的测试工具。</span><span class="sxs-lookup"><span data-stu-id="b453b-115">This tutorial requires Windows Server Standard, Enterprise, Datacenter, or Web Edition, and a custom BTAHL7 installation that includes the MLLP test tools.</span></span> <span data-ttu-id="b453b-116">此外，您应熟悉[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]中的开发[!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)]和中找到的信息[了解 HL7 加速器及可用的 BizTalk 工具](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md)。</span><span class="sxs-lookup"><span data-stu-id="b453b-116">Additionally, you should be familiar with [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] development in [!INCLUDE[btsVCSharp](../../includes/btsvcsharp-md.md)] and the information found in [learn about the HL7 accelerator and the BizTalk tools available](../../adapters-and-accelerators/accelerator-hl7/learn-the-hl7-accelerator-and-the-biztalk-tools-available.md).</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="b453b-117">则可以避免由正在取消部署程序集，停止发送端口的错误和禁用接收位置在前面的教程中使用。</span><span class="sxs-lookup"><span data-stu-id="b453b-117">You can avoid errors by undeploying assemblies, stopping send ports, and disabling receive locations that you used in previous tutorials.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b453b-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="b453b-118">In this section</span></span>  
  
-   [<span data-ttu-id="b453b-119">步骤 1：配置应用程序池标识</span><span class="sxs-lookup"><span data-stu-id="b453b-119">Step 1: Configure Application Pool Identity</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-configure-application-pool-identity.md)  
  
-   [<span data-ttu-id="b453b-120">步骤 2：创建一个新项目</span><span class="sxs-lookup"><span data-stu-id="b453b-120">Step 2: Create a New Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-a-new-project.md)  
  
-   [<span data-ttu-id="b453b-121">步骤 3：为程序集分配强名称</span><span class="sxs-lookup"><span data-stu-id="b453b-121">Step 3: Assign a Strong Name to the Assembly</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-assign-a-strong-name-to-the-assembly.md)  
  
-   [<span data-ttu-id="b453b-122">步骤 4：创建架构</span><span class="sxs-lookup"><span data-stu-id="b453b-122">Step 4: Create the Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-schemas.md)  
  
-   [<span data-ttu-id="b453b-123">步骤 5：提升架构属性</span><span class="sxs-lookup"><span data-stu-id="b453b-123">Step 5: Promote Schema Properties</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-promote-schema-properties.md)  
  
-   [<span data-ttu-id="b453b-124">步骤 6：验证架构</span><span class="sxs-lookup"><span data-stu-id="b453b-124">Step 6: Validate the Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-validate-the-schemas.md)  
  
-   [<span data-ttu-id="b453b-125">步骤 7：登录和生成项目</span><span class="sxs-lookup"><span data-stu-id="b453b-125">Step 7: Sign and Build the Projects</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-sign-and-build-the-projects.md)  
  
-   [<span data-ttu-id="b453b-126">步骤 8：使用 BizTalk 映射器创建映射</span><span class="sxs-lookup"><span data-stu-id="b453b-126">Step 8: Create a Map with BizTalk Mapper</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-create-a-map-with-biztalk-mapper.md)  
  
-   [<span data-ttu-id="b453b-127">步骤 9：验证和生成映射项目</span><span class="sxs-lookup"><span data-stu-id="b453b-127">Step 9: Validate and Build the Map Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-validate-and-build-the-map-project.md)  
  
-   [<span data-ttu-id="b453b-128">步骤 10：创建业务流程</span><span class="sxs-lookup"><span data-stu-id="b453b-128">Step 10: Create an Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-create-an-orchestration.md)  
  
-   [<span data-ttu-id="b453b-129">步骤 11:创建业务流程变量</span><span class="sxs-lookup"><span data-stu-id="b453b-129">Step 11: Create Orchestration Variables</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-11-create-orchestration-variables.md)  
  
-   [<span data-ttu-id="b453b-130">步骤 12：配置业务流程形状</span><span class="sxs-lookup"><span data-stu-id="b453b-130">Step 12: Configure Orchestration Shapes</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-12-configure-orchestration-shapes.md)  
  
-   [<span data-ttu-id="b453b-131">步骤 13：创建和配置端口</span><span class="sxs-lookup"><span data-stu-id="b453b-131">Step 13: Create and Configure Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-13-create-and-configure-ports.md)  
  
-   [<span data-ttu-id="b453b-132">步骤 14：将业务流程作为 Web 服务发布</span><span class="sxs-lookup"><span data-stu-id="b453b-132">Step 14: Publish the Orchestration as a Web Service</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)  
  
-   [<span data-ttu-id="b453b-133">步骤 15：配置发送端口和接收端口</span><span class="sxs-lookup"><span data-stu-id="b453b-133">Step 15: Configure the Send and Receive Ports</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-15-configure-the-send-and-receive-ports.md)  
  
-   [<span data-ttu-id="b453b-134">步骤 16：启动业务流程</span><span class="sxs-lookup"><span data-stu-id="b453b-134">Step 16: Start the Orchestration</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)  
  
-   [<span data-ttu-id="b453b-135">步骤 17：创建 WSClient 应用程序</span><span class="sxs-lookup"><span data-stu-id="b453b-135">Step 17: Create the WSClient Application</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-17-create-the-wsclient-application.md)  
  
-   [<span data-ttu-id="b453b-136">步骤 18：测试新消息充实解决方案</span><span class="sxs-lookup"><span data-stu-id="b453b-136">Step 18: Test Your New Message Enrichment Solution</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-18-test-your-new-message-enrichment-solution.md)