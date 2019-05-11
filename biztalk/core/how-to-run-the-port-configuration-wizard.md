---
title: 如何运行端口配置向导 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Port Configuration Wizard [Orchestration Designer], starting
- Port Configuration Wizard [Orchestration Designer], how to
- Port Configuration Wizard [Orchestration Designer], about Port Configuration Wizard
- ports, Port Configuration Wizard [Orchestration Designer]
- Port Configuration Wizard [Orchestration Designer]
ms.assetid: 8035ce32-5ed4-49cb-b6f0-998b0460751e
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a12efffbcf7d5f283fd4c42547b628e77af08bcb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65334893"
---
# <a name="how-to-run-the-port-configuration-wizard"></a><span data-ttu-id="6ec6c-102">如何运行端口配置向导</span><span class="sxs-lookup"><span data-stu-id="6ec6c-102">How to Run the Port Configuration Wizard</span></span>
<span data-ttu-id="6ec6c-103">使用端口配置向导来创建和配置端口在业务流程设计器中。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-103">You use the Port Configuration Wizard to create and configure a port in Orchestration Designer.</span></span> <span data-ttu-id="6ec6c-104">端口必须具有与其关联的端口类型和您使用向导来选择现有端口类型或创建新的端口类型。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-104">A port must have a port type associated with it, and you use the wizard to select an existing port type or to create a new port type.</span></span> <span data-ttu-id="6ec6c-105">有关端口和端口类型的详细信息，请参阅[业务流程中使用端口](../core/using-ports-in-orchestrations.md)。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-105">For more information about ports and port types, see [Using Ports in Orchestrations](../core/using-ports-in-orchestrations.md).</span></span>  
  
### <a name="to-start-the-wizard"></a><span data-ttu-id="6ec6c-106">若要启动向导</span><span class="sxs-lookup"><span data-stu-id="6ec6c-106">To Start the wizard</span></span>  
  
1.  <span data-ttu-id="6ec6c-107">右键单击端口 （在设计图面上或在业务流程视图窗口中），单击**配置端口**。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-107">Right-clicking a port (on the design surface or in the Orchestration View window) and clicking **Configure Port**.</span></span>  
  
2.  <span data-ttu-id="6ec6c-108">运行其关联的操作会导致一个端口，以创建智能标记项。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-108">Running Smart Tag items whose associated actions cause a port to be created.</span></span>  
  
3.  <span data-ttu-id="6ec6c-109">选择**新配置的端口参数**命令从业务流程视图窗口中的业务流程参数文件夹的快捷菜单。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-109">Selecting the **New Configured Port Parameter** command from the shortcut menu of the Orchestration Parameters folder in the Orchestration View window.</span></span>  
  
### <a name="to-run-the-wizard"></a><span data-ttu-id="6ec6c-110">若要运行向导</span><span class="sxs-lookup"><span data-stu-id="6ec6c-110">To Run the Wizard</span></span>  
  
1.  <span data-ttu-id="6ec6c-111">打开端口配置向导。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-111">Open the Port Configuration Wizard.</span></span>  
  
