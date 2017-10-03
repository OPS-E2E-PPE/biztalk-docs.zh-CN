---
title: "如何运行端口配置向导 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Port Configuration Wizard [Orchestration Designer], starting
- Port Configuration Wizard [Orchestration Designer], how to
- Port Configuration Wizard [Orchestration Designer], about Port Configuration Wizard
- ports, Port Configuration Wizard [Orchestration Designer]
- Port Configuration Wizard [Orchestration Designer]
ms.assetid: 8035ce32-5ed4-49cb-b6f0-998b0460751e
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bbdb5843eb8011478f13c0de6443bb1ded177378
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-run-the-port-configuration-wizard"></a><span data-ttu-id="0d872-102">如何运行端口配置向导</span><span class="sxs-lookup"><span data-stu-id="0d872-102">How to Run the Port Configuration Wizard</span></span>
<span data-ttu-id="0d872-103">您可以使用端口配置向导在业务流程设计器中创建和配置端口。</span><span class="sxs-lookup"><span data-stu-id="0d872-103">You use the Port Configuration Wizard to create and configure a port in Orchestration Designer.</span></span> <span data-ttu-id="0d872-104">端口必须具有与之关联的端口类型，您可以使用该向导来选择现有的端口类型或创建新的端口类型。</span><span class="sxs-lookup"><span data-stu-id="0d872-104">A port must have a port type associated with it, and you use the wizard to select an existing port type or to create a new port type.</span></span> <span data-ttu-id="0d872-105">有关端口和端口类型的详细信息，请参阅[在业务流程中使用端口](../core/using-ports-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="0d872-105">For more information about ports and port types, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
### <a name="to-start-the-wizard"></a><span data-ttu-id="0d872-106">若要启动向导</span><span class="sxs-lookup"><span data-stu-id="0d872-106">To Start the wizard</span></span>  
  
1.  <span data-ttu-id="0d872-107">右键单击一个端口 （设计图面上或业务流程视图窗口中），单击**配置端口**。</span><span class="sxs-lookup"><span data-stu-id="0d872-107">Right-clicking a port (on the design surface or in the Orchestration View window) and clicking **Configure Port**.</span></span>  
  
2.  <span data-ttu-id="0d872-108">运行其关联操作会导致创建端口的智能标记项。</span><span class="sxs-lookup"><span data-stu-id="0d872-108">Running Smart Tag items whose associated actions cause a port to be created.</span></span>  
  
3.  <span data-ttu-id="0d872-109">选择**新配置端口参数**Orchestration 视图窗口中的业务流程参数文件夹的快捷菜单命令。</span><span class="sxs-lookup"><span data-stu-id="0d872-109">Selecting the **New Configured Port Parameter** command from the shortcut menu of the Orchestration Parameters folder in the Orchestration View window.</span></span>  
  
### <a name="to-run-the-wizard"></a><span data-ttu-id="0d872-110">若要运行向导</span><span class="sxs-lookup"><span data-stu-id="0d872-110">To Run the Wizard</span></span>  
  
1.  <span data-ttu-id="0d872-111">打开端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="0d872-111">Open the Port Configuration Wizard.</span></span>  
  
2.  <span data-ttu-id="0d872-112">指定端口信息。</span><span class="sxs-lookup"><span data-stu-id="0d872-112">Specify port information.</span></span> <span data-ttu-id="0d872-113">向导将显示若干页以协助您执行操作。</span><span class="sxs-lookup"><span data-stu-id="0d872-113">To help you, the wizard displays several pages.</span></span> <span data-ttu-id="0d872-114">完成每个页后，将其迁移到以下通过单击**下一步**，或将移动到前一次通过单击**回**。</span><span class="sxs-lookup"><span data-stu-id="0d872-114">After completing each page, move to the following one by clicking **Next**, or move to the preceding one by clicking **Back**.</span></span>  
  
    -   <span data-ttu-id="0d872-115">**端口属性**。</span><span class="sxs-lookup"><span data-stu-id="0d872-115">**Port Properties**.</span></span> <span data-ttu-id="0d872-116">为端口键入名称。</span><span class="sxs-lookup"><span data-stu-id="0d872-116">Type in a name for the port.</span></span>  
  
    -   <span data-ttu-id="0d872-117">**选择端口类型。**</span><span class="sxs-lookup"><span data-stu-id="0d872-117">**Select a Port Type.**</span></span> <span data-ttu-id="0d872-118">在此页上，你首先选择你是否想**新端口类型**或**现有端口类型**。</span><span class="sxs-lookup"><span data-stu-id="0d872-118">On this page, you first select whether you want a **New Port Type** or an **Existing Port Type**.</span></span> <span data-ttu-id="0d872-119">如果你选择**现有端口类型**，然后使用树控件选择要分配的现有端口类型。</span><span class="sxs-lookup"><span data-stu-id="0d872-119">If you select **Existing Port Type**, you then use a tree control to choose which existing port type to assign.</span></span>  
  
         <span data-ttu-id="0d872-120">如果你选择**新端口类型**，然后需要键入的名称中的端口类型**名称**文本框中，或接受建议的默认名称。</span><span class="sxs-lookup"><span data-stu-id="0d872-120">If you select **New Port Type**, you then need to type the name of the port type in the **Name** text box, or accept the suggested default name.</span></span> <span data-ttu-id="0d872-121">还需要选择端口类型的通信模式（单向或请求响应）以及针对新端口类型的任何访问限制。</span><span class="sxs-lookup"><span data-stu-id="0d872-121">You also select the port type's communication pattern (one-way or request-response) and any access restrictions to impose on the new port type.</span></span>  
  
    -   <span data-ttu-id="0d872-122">**端口绑定**。</span><span class="sxs-lookup"><span data-stu-id="0d872-122">**Port Binding**.</span></span> <span data-ttu-id="0d872-123">此页上你指定的方向的通信，也称为*极性*，和端口的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="0d872-123">On this page you specify the direction of communication, also known as the *polarity*, and the binding type of the port.</span></span>  
  
         <span data-ttu-id="0d872-124">你所做的极性选择部分取决于你在向导的上一页中选择的端口类型的通信模式**选择端口类型**。</span><span class="sxs-lookup"><span data-stu-id="0d872-124">The polarity choice you make depends in part on the communication pattern of the port type that you selected on the preceding page of the wizard, **Select a Port Type**.</span></span> <span data-ttu-id="0d872-125">下表对这些选项进行了概括介绍：</span><span class="sxs-lookup"><span data-stu-id="0d872-125">Your choices are summarized in the following table:</span></span>  
  
        |<span data-ttu-id="0d872-126">端口方向</span><span class="sxs-lookup"><span data-stu-id="0d872-126">Port direction</span></span>|<span data-ttu-id="0d872-127">通信模式</span><span class="sxs-lookup"><span data-stu-id="0d872-127">Communication pattern</span></span>|<span data-ttu-id="0d872-128">要在“端口绑定”页上选择的通信方向</span><span class="sxs-lookup"><span data-stu-id="0d872-128">Direction of communication to choose on Port Binding page</span></span>|  
        |--------------------|---------------------------|---------------------------------------------------------------|  
        |<span data-ttu-id="0d872-129">Send</span><span class="sxs-lookup"><span data-stu-id="0d872-129">Send</span></span>|<span data-ttu-id="0d872-130">单向</span><span class="sxs-lookup"><span data-stu-id="0d872-130">One-way</span></span>|<span data-ttu-id="0d872-131">我将始终发送消息上此端口。</span><span class="sxs-lookup"><span data-stu-id="0d872-131">I will always be sending messages on this port.</span></span>|  
        |<span data-ttu-id="0d872-132">Receive</span><span class="sxs-lookup"><span data-stu-id="0d872-132">Receive</span></span>|<span data-ttu-id="0d872-133">单向</span><span class="sxs-lookup"><span data-stu-id="0d872-133">One-way</span></span>|<span data-ttu-id="0d872-134">始终在此端口上接收消息。</span><span class="sxs-lookup"><span data-stu-id="0d872-134">I will always be receiving messages on this port.</span></span>|  
        |<span data-ttu-id="0d872-135">发送-接收</span><span class="sxs-lookup"><span data-stu-id="0d872-135">Send-Receive</span></span>|<span data-ttu-id="0d872-136">请求作出响应</span><span class="sxs-lookup"><span data-stu-id="0d872-136">Solicit-response</span></span>|<span data-ttu-id="0d872-137">我将发送请求并接收响应。</span><span class="sxs-lookup"><span data-stu-id="0d872-137">I will be sending a request and receiving a response.</span></span>|  
        |<span data-ttu-id="0d872-138">接收-发送</span><span class="sxs-lookup"><span data-stu-id="0d872-138">Receive-Send</span></span>|<span data-ttu-id="0d872-139">请求-响应</span><span class="sxs-lookup"><span data-stu-id="0d872-139">Request-response</span></span>|<span data-ttu-id="0d872-140">我将接收请求并发送响应。</span><span class="sxs-lookup"><span data-stu-id="0d872-140">I will be receiving a request and sending a response.</span></span>|  
  
         <span data-ttu-id="0d872-141">您可以从四种不同的绑定类型中选择：“以后指定”、“立即指定”、“动态”和“直接”。</span><span class="sxs-lookup"><span data-stu-id="0d872-141">You have a choice of four different binding types: Specify later, Specify now, Dynamic, and Direct.</span></span> <span data-ttu-id="0d872-142">每个选项显示一组不同的配置选项，如下所述：</span><span class="sxs-lookup"><span data-stu-id="0d872-142">Each choice displays a different set of configuration options, as summarized here:</span></span>  
  
         <span data-ttu-id="0d872-143">**指定更高版本。**</span><span class="sxs-lookup"><span data-stu-id="0d872-143">**Specify later.**</span></span> <span data-ttu-id="0d872-144">在选择此选项之后，在本向导中将不用再选择配置，因为绑定信息不是在设计时确定的。</span><span class="sxs-lookup"><span data-stu-id="0d872-144">After selecting this option, you make no further configuration choices in the wizard because binding information is not determined at design time.</span></span> <span data-ttu-id="0d872-145">通常，它由管理员在部署时添加。</span><span class="sxs-lookup"><span data-stu-id="0d872-145">Typically it is added by an Administrator at deployment time.</span></span>  
  
         <span data-ttu-id="0d872-146">**指定现在。**</span><span class="sxs-lookup"><span data-stu-id="0d872-146">**Specify now.**</span></span> <span data-ttu-id="0d872-147">您可以在设计时指定一个 URI，该 URI 将定义该端口要绑定到的实体。</span><span class="sxs-lookup"><span data-stu-id="0d872-147">You can specify at design time a URI that defines the entity to which the port is to be bound.</span></span> <span data-ttu-id="0d872-148">您还需要从传输类型（包括 BizTalk 消息队列、FILE、SMTP、HTTP 和 SOAP）列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="0d872-148">You also need to select from a list of transport types that includes BizTalk Message Queuing, FILE, SMTP, HTTP, and SOAP.</span></span> <span data-ttu-id="0d872-149">此列表是用于业务流程设计器中的早期绑定的硬编码列表；因此，其他传输类型不包含在此列表中。</span><span class="sxs-lookup"><span data-stu-id="0d872-149">This is a hard-coded list for the purpose of early binding in Orchestration Designer; therefore, other transports are not available in this list.</span></span> <span data-ttu-id="0d872-150">最后，从可用管道列表中选择接收管道和发送管道。</span><span class="sxs-lookup"><span data-stu-id="0d872-150">Finally, you select a receive pipeline and a send pipeline from a list of available pipelines.</span></span> <span data-ttu-id="0d872-151">每个列表中当前的项目以及从引用的程序集，其中显示了选择管道的选项包括所有管道**选择项目类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="0d872-151">The list for each includes all pipelines in the current project plus the option of selecting a pipeline from a referenced assembly, which displays the **Select Artifact Type** dialog box.</span></span>  
  
         <span data-ttu-id="0d872-152">**动态。**</span><span class="sxs-lookup"><span data-stu-id="0d872-152">**Dynamic.**</span></span> <span data-ttu-id="0d872-153">此选项具有类似于选择**现在指定**，但它是仅适用于发送端口。</span><span class="sxs-lookup"><span data-stu-id="0d872-153">This option has similar choices to **Specify now**, but it is available only for a send port.</span></span> <span data-ttu-id="0d872-154">您可以指定要使用的发送管道。</span><span class="sxs-lookup"><span data-stu-id="0d872-154">You can specify a send pipeline to use.</span></span> <span data-ttu-id="0d872-155">你可以指定在单独的端口**表达式**调整，以便在运行时分配。</span><span class="sxs-lookup"><span data-stu-id="0d872-155">You can specify the port separately in an **Expression** shape so that it is assigned at run time.</span></span>  
  
         <span data-ttu-id="0d872-156">**直接。**</span><span class="sxs-lookup"><span data-stu-id="0d872-156">**Direct.**</span></span> <span data-ttu-id="0d872-157">对于直接绑定，您可以选择要连接到的端口、要基于筛选器表达式对 MessageBox 数据库中的传入消息进行路由的端口，或者要成为自相关端口的端口。</span><span class="sxs-lookup"><span data-stu-id="0d872-157">For direct binding, you can either select a port to connect to, to do routing based on filter expressions on incoming messages in the MessageBox database, or to make it a self-correlating port.</span></span> <span data-ttu-id="0d872-158">您可以从下拉列表框中选择端口。</span><span class="sxs-lookup"><span data-stu-id="0d872-158">You can select a port from a drop-down list box.</span></span>  
  
         <span data-ttu-id="0d872-159">有关详细信息，请参阅[端口绑定](../core/port-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="0d872-159">For more information, see [Port Bindings](../core/port-bindings.md).</span></span>  
  
3.  <span data-ttu-id="0d872-160">完成向导。</span><span class="sxs-lookup"><span data-stu-id="0d872-160">Complete the wizard.</span></span> <span data-ttu-id="0d872-161">标题为在端口配置向导的最后一页**完成端口向导**，显示你所做的选择在前面的页上，以便可以将更改提交之前进行验证。</span><span class="sxs-lookup"><span data-stu-id="0d872-161">The final page of the Port Configuration Wizard, entitled **Completing the Port Wizard**, displays the choices you made on the preceding pages so that you can verify them before committing the changes.</span></span> <span data-ttu-id="0d872-162">如果所做的更改是否正确，请单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="0d872-162">If the changes are correct, click **Finish**.</span></span> <span data-ttu-id="0d872-163">否则，请单击**回**重新输入你想要更改的任何信息。</span><span class="sxs-lookup"><span data-stu-id="0d872-163">Otherwise, click **Back** to re-enter any information you want to change.</span></span> <span data-ttu-id="0d872-164">然后再次将完成该向导并单击**完成**最后一页上显示的信息匹配需要进行的更改时。</span><span class="sxs-lookup"><span data-stu-id="0d872-164">Then move through the wizard again and click **Finish** when the information displayed on the final page matches the changes you want to make.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0d872-165">如果你要创建一个新的端口，并且你单击**取消**在任何时间之前完成端口配置时向导中，该端口未创建。</span><span class="sxs-lookup"><span data-stu-id="0d872-165">If you are creating a new port and you click **Cancel** in the wizard at any time before finishing port configuration, the port is not created.</span></span> <span data-ttu-id="0d872-166">如果是使用该向导来修改现有向导，则取消向导将会撤消之前所做的所有更改。</span><span class="sxs-lookup"><span data-stu-id="0d872-166">If you were using the wizard to modify an existing port, canceling the wizard undoes any changes you have made.</span></span> <span data-ttu-id="0d872-167">否则为如果你单击**取消**在向导中，仍创建该适配器，但未设置其属性。</span><span class="sxs-lookup"><span data-stu-id="0d872-167">Otherwise, if you click **Cancel** in the wizard, the adapter is still created, but its properties are not set.</span></span> <span data-ttu-id="0d872-168">您可以在端口的“属性”窗口中手动设置端口属性，也可以重新运行本向导。</span><span class="sxs-lookup"><span data-stu-id="0d872-168">You can set port properties manually in the Properties window for the port, or you can run the wizard again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d872-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d872-169">See Also</span></span>  
 [<span data-ttu-id="0d872-170">使用在业务流程中的端口</span><span class="sxs-lookup"><span data-stu-id="0d872-170">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)