---
title: 在 BizTalk 中配置用于 Siebel 适配器的 SOAP 操作 |Microsoft 文档
description: 在 Visual Studio 中，输入 SOAP 操作或使用 BizTalk 适配器包 (BAP) 中的 WCF 自定义或 WCF Siebel 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f22a4691-0355-4f08-a14e-e90a3c987ac0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b851aa0b26d80a43f5a839232298ace5507f471b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22222557"
---
# <a name="configure-the-soap-action-for-siebel"></a><span data-ttu-id="56c0f-103">配置用于 Siebel 的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="56c0f-103">Configure the SOAP action for Siebel</span></span>
<span data-ttu-id="56c0f-104">若要对使用基于 WCF 的 Siebel 系统执行任何操作[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]，适配器用户必须指定 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="56c0f-104">To perform any operation on the Siebel system using the WCF-based [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)], adapter users must specify a SOAP action.</span></span> <span data-ttu-id="56c0f-105">SOAP 操作进行通信的适配器应执行什么操作。</span><span class="sxs-lookup"><span data-stu-id="56c0f-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="56c0f-106">你可以指定在设计时或在运行时的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="56c0f-106">You can specify the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="56c0f-107">但是，如果你指定的 SOAP 操作这两个在设计时和运行时，将替代在设计时指定的操作。</span><span class="sxs-lookup"><span data-stu-id="56c0f-107">However, if you specify the SOAP action both at design time and run time, the action you specified at design time will be overridden.</span></span>  
  
 <span data-ttu-id="56c0f-108">有关指定 SOAP 操作的详细信息，请参阅[指定 WCF 发送适配器的 SOAP 操作](../../core/specifying-soap-actions-for-wcf-send-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="56c0f-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>
  
## <a name="enter-soap-action-at-design-time"></a><span data-ttu-id="56c0f-109">输入在设计时的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="56c0f-109">Enter SOAP Action at Design Time</span></span>  
 <span data-ttu-id="56c0f-110">为设计时，你必须指定的 SOAP 操作的业务流程的一部分包括表达式形状。</span><span class="sxs-lookup"><span data-stu-id="56c0f-110">For design time, you must specify the SOAP action as part of orchestration by including an expression shape.</span></span>  
  
1.  <span data-ttu-id="56c0f-111">在 BizTalk 业务流程是表达式形状包含通过拖动从**BizTalk 业务流程**工具箱。</span><span class="sxs-lookup"><span data-stu-id="56c0f-111">In the BizTalk orchestration include an Expression shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="56c0f-112">双击**表达式**形状以打开 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="56c0f-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="56c0f-113">在 BizTalk 表达式编辑器中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="56c0f-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="56c0f-114">例如：</span><span class="sxs-lookup"><span data-stu-id="56c0f-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert"  
    ```  
  
     <span data-ttu-id="56c0f-115">有关详细信息**表达式**形状和 BizTalk 表达式编辑器，请参阅[如何创建表达式](../../core/how-to-create-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="56c0f-115">For more information about **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-at-run-time"></a><span data-ttu-id="56c0f-116">在运行时输入 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="56c0f-116">Enter SOAP Action at run time</span></span>  
 <span data-ttu-id="56c0f-117">运行时，你必须作为 WCF 自定义或 WCF Siebel 端口属性对话框中的一部分来指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="56c0f-117">For run time, you must specify the SOAP action as part of the WCF-Custom or WCF-Siebel port properties dialog box.</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="56c0f-118">输入 WCF 自定义端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="56c0f-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="56c0f-119">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="56c0f-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="56c0f-120">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="56c0f-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="56c0f-121">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="56c0f-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="56c0f-122">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="56c0f-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="56c0f-123">在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="56c0f-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="56c0f-124">在**操作**文本框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="56c0f-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="56c0f-125">你可以通过以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="56c0f-125">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="56c0f-126">**通过单个操作格式**。</span><span class="sxs-lookup"><span data-stu-id="56c0f-126">**By using the single action format**.</span></span> <span data-ttu-id="56c0f-127">如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="56c0f-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="56c0f-128">例如：</span><span class="sxs-lookup"><span data-stu-id="56c0f-128">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    -   <span data-ttu-id="56c0f-129">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="56c0f-129">**By using the action mapping format**.</span></span> <span data-ttu-id="56c0f-130">如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="56c0f-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="56c0f-131">例如，如果单个 WCF 自定义端口发送和接收 Op1 （即执行插入操作帐户在业务组件上的） 和 Op2 （即执行更新操作帐户在业务组件上的） 的消息，SOAP 操作可以指定以下方式：</span><span class="sxs-lookup"><span data-stu-id="56c0f-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to perform an Insert operation on Account business component) and Op2 (to perform an Update operation on Account business component), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="56c0f-132">此方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过相同端口。</span><span class="sxs-lookup"><span data-stu-id="56c0f-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="56c0f-133">SOAP 操作的格式为每个操作不同。</span><span class="sxs-lookup"><span data-stu-id="56c0f-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="56c0f-134">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="56c0f-134">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span></span>
  
#### <a name="enter-a-soap-action-for-the-wcf-siebel-port"></a><span data-ttu-id="56c0f-135">输入 WCF Siebel 端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="56c0f-135">Enter a SOAP action for the WCF-Siebel port</span></span>  
  
1.  <span data-ttu-id="56c0f-136">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="56c0f-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="56c0f-137">添加到在 WCF Siebel 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="56c0f-137">Add the WCF-Siebel adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="56c0f-138">有关说明，请参阅[将 Siebel 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="56c0f-138">For instructions, see [Add the Siebel Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-siebel/add-the-siebel-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="56c0f-139">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="56c0f-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="56c0f-140">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="56c0f-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="56c0f-141">在端口属性对话框中，从**类型**下拉列表中，选择 WCF Siebel 适配器更早版本，添加，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="56c0f-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-Siebel adapter you add earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="56c0f-142">在端口属性对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="56c0f-142">In the port properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="56c0f-143">在**操作**文本框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="56c0f-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="56c0f-144">你可以通过以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="56c0f-144">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="56c0f-145">**通过单个操作格式**。</span><span class="sxs-lookup"><span data-stu-id="56c0f-145">**By using the single action format**.</span></span> <span data-ttu-id="56c0f-146">如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="56c0f-146">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="56c0f-147">例如：</span><span class="sxs-lookup"><span data-stu-id="56c0f-147">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
        ```  
  
    -   <span data-ttu-id="56c0f-148">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="56c0f-148">**By using the action mapping format**.</span></span> <span data-ttu-id="56c0f-149">如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="56c0f-149">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="56c0f-150">例如，如果单个 WCF 自定义端口发送和接收 Op1 （即执行插入操作帐户在业务组件上的） 和 Op2 （即执行更新操作帐户在业务组件上的） 的消息，SOAP 操作可以指定以下方式：</span><span class="sxs-lookup"><span data-stu-id="56c0f-150">For example, if a single WCF-Custom port sends and receives messages for Op1 (to perform an Insert operation on Account business component) and Op2 (to perform an Update operation on Account business component), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Update " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="56c0f-151">此方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过相同端口。</span><span class="sxs-lookup"><span data-stu-id="56c0f-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="56c0f-152">SOAP 操作的格式为每个操作不同。</span><span class="sxs-lookup"><span data-stu-id="56c0f-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="56c0f-153">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="56c0f-153">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="56c0f-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="56c0f-154">See Also</span></span>  
[<span data-ttu-id="56c0f-155">构建基块创建带有 Siebel 适配器 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="56c0f-155">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)