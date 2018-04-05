---
title: 端到端 Tutorial1 |Microsoft 文档
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
ms.openlocfilehash: 90dc31ac286f8ce1e38d9a511eb319828d8ae939
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="end-to-end-tutorial"></a><span data-ttu-id="c1bd0-102">端到端教程</span><span class="sxs-lookup"><span data-stu-id="c1bd0-102">End-to-End Tutorial</span></span>
<span data-ttu-id="c1bd0-103">本教程包含的详细的步骤，描述如何使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]为了便于在订阅服务器和发布服务器方案中的业务流程。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-103">This tutorial contains detailed steps that describe how you use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to facilitate business processes in a subscriber and publisher scenario.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c1bd0-104">若要使用本教程，必须安装 BTAHL7 时安装的测试工具。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-104">To use this tutorial, you must install the test tools when installing BTAHL7.</span></span> <span data-ttu-id="c1bd0-105">如果执行典型的安装，以安装 BTAHL7，然后必须运行自定义安装，并按本教程中正常工作的顺序安装的测试工具。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-105">If you performed a typical installation to install BTAHL7, then you must run a Custom installation and install the test tools in order for this tutorial to work correctly.</span></span> <span data-ttu-id="c1bd0-106">在**自定义安装**BTAHL7 自定义安装中，选择屏幕**MLLP 测试工具**从**适配器**文件夹，并选择**测试实例**从**项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-106">At the **Custom Setup** screen of the BTAHL7 custom installation, select **MLLP Test Tool** from the **Adapter** folder, and select **Test Instances** from the **Artifacts** folder.</span></span> <span data-ttu-id="c1bd0-107">有关详细信息，请参阅[HL7 安装 BizTalk 快捷键](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-107">For more information, see [Install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="declarative-scenario"></a><span data-ttu-id="c1bd0-108">声明性方案</span><span class="sxs-lookup"><span data-stu-id="c1bd0-108">Declarative Scenario</span></span>  
 <span data-ttu-id="c1bd0-109">本教程使用的发布/订阅或声明性方案。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-109">This tutorial uses the publish/subscribe or declarative scenario.</span></span> <span data-ttu-id="c1bd0-110">在声明性的方案中，业务流程是类似于下图中所示。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-110">In the declarative scenario, the flow of business is similar to that shown in the following figure.</span></span> <span data-ttu-id="c1bd0-111">下图的编号的列表描述工作流。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-111">The numbered list following the figure describes the workflow.</span></span>  
  
 ![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-e2e-wkflw.gif "hl7_e2e_wkflw")  
<span data-ttu-id="c1bd0-112">该图显示的声明性方案的业务流程</span><span class="sxs-lookup"><span data-stu-id="c1bd0-112">Figure showing the flow of business for the declarative scenario</span></span>  
  
1.  <span data-ttu-id="c1bd0-113">当发布服务器，例如，许可放电并传输系统将一条消息发送到特定的订阅服务器时，将开始工作流。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-113">The workflow begins when the publisher, for example, an Admissions Discharge and Transfer system, sends a message to specific subscribers.</span></span> <span data-ttu-id="c1bd0-114">工作流中的发布服务器是"Tutorial_ADTSystem"，并且调用了消息"**ADT ^ A103**。"</span><span class="sxs-lookup"><span data-stu-id="c1bd0-114">The publisher in the workflow is "Tutorial_ADTSystem", and the message is called "**ADT^A103**."</span></span>  
  
2.  <span data-ttu-id="c1bd0-115">将消息路由到 BTAHL7 接口引擎，后者反过来接收、 处理、 验证、 重新格式化，并随后将消息路由到订阅服务器。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-115">The message is routed to the BTAHL7 Interface Engine, which in turn receives, processes, validates, reformats, and then routes the message to subscribers.</span></span>  
  
3.  <span data-ttu-id="c1bd0-116">在此方案中的订阅服务器是医院信息系统 (Tutorial_HISystem) 和药房系统 (Tutorial_RXSystem)。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-116">The subscribers in this scenario are a Hospital Information System (Tutorial_HISystem) and a Pharmacy System (Tutorial_RXSystem).</span></span> <span data-ttu-id="c1bd0-117">此方案使用文件和 MLLP 适配器类型。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-117">This scenario uses both File and MLLP adapter types.</span></span> <span data-ttu-id="c1bd0-118">发布服务器不需要注意的订阅服务器和 BTAHL7 处理消息之后中适当地将确认发送到发布服务器。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-118">The publisher does not need to be aware of the subscribers and BTAHL7 appropriately sends an acknowledgment to the publisher after processing the message.</span></span>  
  
4.  <span data-ttu-id="c1bd0-119">发布服务器发送 ADT ^ A03 消息通过单向 MLLP 适配器 (Tutorial_1WayReceivePort)。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-119">The publisher sends the ADT^A03 message through a one-way MLLP adapter (Tutorial_1WayReceivePort).</span></span>  
  
5.  <span data-ttu-id="c1bd0-120">此消息的目标是 BTAHL7 接口引擎，因此传入消息包含源消息 (MSH3 = Tutorial_ADTSystem) 和目标消息 (MSH5 = BTAHL7InterfaceEngine)。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-120">The destination of this message is the BTAHL7 Interface Engine, so the incoming message contains a source message (MSH3 = Tutorial_ADTSystem) and a destination message (MSH5 = BTAHL7InterfaceEngine).</span></span>  
  
6.  <span data-ttu-id="c1bd0-121">BTAHL7 在适当地验证消息之后, 生成的确认 (ACK)，并随后将确认发送到通过文件适配器 Tutorial_ADTSystem。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-121">BTAHL7 generates an acknowledgment (ACK) after appropriately validating the message, and then sends the acknowledgment to the Tutorial_ADTSystem through the File adapter.</span></span>  
  
7.  <span data-ttu-id="c1bd0-122">Tutorial_HISystem 系统和 Tutorial_RXSystem 系统订阅接收 BTAHL7 接口引擎的 ADT 消息。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-122">The Tutorial_HISystem system and the Tutorial_RXSystem system subscribe to the ADT message received by the BTAHL7 Interface Engine.</span></span>  
  
8.  <span data-ttu-id="c1bd0-123">使用指定的相应字段的值时发生转换**MSH 映射**BTAHL7 配置资源管理器中的选项卡。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-123">The transformation occurs when you specify values for the respective fields by using the **MSH Map** tab in BTAHL7 Configuration Explorer.</span></span>  
  
     <span data-ttu-id="c1bd0-124">例如，当事方 Tutorial_RXSystem 具有 MSH3 = 中指定的 BTHL7 **MSH 映射**选项卡。因此，通过将订阅者收到的消息将具有"BTAHL7"与 MSH3 字段的值。</span><span class="sxs-lookup"><span data-stu-id="c1bd0-124">For example, the party Tutorial_RXSystem has MSH3=BTHL7 specified in the **MSH Map** tab. Therefore, the message received by the subscriber will have "BTAHL7" as the value for the MSH3 field.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c1bd0-125">在本节中</span><span class="sxs-lookup"><span data-stu-id="c1bd0-125">In this section</span></span>  
  
-   [<span data-ttu-id="c1bd0-126">测试安装</span><span class="sxs-lookup"><span data-stu-id="c1bd0-126">Testing Your Installation</span></span>](../../adapters-and-accelerators/accelerator-hl7/testing-your-installation.md)  
  
-   [<span data-ttu-id="c1bd0-127">准备使用本教程</span><span class="sxs-lookup"><span data-stu-id="c1bd0-127">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial2.md)  
  
-   [<span data-ttu-id="c1bd0-128">步骤 1： 创建和部署标头和确认架构</span><span class="sxs-lookup"><span data-stu-id="c1bd0-128">Step 1: Create and Deploy Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="c1bd0-129">步骤 2： 创建常见 v2.3.1 架构</span><span class="sxs-lookup"><span data-stu-id="c1bd0-129">Step 2: Create Common Schemas for v2.3.1</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-3-1.md)  
  
-   [<span data-ttu-id="c1bd0-130">步骤 3： 创建和部署的触发器事件 （消息） 项目</span><span class="sxs-lookup"><span data-stu-id="c1bd0-130">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project.md)  
  
-   [<span data-ttu-id="c1bd0-131">步骤 4： 创建用于接受 ADT 接收端口 ^ A03 消息从 ADT 系统使用 MLLP 适配器</span><span class="sxs-lookup"><span data-stu-id="c1bd0-131">Step 4: Create the Receive Port for Accepting ADT^A03 Messages from ADT Systems Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-receive-port-to-accept-adt^a03-messages-from-adt-using-mllp.md)  
  
-   [<span data-ttu-id="c1bd0-132">步骤 5： 创建发送端口将确认传递到使用文件适配器的 ADT 系统</span><span class="sxs-lookup"><span data-stu-id="c1bd0-132">Step 5: Create a Send Port to Deliver Acknowledgments to the ADT System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-send-port-to-deliver-acknowledgments-to-adt-system-using-file.md)  
  
-   [<span data-ttu-id="c1bd0-133">步骤 6： 创建发送端口，以提供 ADT ^ 到 RX 系统使用了文件适配器 A03 消息</span><span class="sxs-lookup"><span data-stu-id="c1bd0-133">Step 6: Create a Send Port to Deliver the ADT^A03 Message to the RX System Using the File Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-send-port-to-deliver-adt^a03-message-to-rx-system-using-file.md)  
  
-   [<span data-ttu-id="c1bd0-134">步骤 7： 创建发送端口，以提供 ADT ^ 到他使用 MLLP 适配器 A03 消息</span><span class="sxs-lookup"><span data-stu-id="c1bd0-134">Step 7: Create a Send Port to Deliver the ADT^A03 Message to HIS Using the MLLP Adapter</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-send-port-to-deliver-adt^a03-message-to-his-using-mllp-adapter.md)  
  
-   [<span data-ttu-id="c1bd0-135">步骤 8： 配置当事方信息</span><span class="sxs-lookup"><span data-stu-id="c1bd0-135">Step 8: Configure Party Information</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information.md)  
  
-   [<span data-ttu-id="c1bd0-136">步骤 9： 重新启动 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="c1bd0-136">Step 9: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server.md)  
  
-   [<span data-ttu-id="c1bd0-137">步骤 10： 验证端到端方案</span><span class="sxs-lookup"><span data-stu-id="c1bd0-137">Step 10: Verify the End-to-End Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-end-to-end-scenario.md)

## <a name="see-also"></a><span data-ttu-id="c1bd0-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1bd0-138">See also</span></span>
[<span data-ttu-id="c1bd0-139">入门 HL7 BizTalk 快捷键</span><span class="sxs-lookup"><span data-stu-id="c1bd0-139">Get started with the BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)