2.  <span data-ttu-id="6ec6c-112">指定的端口信息。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-112">Specify port information.</span></span> <span data-ttu-id="6ec6c-113">为了帮助您，向导将显示多个页面。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-113">To help you, the wizard displays several pages.</span></span> <span data-ttu-id="6ec6c-114">完成每个页后，迁移到以下通过单击**下一步**，或将移动到通过单击前一次**回**。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-114">After completing each page, move to the following one by clicking **Next**, or move to the preceding one by clicking **Back**.</span></span>  
  
    -   <span data-ttu-id="6ec6c-115">**端口属性**。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-115">**Port Properties**.</span></span> <span data-ttu-id="6ec6c-116">键入端口的名称。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-116">Type in a name for the port.</span></span>  
  
    -   <span data-ttu-id="6ec6c-117">**选择端口类型。**</span><span class="sxs-lookup"><span data-stu-id="6ec6c-117">**Select a Port Type.**</span></span> <span data-ttu-id="6ec6c-118">在此页上，您首先选择是否想**新建端口类型**或**现有端口类型**。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-118">On this page, you first select whether you want a **New Port Type** or an **Existing Port Type**.</span></span> <span data-ttu-id="6ec6c-119">如果选择**现有端口类型**，然后使用树控件来选择要分配现有端口类型。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-119">If you select **Existing Port Type**, you then use a tree control to choose which existing port type to assign.</span></span>  
  
         <span data-ttu-id="6ec6c-120">如果选择**新建端口类型**，然后，你需要键入的名称中的端口类型**名称**文本，或接受建议的默认名称。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-120">If you select **New Port Type**, you then need to type the name of the port type in the **Name** text box, or accept the suggested default name.</span></span> <span data-ttu-id="6ec6c-121">您还选择端口类型的通信模式 (单向或请求-响应) 和任何访问限制在新建端口类型。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-121">You also select the port type's communication pattern (one-way or request-response) and any access restrictions to impose on the new port type.</span></span>  
  
    -   <span data-ttu-id="6ec6c-122">**端口绑定**。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-122">**Port Binding**.</span></span> <span data-ttu-id="6ec6c-123">此页上，指定的方向的通信，也称为*极性*，以及该端口的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-123">On this page you specify the direction of communication, also known as the *polarity*, and the binding type of the port.</span></span>  
  
         <span data-ttu-id="6ec6c-124">您所做的极性选择部分取决于您在向导的上一页选择的端口类型的通信模式**选择端口类型**。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-124">The polarity choice you make depends in part on the communication pattern of the port type that you selected on the preceding page of the wizard, **Select a Port Type**.</span></span> <span data-ttu-id="6ec6c-125">下表总结了你的选择：</span><span class="sxs-lookup"><span data-stu-id="6ec6c-125">Your choices are summarized in the following table:</span></span>  
  
        |<span data-ttu-id="6ec6c-126">端口方向</span><span class="sxs-lookup"><span data-stu-id="6ec6c-126">Port direction</span></span>|<span data-ttu-id="6ec6c-127">通信模式</span><span class="sxs-lookup"><span data-stu-id="6ec6c-127">Communication pattern</span></span>|<span data-ttu-id="6ec6c-128">若要选择端口绑定页面上的通信方向</span><span class="sxs-lookup"><span data-stu-id="6ec6c-128">Direction of communication to choose on Port Binding page</span></span>|  
        |--------------------|---------------------------|---------------------------------------------------------------|  
        |<span data-ttu-id="6ec6c-129">Send</span><span class="sxs-lookup"><span data-stu-id="6ec6c-129">Send</span></span>|<span data-ttu-id="6ec6c-130">单向</span><span class="sxs-lookup"><span data-stu-id="6ec6c-130">One-way</span></span>|<span data-ttu-id="6ec6c-131">我将始终在发送消息此端口上。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-131">I will always be sending messages on this port.</span></span>|  
        |<span data-ttu-id="6ec6c-132">Receive</span><span class="sxs-lookup"><span data-stu-id="6ec6c-132">Receive</span></span>|<span data-ttu-id="6ec6c-133">单向</span><span class="sxs-lookup"><span data-stu-id="6ec6c-133">One-way</span></span>|<span data-ttu-id="6ec6c-134">我始终将接收此端口上的消息。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-134">I will always be receiving messages on this port.</span></span>|  
        |<span data-ttu-id="6ec6c-135">发送接收</span><span class="sxs-lookup"><span data-stu-id="6ec6c-135">Send-Receive</span></span>|<span data-ttu-id="6ec6c-136">要求响应</span><span class="sxs-lookup"><span data-stu-id="6ec6c-136">Solicit-response</span></span>|<span data-ttu-id="6ec6c-137">我将发送请求并接收响应。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-137">I will be sending a request and receiving a response.</span></span>|  
        |<span data-ttu-id="6ec6c-138">接收发送</span><span class="sxs-lookup"><span data-stu-id="6ec6c-138">Receive-Send</span></span>|<span data-ttu-id="6ec6c-139">请求-响应</span><span class="sxs-lookup"><span data-stu-id="6ec6c-139">Request-response</span></span>|<span data-ttu-id="6ec6c-140">我将接收请求并发送响应。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-140">I will be receiving a request and sending a response.</span></span>|  
  
         <span data-ttu-id="6ec6c-141">有四个不同的绑定类型的选择：以后指定、 立即指定、 动态和直接。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-141">You have a choice of four different binding types: Specify later, Specify now, Dynamic, and Direct.</span></span> <span data-ttu-id="6ec6c-142">每个选项显示一组不同的配置选项，如下所述：</span><span class="sxs-lookup"><span data-stu-id="6ec6c-142">Each choice displays a different set of configuration options, as summarized here:</span></span>  
  
         <span data-ttu-id="6ec6c-143">**指定更高版本。**</span><span class="sxs-lookup"><span data-stu-id="6ec6c-143">**Specify later.**</span></span> <span data-ttu-id="6ec6c-144">选择此选项后，您无需再配置向导中做出选择因为在设计时不确定的绑定信息。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-144">After selecting this option, you make no further configuration choices in the wizard because binding information is not determined at design time.</span></span> <span data-ttu-id="6ec6c-145">通常它是由管理员在部署时添加。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-145">Typically it is added by an Administrator at deployment time.</span></span>  
  
         <span data-ttu-id="6ec6c-146">**立即指定。**</span><span class="sxs-lookup"><span data-stu-id="6ec6c-146">**Specify now.**</span></span> <span data-ttu-id="6ec6c-147">可以在设计时指定一个 URI，定义的端口是要绑定的实体。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-147">You can specify at design time a URI that defines the entity to which the port is to be bound.</span></span> <span data-ttu-id="6ec6c-148">此外需要从包含 BizTalk 消息队列、 文件、 SMTP、 HTTP 和 SOAP 传输类型的列表中选择。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-148">You also need to select from a list of transport types that includes BizTalk Message Queuing, FILE, SMTP, HTTP, and SOAP.</span></span> <span data-ttu-id="6ec6c-149">这是为了在业务流程设计器中; 早期绑定的硬编码列表因此，其他传输不可用在此列表中。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-149">This is a hard-coded list for the purpose of early binding in Orchestration Designer; therefore, other transports are not available in this list.</span></span> <span data-ttu-id="6ec6c-150">最后，选择接收管道和发送管道中的可用管道列表。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-150">Finally, you select a receive pipeline and a send pipeline from a list of available pipelines.</span></span> <span data-ttu-id="6ec6c-151">每个列表中包括的所有管道中当前的项目以及从引用的程序集，其中显示了选择管道的选项**选择项目类型**对话框。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-151">The list for each includes all pipelines in the current project plus the option of selecting a pipeline from a referenced assembly, which displays the **Select Artifact Type** dialog box.</span></span>  
  
         <span data-ttu-id="6ec6c-152">**动态。**</span><span class="sxs-lookup"><span data-stu-id="6ec6c-152">**Dynamic.**</span></span> <span data-ttu-id="6ec6c-153">此选项具有类似的选项**立即指定**，但仅适用于发送端口。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-153">This option has similar choices to **Specify now**, but it is available only for a send port.</span></span> <span data-ttu-id="6ec6c-154">您可以指定要使用的发送管道。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-154">You can specify a send pipeline to use.</span></span> <span data-ttu-id="6ec6c-155">可以指定的端口中单独**表达式**形状，以便在运行时分配。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-155">You can specify the port separately in an **Expression** shape so that it is assigned at run time.</span></span>  
  
         <span data-ttu-id="6ec6c-156">**直接。**</span><span class="sxs-lookup"><span data-stu-id="6ec6c-156">**Direct.**</span></span> <span data-ttu-id="6ec6c-157">对于直接绑定，您可以选择连接到，若要进行路由基于筛选器表达式对 MessageBox 数据库中传入的消息或使它成为自相关端口的端口。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-157">For direct binding, you can either select a port to connect to, to do routing based on filter expressions on incoming messages in the MessageBox database, or to make it a self-correlating port.</span></span> <span data-ttu-id="6ec6c-158">可以从下拉列表框中选择的端口。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-158">You can select a port from a drop-down list box.</span></span>  
  
         <span data-ttu-id="6ec6c-159">有关详细信息，请参阅[端口绑定](../core/port-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-159">For more information, see [Port Bindings](../core/port-bindings.md).</span></span>  
  
3.  <span data-ttu-id="6ec6c-160">完成向导。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-160">Complete the wizard.</span></span> <span data-ttu-id="6ec6c-161">端口配置向导，标题为的最后一页**完成端口向导**，显示你所做的选择在前面的页面，以便可以在提交更改之前进行验证。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-161">The final page of the Port Configuration Wizard, entitled **Completing the Port Wizard**, displays the choices you made on the preceding pages so that you can verify them before committing the changes.</span></span> <span data-ttu-id="6ec6c-162">如果所做的更改是否正确，请单击**完成**。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-162">If the changes are correct, click **Finish**.</span></span> <span data-ttu-id="6ec6c-163">否则，请单击**回**重新输入你想要更改的任何信息。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-163">Otherwise, click **Back** to re-enter any information you want to change.</span></span> <span data-ttu-id="6ec6c-164">然后再次将通过该向导并单击**完成**时想要进行的更改相匹配的最后一页上显示的信息。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-164">Then move through the wizard again and click **Finish** when the information displayed on the final page matches the changes you want to make.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6ec6c-165">如果你要创建一个新的端口并且单击**取消**在任何时间之前完成端口配置向导中，该端口未创建。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-165">If you are creating a new port and you click **Cancel** in the wizard at any time before finishing port configuration, the port is not created.</span></span> <span data-ttu-id="6ec6c-166">如果已使用向导来修改现有的端口，取消向导撤消所做的任何更改。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-166">If you were using the wizard to modify an existing port, canceling the wizard undoes any changes you have made.</span></span> <span data-ttu-id="6ec6c-167">否则为如果您单击**取消**在向导中，仍然会创建适配器，但未设置其属性。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-167">Otherwise, if you click **Cancel** in the wizard, the adapter is still created, but its properties are not set.</span></span> <span data-ttu-id="6ec6c-168">您可以手动设置端口属性作为端口，在属性窗口中也可以再次运行向导。</span><span class="sxs-lookup"><span data-stu-id="6ec6c-168">You can set port properties manually in the Properties window for the port, or you can run the wizard again.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec6c-169">请参阅</span><span class="sxs-lookup"><span data-stu-id="6ec6c-169">See Also</span></span>  
 [<span data-ttu-id="6ec6c-170">在业务流程中使用端口</span><span class="sxs-lookup"><span data-stu-id="6ec6c-170">Using Ports in Orchestrations</span></span>](../core/using-ports-in-orchestrations.md)