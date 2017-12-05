---
title: "步骤 13： 创建并配置端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- ports, creating
- message enrichment tutorial, ports
- creating, ports
- configuring, ports
- ports, configuring
ms.assetid: cc0540d7-46fc-4d9f-bcf3-0b0e0179fd51
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c1b18e5b7addf1bae390dd541b84d17bd94023d
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
---
# <a name="step-13-create-and-configure-ports"></a><span data-ttu-id="a2fa3-102">步骤 13： 创建并配置端口</span><span class="sxs-lookup"><span data-stu-id="a2fa3-102">Step 13: Create and Configure Ports</span></span>
<span data-ttu-id="a2fa3-103">在此步骤中，你可以使用端口配置向导以创建和业务流程设计器中配置端口。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-103">In this step, you use the Port Configuration Wizard to create and configure ports in Orchestration Designer.</span></span> <span data-ttu-id="a2fa3-104">端口指定您的业务流程发送和接收消息与其他业务流程的方式。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-104">Ports specify how your orchestration sends and receives messages to and from business processes.</span></span> <span data-ttu-id="a2fa3-105">每个端口都具有类型、 方向和绑定。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-105">Each port has a type, a direction, and a binding.</span></span> <span data-ttu-id="a2fa3-106">属性共同决定通信、 通信模式、 位置到或从其方向[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]发送或接收的消息和如何进行通信。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-106">The properties together determine the direction of communication, the pattern of communication, the location to or from which [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] sends or receives the message, and how the communication takes place.</span></span> [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]<span data-ttu-id="a2fa3-107">使用作为发送端口的最小值较低层协议 (MLLP) 适配器。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-107"> uses the Minimum Lower Layer Protocol (MLLP) adapter as a send port.</span></span> <span data-ttu-id="a2fa3-108">MLLP 适配器将接口与其他应用程序，如实验室应用程序、 保险应用程序和旧的业务线应用程序中使用 TCP 套接字通信。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-108">The MLLP adapter uses TCP sockets communication to interface with other applications, such as laboratory applications, insurance applications, and legacy line-of-business applications.</span></span> <span data-ttu-id="a2fa3-109">MLLP 发送适配器表示[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]适配器：</span><span class="sxs-lookup"><span data-stu-id="a2fa3-109">The MLLP Send Adapter represents a [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adapter that is:</span></span>  
  
-   <span data-ttu-id="a2fa3-110">自定义。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-110">Customized.</span></span> <span data-ttu-id="a2fa3-111">适配器仅附带[!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)]，而不是与 BizTalk Server 传送。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-111">The adapter only ships with [!INCLUDE[HL7_CurrentVersion_abbrev](../../includes/hl7-currentversion-abbrev-md.md)], as opposed to shipping with BizTalk Server.</span></span>  
  
-   <span data-ttu-id="a2fa3-112">协议/传输。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-112">Protocol/Transport.</span></span> <span data-ttu-id="a2fa3-113">适配器不是应用程序或数据适配器。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-113">The adapter is not an application or data adapter.</span></span>  
  
-   <span data-ttu-id="a2fa3-114">静态。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-114">Static.</span></span> <span data-ttu-id="a2fa3-115">适配器配置不涉及自定义用户界面。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-115">The adapter configuration does not involve a custom user interface.</span></span>  
  
-   <span data-ttu-id="a2fa3-116">异步。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-116">Asynchronous.</span></span> <span data-ttu-id="a2fa3-117">适配器不会阻止消息引擎线程，从而使所有适配器的提高的性能，[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]主机。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-117">The adapter does not block the Messaging Engine thread, which enables increased performance of all adapters that [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] hosts.</span></span>  
  
-   <span data-ttu-id="a2fa3-118">Nontransacted。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-118">Nontransacted.</span></span> <span data-ttu-id="a2fa3-119">适配器不是事务处理的接收或发送[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]适配器。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-119">The adapter is not a transacted receive or send [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] adapter.</span></span>  
  
-   <span data-ttu-id="a2fa3-120">正则。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-120">Regular.</span></span> <span data-ttu-id="a2fa3-121">适配器不在单独的应用程序的进程中运行。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-121">The adapter does not run in a separate application process.</span></span>  
  
-   <span data-ttu-id="a2fa3-122">同时单向和双向。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-122">Both One-Way and Two-Way.</span></span> <span data-ttu-id="a2fa3-123">适配器支持交互的单向和请求-响应/请求-响应的模式。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-123">The adapter supports both One-way and Request-Response/Solicit-Response modes of interaction.</span></span>  
  
 <span data-ttu-id="a2fa3-124">MLLP 适配器可以提交单个消息，或提交批处理中的消息。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-124">The MLLP adapter can submit individual messages or submit messages in a batch.</span></span> <span data-ttu-id="a2fa3-125">MLLP 消息的开头标记使用包装的字符，十六进制 0x0b （也称为启动块或 SB 字符），并且消息的末尾是通过十六进制 0x1c 字符 （也称为结束块或 EB 字符） 的组合紧接着是 0x0d 字符 （回车）。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-125">The beginning of an MLLP message is marked with a wrapper character, hexadecimal 0x0b (also known as the Start Block or SB character), and the end of the message is marked by the combination of a hexadecimal 0x1c character (also known as the End Block or EB character) immediately followed by the 0x0d character (Carriage Return).</span></span> <span data-ttu-id="a2fa3-126">BTAHL7 性能计数器仅统计发送消息的这些包装器字符。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-126">BTAHL7 performance counters only count these wrapper characters for sent messages.</span></span> <span data-ttu-id="a2fa3-127">在接收消息时，BTAHL7 性能计数器进行计数这些包装器字符。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-127">BTAHL7 performance counters do not count these wrapper characters when receiving messages.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2fa3-128">标准的 MLLP 协议不消息有效负载中允许下 0x20 字符，因为它干扰检测 SB 和 EB 字符的能力。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-128">The MLLP protocol standard does not allow characters under 0x20 in the message payload because it interferes with the ability to detect the SB and EB characters.</span></span> <span data-ttu-id="a2fa3-129">你可以配置 SB 和 EB 的字符值，因此应谨慎此问题时进行更改。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-129">You can configure the SB and EB character values, so be wary of this issue when making changes.</span></span>  
  
 <span data-ttu-id="a2fa3-130">在此步骤中，你可以配置 MLLP 适配器和 SOAP 适配器。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-130">In this step, you configure the MLLP adapter and SOAP adapter.</span></span>  
  
### <a name="to-create-and-configure-the-ports"></a><span data-ttu-id="a2fa3-131">创建并配置端口</span><span class="sxs-lookup"><span data-stu-id="a2fa3-131">To create and configure the ports</span></span>  
  
1.  <span data-ttu-id="a2fa3-132">业务流程的设计器中拖动**端口**从工具箱调整到的设计视图图面，左侧端口面和删除形状，以便与水平对齐**DoorbellReceive**形状。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-132">In Orchestration Designer, drag the **Port** shape from the Toolbox to the Port Surface on the left side of the Design view surface, and drop the shape so that it aligns horizontally with the **DoorbellReceive** shape.</span></span>  
  
2.  <span data-ttu-id="a2fa3-133">在**端口配置向导**，单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-133">In the **Port Configuration Wizard**, click **Next**.</span></span>  
  
3.  <span data-ttu-id="a2fa3-134">上**端口属性**页上，在**名称**字段中，键入**SOAPReceivePort**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-134">On the **Port Properties** page, in the **Name** field, type **SOAPReceivePort**, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="a2fa3-135">上**选择端口类型**页上，输入以下信息，，然后单击**下一步**以继续。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-135">On the **Select a Port Type** page, enter the following information, and then click **Next** to continue.</span></span>  
  
    |<span data-ttu-id="a2fa3-136">使用此选项</span><span class="sxs-lookup"><span data-stu-id="a2fa3-136">Use this</span></span>|<span data-ttu-id="a2fa3-137">执行的操作</span><span class="sxs-lookup"><span data-stu-id="a2fa3-137">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="a2fa3-138">**端口类型名称**</span><span class="sxs-lookup"><span data-stu-id="a2fa3-138">**Port Type Name**</span></span>|<span data-ttu-id="a2fa3-139">类型**SOAPReceivePortType**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-139">Type **SOAPReceivePortType**.</span></span>|  
    |<span data-ttu-id="a2fa3-140">**通信模式**</span><span class="sxs-lookup"><span data-stu-id="a2fa3-140">**Communication Pattern**</span></span>|<span data-ttu-id="a2fa3-141">选择**单向**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-141">Select **One-Way**.</span></span>|  
    |<span data-ttu-id="a2fa3-142">**访问限制**</span><span class="sxs-lookup"><span data-stu-id="a2fa3-142">**Access Restrictions**</span></span>|<span data-ttu-id="a2fa3-143">选择**公有-无限制**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-143">Select **Public - no limit**.</span></span>|  
  
5.  <span data-ttu-id="a2fa3-144">上**端口绑定**页上，单击**下一步**以接受默认值。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-144">On the **Port Binding** page, click **Next** to accept the default values.</span></span>  
  
6.  <span data-ttu-id="a2fa3-145">上**完成端口向导**页上，单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-145">On the **Completing the Port Wizard** page, click **Finish**.</span></span>  
  
7.  <span data-ttu-id="a2fa3-146">拖动**端口**从工具箱调整到的设计视图图面，右侧端口面和删除形状，以便与水平对齐**DoorbellSend**形状。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-146">Drag the **Port** shape from the Toolbox to the Port Surface on the right side of the Design view surface, and drop the shape so that it aligns horizontally with the **DoorbellSend** shape.</span></span>  
  
8.  <span data-ttu-id="a2fa3-147">使用**端口配置向导**按步骤 2 至 7 中，创建使用以下参数的其他发送端口：</span><span class="sxs-lookup"><span data-stu-id="a2fa3-147">Using the **Port Configuration Wizard** as you did in steps 2 through 7, create an additional send port using the following parameters:</span></span>  
  
    |<span data-ttu-id="a2fa3-148">属性</span><span class="sxs-lookup"><span data-stu-id="a2fa3-148">Property</span></span>|<span data-ttu-id="a2fa3-149">参数</span><span class="sxs-lookup"><span data-stu-id="a2fa3-149">Parameter</span></span>|  
    |--------------|---------------|  
    |<span data-ttu-id="a2fa3-150">**端口属性名称**</span><span class="sxs-lookup"><span data-stu-id="a2fa3-150">**Port Properties Name**</span></span>|<span data-ttu-id="a2fa3-151">MLLPSendPort</span><span class="sxs-lookup"><span data-stu-id="a2fa3-151">MLLPSendPort</span></span>|  
    |<span data-ttu-id="a2fa3-152">**端口类型名称**</span><span class="sxs-lookup"><span data-stu-id="a2fa3-152">**Port Type Name**</span></span>|<span data-ttu-id="a2fa3-153">MLLPSendPortType</span><span class="sxs-lookup"><span data-stu-id="a2fa3-153">MLLPSendPortType</span></span>|  
    |<span data-ttu-id="a2fa3-154">**通信模式**</span><span class="sxs-lookup"><span data-stu-id="a2fa3-154">**Communication Pattern**</span></span>|<span data-ttu-id="a2fa3-155">单向</span><span class="sxs-lookup"><span data-stu-id="a2fa3-155">One-Way</span></span>|  
    |<span data-ttu-id="a2fa3-156">**访问限制**</span><span class="sxs-lookup"><span data-stu-id="a2fa3-156">**Access Restrictions**</span></span>|<span data-ttu-id="a2fa3-157">公有 - 无限制</span><span class="sxs-lookup"><span data-stu-id="a2fa3-157">Public - no limit</span></span>|  
    |<span data-ttu-id="a2fa3-158">**端口绑定**</span><span class="sxs-lookup"><span data-stu-id="a2fa3-158">**Port Binding**</span></span>|<span data-ttu-id="a2fa3-159">以后指定</span><span class="sxs-lookup"><span data-stu-id="a2fa3-159">Specify Later</span></span>|  
    |<span data-ttu-id="a2fa3-160">**端口通信方向**</span><span class="sxs-lookup"><span data-stu-id="a2fa3-160">**Port direction of communication**</span></span>|<span data-ttu-id="a2fa3-161">始终在此端口上发送消息。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-161">I'll always be sending messages on this port.</span></span>|  
  
9. <span data-ttu-id="a2fa3-162">在**业务流程视图**窗口中，与**类型**，**端口类型**，和**SOAPReceivePortType**节点已展开，展开**Operation_1**，然后单击**请求**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-162">In the **Orchestration View** window, with the **Types**, **Ports Types**, and **SOAPReceivePortType** nodes expanded, expand **Operation_1**, and then click **Request**.</span></span>  
  
10. <span data-ttu-id="a2fa3-163">在**属性**窗口中的下拉列表**消息类型**，展开**架构**，然后单击**BTAHL7_Project.Doorbell**.</span><span class="sxs-lookup"><span data-stu-id="a2fa3-163">In the **Properties** window, in the drop-down list for **Message Type**, expand **Schemas**, and then click **BTAHL7_Project.Doorbell**.</span></span>  
  
11. <span data-ttu-id="a2fa3-164">在**业务流程视图**窗口中，展开**MLLPSendPortType**，展开**Operation_1**，然后单击**请求**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-164">In the **Orchestration View** window, expand **MLLPSendPortType**, expand **Operation_1**, and then click **Request**.</span></span>  
  
12. <span data-ttu-id="a2fa3-165">在**属性**窗口中的下拉列表**消息类型**，展开**多部分消息类型**，然后单击**BTAHL7_Project.DoorbellFinalMessageType**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-165">In the **Properties** window, in the drop-down list for **Message Type**, expand **Multi-part Message Types**, and then click **BTAHL7_Project.DoorbellFinalMessageType**.</span></span>  
  
13. <span data-ttu-id="a2fa3-166">在**名称**字段中，键入**响应**，然后按**Enter**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-166">In the **Name** field, type **Response**, then press **Enter**.</span></span>  
  
14. <span data-ttu-id="a2fa3-167">在业务流程设计视图图面中，单击**DoorbellReceive**操作形状。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-167">On the orchestration Design view surface, click the **DoorbellReceive** action shape.</span></span>  
  
15. <span data-ttu-id="a2fa3-168">在**属性**窗口中的下拉列表**消息**，选择**DoorbellInputMessage**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-168">In the **Properties** window, in the drop-down list for **Message**, select **DoorbellInputMessage**.</span></span>  
  
16. <span data-ttu-id="a2fa3-169">在业务流程设计视图图面中，单击**DoorbellSend**形状。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-169">On the orchestration Design view surface, click the **DoorbellSend** shape.</span></span>  
  
17. <span data-ttu-id="a2fa3-170">在**属性**窗口中的下拉列表**消息**，选择**DoorbellFinalMessage**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-170">In the **Properties** window, in the drop-down list for **Message**, select **DoorbellFinalMessage**.</span></span>  
  
18. <span data-ttu-id="a2fa3-171">单击绿色的句柄以**SOAPReceivePort**并将其拖到绿色句柄**DoorbellReceive**接收形状连接**SOAPReceivePort**到**DoorbellReceive**接收形状。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-171">Click the green handle in the **SOAPReceivePort** and drag it to the green handle on the **DoorbellReceive** receive shape to connect the **SOAPReceivePort** to the **DoorbellReceive** receive shape.</span></span>  
  
19. <span data-ttu-id="a2fa3-172">单击绿色的句柄以**DoorbellSend**形状并将其拖到绿色句柄**MLLPSendPort**端口以连接**DoorbellSend**将形状发送到**MLLPSendPort**端口。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-172">Click the green handle in the **DoorbellSend** shape and drag it to the green handle on the **MLLPSendPort** port to connect the **DoorbellSend** send shape to the **MLLPSendPort** port.</span></span>  
  
20. <span data-ttu-id="a2fa3-173">单击**解决方案资源管理器**Orchestration 视图下的选项卡。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-173">Click the **Solution Explorer** tab under the Orchestration View.</span></span>  
  
21. <span data-ttu-id="a2fa3-174">在解决方案资源管理器，右键单击**BTAHL7V22Common**，然后单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-174">In Solution Explorer, right-click **BTAHL7V22Common**, and then click **Build**.</span></span> <span data-ttu-id="a2fa3-175">确保在输出窗口中显示一条成功消息。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-175">Ensure that a success message appears in the output window.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a2fa3-176">如果不显示任何成功消息，对解决方案进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-176">If no success message appears, troubleshoot the solution.</span></span>  
  
22. <span data-ttu-id="a2fa3-177">右键单击**BTAHL7 项目**，然后单击**部署**部署 BTAHL7 项目。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-177">Right-click **BTAHL7 Project**, and click **Deploy** to deploy the BTAHL7 project.</span></span>  
  
 <span data-ttu-id="a2fa3-178">继续执行[步骤 14： 发布作为 Web 服务业务流程](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md)。</span><span class="sxs-lookup"><span data-stu-id="a2fa3-178">Proceed to [Step 14: Publish the Orchestration as a Web Service](../../adapters-and-accelerators/accelerator-hl7/step-14-publish-the-orchestration-as-a-web-service.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2fa3-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2fa3-179">See Also</span></span>  
 [<span data-ttu-id="a2fa3-180">消息充实教程</span><span class="sxs-lookup"><span data-stu-id="a2fa3-180">Message Enrichment Tutorial</span></span>](../../adapters-and-accelerators/accelerator-hl7/message-enrichment-tutorial.md)