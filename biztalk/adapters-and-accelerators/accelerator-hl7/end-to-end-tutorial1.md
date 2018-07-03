---
title: 端到端 Tutorial1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.endtoendtutorial
helpviewer_keywords:
- end-to-end tutorial, about the tutorial
- end-to-end tutorial
- tutorials, end-to-end tutorial
ms.assetid: 90625edc-70a0-42c9-a2fb-8eeb5465d766
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 264a6eee008b9b327185c931ad4e5ac60cdc995a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37000734"
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="be292-102">端到端教程</span><span class="sxs-lookup"><span data-stu-id="be292-102">End-to-End Tutorial</span></span>
<span data-ttu-id="be292-103">本教程包含详细的步骤，描述如何使用 Microsoft[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]来推进业务流程在订阅服务器和发布服务器的方案。</span><span class="sxs-lookup"><span data-stu-id="be292-103">This tutorial contains detailed steps that describe how you use Microsoft [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to facilitate business processes in a subscriber and publisher scenario.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="be292-104">若要使用本教程，必须安装 BTAHL7 时安装的测试工具。</span><span class="sxs-lookup"><span data-stu-id="be292-104">To use this tutorial, you must install the test tools when installing BTAHL7.</span></span> <span data-ttu-id="be292-105">如果您执行典型安装中安装 BTAHL7，然后必须运行自定义安装，并按本教程中正常工作的顺序安装测试工具。</span><span class="sxs-lookup"><span data-stu-id="be292-105">If you performed a typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="be292-106">在**自定义安装**BTAHL7 自定义安装中，选择屏幕**MLLP 测试工具**从**适配器**文件夹，然后选择**测试实例**从**项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="be292-106">At the **Custom Setup** screen of the BTAHL7 custom installation, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="be292-107">有关详细信息，请参阅[安装 BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。</span><span class="sxs-lookup"><span data-stu-id="be292-107">For more information, see [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="declarative-scenario"></a><span data-ttu-id="be292-108">声明性方案</span><span class="sxs-lookup"><span data-stu-id="be292-108">Declarative Scenario</span></span>  
 <span data-ttu-id="be292-109">本教程使用的发布/订阅或声明性的方案。</span><span class="sxs-lookup"><span data-stu-id="be292-109">This tutorial uses the publish/subscribe or declarative scenario.</span></span> <span data-ttu-id="be292-110">在声明性的方案中流程是业务的类似于下图中所示。</span><span class="sxs-lookup"><span data-stu-id="be292-110">In the declarative scenario, the flow of business is similar to that shown in the following figure.</span></span> <span data-ttu-id="be292-111">编号的列表下图描述的工作流。</span><span class="sxs-lookup"><span data-stu-id="be292-111">The numbered list following the figure describes the workflow.</span></span>  
  
 <span data-ttu-id="be292-112">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")</span><span class="sxs-lookup"><span data-stu-id="be292-112">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")</span></span>  
<span data-ttu-id="be292-113">显示的声明性方案的业务流图</span><span class="sxs-lookup"><span data-stu-id="be292-113">Figure showing the flow of business for the declarative scenario</span></span>  
  
1.  <span data-ttu-id="be292-114">在工作流开始时发布服务器，例如，一个病人入院出院事项和传输系统中，将消息发送到特定的订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="be292-114">The workflow begins when the publisher, for example, an Admissions Discharge and Transfer system, sends a message to specific subscribers.</span></span> <span data-ttu-id="be292-115">工作流中的发布服务器进行"Tutorial_ADTSystem"，并调用消息"**ADT ^ A103**。"</span><span class="sxs-lookup"><span data-stu-id="be292-115">The publisher in the workflow is "Tutorial_ADTSystem", and the message is called "**ADT^A103**."</span></span>  
  
2.  <span data-ttu-id="be292-116">消息路由到 BTAHL7 接口引擎，又接收、 处理、 验证、 重新格式化，并随后将消息路由到订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="be292-116">The message is routed to the BTAHL7 Interface Engine, which in turn receives, processes, validates, reformats, and then routes the message to subscribers.</span></span>  
  
3.  <span data-ttu-id="be292-117">在此方案中的订阅服务器是医院信息系统 (Tutorial_HISystem) 和药房系统 (Tutorial_RXSystem)。</span><span class="sxs-lookup"><span data-stu-id="be292-117">The subscribers in this scenario are a Hospital Information System (Tutorial_HISystem) and a Pharmacy System (Tutorial_RXSystem).</span></span> <span data-ttu-id="be292-118">此方案使用文件和 MLLP 适配器类型。</span><span class="sxs-lookup"><span data-stu-id="be292-118">This scenario uses both File and MLLP adapter types.</span></span> <span data-ttu-id="be292-119">发布服务器不需要注意的订阅服务器并 BTAHL7 处理消息之后中适当地将确认发送到发布服务器。</span><span class="sxs-lookup"><span data-stu-id="be292-119">The publisher does not need to be aware of the subscribers and BTAHL7 appropriately sends an acknowledgment to the publisher after processing the message.</span></span>  
  
4.  <span data-ttu-id="be292-120">发布服务器发送 ADT ^ A03 消息通过单向 MLLP 适配器 (Tutorial_1WayReceivePort)。</span><span class="sxs-lookup"><span data-stu-id="be292-120">The publisher sends the ADT^A03 message through a one-way MLLP adapter (Tutorial_1WayReceivePort).</span></span>  
  
5.  <span data-ttu-id="be292-121">此消息的目标是 BTAHL7 接口引擎，因此传入消息包含源消息 (MSH3 = Tutorial_ADTSystem) 和目标消息 (MSH5 = BTAHL7InterfaceEngine)。</span><span class="sxs-lookup"><span data-stu-id="be292-121">The destination of this message is the BTAHL7 Interface Engine, so the incoming message contains a source message (MSH3 = Tutorial_ADTSystem) and a destination message (MSH5 = BTAHL7InterfaceEngine).</span></span>  
  
6.  <span data-ttu-id="be292-122">BTAHL7 适当地验证消息后, 生成的确认 (ACK)，并随后将确认发送到通过文件适配器 Tutorial_ADTSystem。</span><span class="sxs-lookup"><span data-stu-id="be292-122">BTAHL7 generates an acknowledgment (ACK) after appropriately validating the message, and then sends the acknowledgment to the Tutorial_ADTSystem through the File adapter.</span></span>  
  
7.  <span data-ttu-id="be292-123">Tutorial_HISystem 系统和 Tutorial_RXSystem 系统订阅 BTAHL7 接口引擎接收的 ADT 消息。</span><span class="sxs-lookup"><span data-stu-id="be292-123">The Tutorial_HISystem system and the Tutorial_RXSystem system subscribe to the ADT message received by the BTAHL7 Interface Engine.</span></span>  
  
8.  <span data-ttu-id="be292-124">使用指定的相应字段的值时发生转换**MSH 映射**BTAHL7 配置资源管理器中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="be292-124">The transformation occurs when you specify values for the respective fields by using the **MSH Map** tab in BTAHL7 Configuration Explorer.</span></span>  
  
     <span data-ttu-id="be292-125">例如，参与方 Tutorial_RXSystem 具有 MSH3 = 中指定的 BTHL7 **MSH 映射**选项卡。因此，订阅服务器接收的消息将具有"BTAHL7"与 MSH3 字段的值。</span><span class="sxs-lookup"><span data-stu-id="be292-125">For example, the party Tutorial_RXSystem has MSH3=BTHL7 specified in the **MSH Map** tab. Therefore, the message received by the subscriber will have "BTAHL7" as the value for the MSH3 field.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be292-126">本节内容</span><span class="sxs-lookup"><span data-stu-id="be292-126">In this section</span></span>  
  
-   [<span data-ttu-id="be292-127">测试安装</span><span class="sxs-lookup"><span data-stu-id="be292-127">Testing Your Installation</span></span>](../../adapters-and-accelerators/accelerator-hl7/testing-your-installation.md)  
  
-   [<span data-ttu-id="be292-128">为使用教程做准备</span><span class="sxs-lookup"><span data-stu-id="be292-128">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)  
  
-   [<span data-ttu-id="be292-129">步骤 1：创建和部署标头及确认架构</span><span class="sxs-lookup"><span data-stu-id="be292-129">Step 1: Create and Deploy Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="be292-130">步骤 2： 创建适用于 v2.3.1 的通用架构</span><span class="sxs-lookup"><span data-stu-id="be292-130">Step 2: Create Common Schemas for v2.3.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)  
  
-   [<span data-ttu-id="be292-131">步骤 3：创建和部署触发器事件（消息）项目</span><span class="sxs-lookup"><span data-stu-id="be292-131">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project.md)  
  
-   [<span data-ttu-id="be292-132">步骤 4：使用 MLLP 适配器，创建从 ADT 系统接收 ADT^A03 消息的接收端口</span><span class="sxs-lookup"><span data-stu-id="be292-132">Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)  
  
-   [<span data-ttu-id="be292-133">步骤 5：使用文件适配器创建发送端口以将确认传递至 ADT 系统</span><span class="sxs-lookup"><span data-stu-id="be292-133">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)  
  
-   [<span data-ttu-id="be292-134">步骤 6：使用文件适配器创建发送端口以将 ADT^A03 消息传递至 RX 系统</span><span class="sxs-lookup"><span data-stu-id="be292-134">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)  
  
-   [<span data-ttu-id="be292-135">步骤 7：使用 MLLP 适配器创建发送端口以将 ADT^A03 消息传递至 HIS</span><span class="sxs-lookup"><span data-stu-id="be292-135">Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)  
  
-   [<span data-ttu-id="be292-136">步骤 8：配置参与方信息</span><span class="sxs-lookup"><span data-stu-id="be292-136">Step 8: Configure Party Information</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)  
  
-   [<span data-ttu-id="be292-137">步骤 9：重启 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="be292-137">Step 9: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="be292-138">步骤 10：验证端到端方案</span><span class="sxs-lookup"><span data-stu-id="be292-138">Step 10: Verify the End-to-End Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-end-to-end-scenario.md)

## <a name="see-also"></a><span data-ttu-id="be292-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="be292-139">See also</span></span>
[<span data-ttu-id="be292-140">BizTalk Accelerator for HL7 入门</span><span class="sxs-lookup"><span data-stu-id="be292-140">Get started with the BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)