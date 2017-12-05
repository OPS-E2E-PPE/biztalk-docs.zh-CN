---
title: "Interrogative 教程 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- interrogative tutorial
- interrogative tutorial, about the tutorial
- tutorials, interrogative tutorial
ms.assetid: 93988429-5544-4920-821f-54f0a67bda72
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 642f2521917dd87b60ee43a4cd7decaeeb1f1365
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="interrogative-tutorial"></a><span data-ttu-id="00223-102">Interrogative 教程</span><span class="sxs-lookup"><span data-stu-id="00223-102">Interrogative Tutorial</span></span>
<span data-ttu-id="00223-103">本教程包含的详细的步骤，描述如何使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]以便在查询/响应方案中的业务流程。</span><span class="sxs-lookup"><span data-stu-id="00223-103">This tutorial contains detailed steps that describe how you use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] to facilitate business processes in a Query/Response scenario.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="00223-104">若要使用本教程，你必须安装 MLLP 测试工具。</span><span class="sxs-lookup"><span data-stu-id="00223-104">To use this tutorial, you must install the MLLP test tools.</span></span> <span data-ttu-id="00223-105">通过 BTAHL7 的典型安装未安装这些工具。</span><span class="sxs-lookup"><span data-stu-id="00223-105">These tools are not installed by a Typical installation of BTAHL7.</span></span> <span data-ttu-id="00223-106">你必须运行自定义安装，并选择**MLLP 测试工具**从适配器文件夹和**测试实例**项目文件夹中。</span><span class="sxs-lookup"><span data-stu-id="00223-106">You must run a Custom installation and select **MLLP Test Tool** from the Adapter folder and **Test Instances** from the Artifacts folder.</span></span> <span data-ttu-id="00223-107">如果安装的测试工具，你的系统将包含文件夹\<*驱动器*:\>files\microsoft BizTalk\<版本\>Accelerator for HL7\SDK\MLLP 实用程序。</span><span class="sxs-lookup"><span data-stu-id="00223-107">If the test tools are installed, your system will contain the folder \<*drive*:\>\Program Files\Microsoft BizTalk \<version\> Accelerator for HL7\SDK\MLLP Utilities.</span></span> <span data-ttu-id="00223-108">请参阅[为 HL7 安装 BizTalk Accelerator](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md)。</span><span class="sxs-lookup"><span data-stu-id="00223-108">See [install BizTalk Accelerator for HL7](../../adapters-and-accelerators/accelerator-hl7/install-biztalk-accelerator-for-hl7.md).</span></span>  
  
## <a name="interrogative-scenario"></a><span data-ttu-id="00223-109">Interrogative 方案</span><span class="sxs-lookup"><span data-stu-id="00223-109">Interrogative Scenario</span></span>  
 <span data-ttu-id="00223-110">本教程使用的查询/响应或 Interrogative 方案。</span><span class="sxs-lookup"><span data-stu-id="00223-110">This tutorial uses the Query/Response or Interrogative scenario.</span></span> <span data-ttu-id="00223-111">在此方案中，业务流程是类似于下图中所示。</span><span class="sxs-lookup"><span data-stu-id="00223-111">In this scenario, the flow of business is similar to that shown in the following figure.</span></span> <span data-ttu-id="00223-112">下图的编号的列表描述工作流。</span><span class="sxs-lookup"><span data-stu-id="00223-112">The numbered list following the figure describes the workflow.</span></span>  
  
 <span data-ttu-id="00223-113">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-intertutorial.gif "hl7_intertutorial")</span><span class="sxs-lookup"><span data-stu-id="00223-113">![](../../adapters-and-accelerators/accelerator-hl7/media/hl7-intertutorial.gif "hl7_intertutorial")</span></span>  
  
1.  <span data-ttu-id="00223-114">工作流开始时许可放电并传输 (ADT) 的系统将查询发送到医院信息系统。</span><span class="sxs-lookup"><span data-stu-id="00223-114">The workflow begins when an Admissions Discharge and Transfer (ADT) system sends a query to the Hospital Information System.</span></span> <span data-ttu-id="00223-115">HL7 消息使用"**QRY ^ Q01**"架构。</span><span class="sxs-lookup"><span data-stu-id="00223-115">The HL7 message uses the "**QRY^Q01**" schema.</span></span> <span data-ttu-id="00223-116">在本教程，MllpSend 实用工具模拟 ADT 查询将消息发送到通过 ADT 医院信息系统的系统接收 BTAHL7 集成引擎中的端口。</span><span class="sxs-lookup"><span data-stu-id="00223-116">In the tutorial, the MllpSend utility simulates the ADT system sending the query message to the Hospital Information System through the ADT receive port in the BTAHL7 Integration Engine.</span></span>  
  
2.  <span data-ttu-id="00223-117">BTAHL7 集成引擎从 ADT 系统接收查询消息，并对它进行验证。</span><span class="sxs-lookup"><span data-stu-id="00223-117">The BTAHL7 Integration Engine receives the query message from the ADT system and validates it.</span></span> <span data-ttu-id="00223-118">然后，BTAHL7 管道将确认发送回 ADT。</span><span class="sxs-lookup"><span data-stu-id="00223-118">Then, the BTAHL7 pipeline sends an acknowledgment back to ADT.</span></span>  
  
