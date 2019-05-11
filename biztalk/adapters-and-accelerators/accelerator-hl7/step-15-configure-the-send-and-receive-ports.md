---
title: 步骤 15:配置发送和接收端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message enrichment tutorial, ports
ms.assetid: d532b196-473e-4c8f-b4ed-acef674fc698
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: efb16b8222e3ef2c6afebe0aaf63a0e203afc73e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65289030"
---
# <a name="step-15-configure-the-send-and-receive-ports"></a><span data-ttu-id="6a6a8-102">步骤 15:配置发送和接收端口</span><span class="sxs-lookup"><span data-stu-id="6a6a8-102">Step 15: Configure the Send and Receive Ports</span></span>
<span data-ttu-id="6a6a8-103">在上一步骤中，创建逻辑发送和接收端口使用业务流程设计器并设置为"以后指定"端口绑定。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-103">In previous steps, you created a logical send and receive port using Orchestration Designer and set the port binding to "Specify Later".</span></span> <span data-ttu-id="6a6a8-104">在此步骤中，使用 BizTalk 浏览器通过定义物理源和目标位置，并将物理端口绑定到业务流程中创建的逻辑端口完成端口配置。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-104">In this step, you use BizTalk Explorer to finalize the port configuration by defining the physical source and destination locations and binding the physical ports to the logical ports that you created in the orchestration.</span></span>  
  
## <a name="configure-the-send-and-receive-ports"></a><span data-ttu-id="6a6a8-105">配置发送和接收端口</span><span class="sxs-lookup"><span data-stu-id="6a6a8-105">Configure the send and receive ports</span></span>  
  
1.  <span data-ttu-id="6a6a8-106">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开**BizTalk 应用程序 1**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-106">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand **BizTalk Application 1**.</span></span>  
  
2.  <span data-ttu-id="6a6a8-107">右键单击**发送端口**，指向新建，，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-107">Right-click **Send Ports**, point to New, and then click **Static One-way Send Port**.</span></span>  
  
3.  <span data-ttu-id="6a6a8-108">在发送端口属性对话框中，在**名称**框中，键入**MLLPSendPort**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-108">In the Send Port Properties dialog box, in the **Name** box, type **MLLPSendPort**.</span></span>  
  
4.  <span data-ttu-id="6a6a8-109">有关**类型**，选择**MLLP**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-109">For **Type**, select **MLLP**.</span></span>  
  
5.  <span data-ttu-id="6a6a8-110">单击**配置**右侧的按钮**类型**字段。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-110">Click the **Configure** button to the right of the **Type** field.</span></span>  
  
6.  <span data-ttu-id="6a6a8-111">在处的 MLLP 传输属性对话框中，对于**连接名称**输入**MLLPConnection**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-111">In the MLLP Transport Properties dialog box, for **Connection Name** enter **MLLPConnection**.</span></span> <span data-ttu-id="6a6a8-112">有关**主机**输入**localhost**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-112">For **Host** enter **localhost**.</span></span> <span data-ttu-id="6a6a8-113">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-113">Click **OK**.</span></span>  
  
7.  <span data-ttu-id="6a6a8-114">在发送端口属性对话框中，对于**发送管道**，选择**BTAHL72XPipelines.BTAHL72XSendPipeline**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-114">In the Send Port Properties dialog box, for **Send pipeline**, select **BTAHL72XPipelines.BTAHL72XSendPipeline**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="6a6a8-115">在管理控制台中，右键单击**MLLPSendPort**端口，，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-115">In the Administration Console, right-click **MLLPSendPort** port, and then click **Start**.</span></span>  
  
9. <span data-ttu-id="6a6a8-116">展开**平台设置**，单击**主机实例**，右键单击**BizTalkServerApplication**，然后单击**启动**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-116">Expand **Platform Settings**, click **Host Instances**, right-click **BizTalkServerApplication**, and then click **Start**.</span></span> <span data-ttu-id="6a6a8-117">如果主机已在运行，请单击**重新启动**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-117">If the host is already running, click **Restart**.</span></span>  
  
10. <span data-ttu-id="6a6a8-118">单击**业务流程**，右键单击**BTAHL7_Project.Doorbell_Orchestration**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-118">Click **Orchestrations**, right-click **BTAHL7_Project.Doorbell_Orchestration**, and then click **Properties**.</span></span>  
  
11. <span data-ttu-id="6a6a8-119">在业务流程属性对话框中，在控制台树中，单击**绑定**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-119">In the Orchestration Properties dialog box, in the console tree, click **Bindings**.</span></span>  
  
12. <span data-ttu-id="6a6a8-120">在中**绑定**窗格中，对于**主机**，选择**BizTalkServerApplication**。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-120">In the **Bindings** pane, for **Host**, select **BizTalkServerApplication**.</span></span>  
  
13. <span data-ttu-id="6a6a8-121">有关**SOAPReceivePort**，选择**WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort**中**接收端口**列。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-121">For **SOAPReceivePort**, select **WebPort_BTAHL7_Project_Proxy/BTAHL7_Project_Doorbell_Orchestration_SOAPReceivePort** in the **Receive Ports** column.</span></span>  
  
14. <span data-ttu-id="6a6a8-122">有关**MLLPSendPort**，选择**MLLPSendPort**中**发送端口/发送端口组**列。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-122">For **MLLPSendPort**, select **MLLPSendPort** in the **Send Ports/Send Port Groups** column.</span></span>  
  
15. <span data-ttu-id="6a6a8-123">单击**确定**以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-123">Click **OK** to save the changes.</span></span>  
  
## <a name="msh-5-and-msh-6"></a><span data-ttu-id="6a6a8-124">MSH 5 和 MSH 6</span><span class="sxs-lookup"><span data-stu-id="6a6a8-124">MSH 5 and MSH 6</span></span>  
 <span data-ttu-id="6a6a8-125">MSH 5 和 MSH 6 标头字段包含的目标应用程序和工具，分别。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-125">The MSH 5 and MSH 6 header fields contain the destination application and facility, respectively.</span></span> <span data-ttu-id="6a6a8-126">在配置资源管理器，可以为每个 MSH 5 和 MSH 6，在你想要更改的消息中的目标信息的情况下的三个组件指定值。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-126">In Configuration Explorer, you can specify the values for each of the three components of MSH 5 and MSH 6, in cases when you want the destination information in the message to be changed.</span></span> <span data-ttu-id="6a6a8-127">原始消息不包括特定于参与方信息时，这是可能的方案。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-127">This is a likely scenario when the original message does not include party-specific information.</span></span> <span data-ttu-id="6a6a8-128">此步骤是在声明性 （发布服务器/订阅服务器） 模型中适用。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-128">This step is applicable in the declarative (publisher/subscriber) model.</span></span> <span data-ttu-id="6a6a8-129">如果适用您的环境中，执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-129">You perform this step if it is applicable in your environment.</span></span> <span data-ttu-id="6a6a8-130">有关设置这些值的详细信息，请参阅[参与方-BTAHL7 配置资源管理器](parties-tab.md)。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-130">For more information about setting these values, see [Parties - BTAHL7 Configuration Explorer](parties-tab.md).</span></span>  
  
 <span data-ttu-id="6a6a8-131">请继续执行[步骤 16:启动业务流程](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md)。</span><span class="sxs-lookup"><span data-stu-id="6a6a8-131">Proceed to [Step 16: Start the Orchestration](../../adapters-and-accelerators/accelerator-hl7/step-16-start-the-orchestration.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a6a8-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="6a6a8-132">See Also</span></span>  
 [<span data-ttu-id="6a6a8-133">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="6a6a8-133">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)