3.  <span data-ttu-id="00223-119">BTAHL7 接口引擎处理消息，然后再路由到 HIS 目标查询消息方通过 HIS 发送端口。</span><span class="sxs-lookup"><span data-stu-id="00223-119">The BTAHL7 Interface Engine processes the message, and then routes the query message to the HIS destination party through the HIS send port.</span></span>  
  
4.  <span data-ttu-id="00223-120">在从原始查询接收该确认后, ADT 系统等待响应。</span><span class="sxs-lookup"><span data-stu-id="00223-120">After receiving the acknowledgment from the original query, the ADT system waits for a response.</span></span> <span data-ttu-id="00223-121">响应消息通过 HIS 回来医院信息系统发送接收端口。</span><span class="sxs-lookup"><span data-stu-id="00223-121">The Hospital Information System sends a response message back through the HIS receive port.</span></span> <span data-ttu-id="00223-122">对于本教程，MllpSend 实用工具模拟医院信息系统发送响应消息。</span><span class="sxs-lookup"><span data-stu-id="00223-122">For this tutorial, the MllpSend utility simulates the Hospital Information System sending the response message.</span></span>  
  
5.  <span data-ttu-id="00223-123">BTAHL7 接口引擎处理响应消息，并随后将它路由到通过 ADT 发送端口目标参与方。</span><span class="sxs-lookup"><span data-stu-id="00223-123">The BTAHL7 Interface Engine processes the response message and then routes it to the destination party through the ADT send port.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="00223-124">在本节中</span><span class="sxs-lookup"><span data-stu-id="00223-124">In this section</span></span>  
  
-   [<span data-ttu-id="00223-125">为使用教程做准备</span><span class="sxs-lookup"><span data-stu-id="00223-125">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)  
  
-   [<span data-ttu-id="00223-126">步骤 1：创建和部署通用标头及确认架构</span><span class="sxs-lookup"><span data-stu-id="00223-126">Step 1: Create and Deploy Common Header and Acknowledgment Schemas</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-1-create-and-deploy-common-header-and-acknowledgment-schemas.md)  
  
-   [<span data-ttu-id="00223-127">步骤 2：创建适用于 V2.4 的通用架构</span><span class="sxs-lookup"><span data-stu-id="00223-127">Step 2: Create Common Schemas for V2.4</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-2-create-common-schemas-for-v2-4.md)  
  
-   [<span data-ttu-id="00223-128">步骤 3：创建和部署触发器事件（消息）项目</span><span class="sxs-lookup"><span data-stu-id="00223-128">Step 3: Create and Deploy a Trigger Event (Message) Project</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-3-create-and-deploy-a-trigger-event-message-project-hl7-main.md)  
  
-   [<span data-ttu-id="00223-129">步骤 4：创建用于接收 ADT 查询消息的接收端口</span><span class="sxs-lookup"><span data-stu-id="00223-129">Step 4: Create the Receive Port for Accepting ADT Query Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-4-create-the-receive-port-for-accepting-adt-query-messages.md)  
  
-   [<span data-ttu-id="00223-130">步骤 5：创建用于接收 HIS 消息的接收端口</span><span class="sxs-lookup"><span data-stu-id="00223-130">Step 5: Create the Receive Port for Accepting HIS Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-5-create-the-receive-port-for-accepting-his-messages.md)  
  
-   [<span data-ttu-id="00223-131">步骤 6：创建用于传递查询消息的发送端口</span><span class="sxs-lookup"><span data-stu-id="00223-131">Step 6: Create a Send Port to Deliver Query Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-6-create-a-send-port-to-deliver-query-messages.md)  
  
-   [<span data-ttu-id="00223-132">步骤 7：创建用于传递响应消息的发送端口</span><span class="sxs-lookup"><span data-stu-id="00223-132">Step 7: Create a Send Port to Deliver Response Messages</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-7-create-a-send-port-to-deliver-response-messages.md)  
  
-   [<span data-ttu-id="00223-133">步骤 8：配置参与方信息</span><span class="sxs-lookup"><span data-stu-id="00223-133">Step 8: Configure Party Information</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-8-configure-party-information-hl7-main.md)  
  
-   [<span data-ttu-id="00223-134">步骤 9：重启 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="00223-134">Step 9: Restart BizTalk Server</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-9-restart-biztalk-server-hl7-main.md)  
  
-   [<span data-ttu-id="00223-135">步骤 10：验证询问方案</span><span class="sxs-lookup"><span data-stu-id="00223-135">Step 10: Verify the Interrogative Scenario</span></span>](../../adapters-and-accelerators/accelerator-hl7/step-10-verify-the-interrogative-scenario.md)  

## <a name="next-step"></a><span data-ttu-id="00223-136">下一步</span><span class="sxs-lookup"><span data-stu-id="00223-136">Next step</span></span>  
 [<span data-ttu-id="00223-137">为使用教程做准备</span><span class="sxs-lookup"><span data-stu-id="00223-137">Preparing to Use the Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/preparing-to-use-the-tutorial-hl7-main.md)
  
## <a name="see-also"></a><span data-ttu-id="00223-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00223-138">See Also</span></span>  
[<span data-ttu-id="00223-139">BizTalk Accelerator for HL7 入门</span><span class="sxs-lookup"><span data-stu-id="00223-139">Get started with the BizTalk Accelerator for HL7</span></span>](../../adapters-and-accelerators/accelerator-hl7/get-started-with-the-biztalk-accelerator-for-hl7.md)