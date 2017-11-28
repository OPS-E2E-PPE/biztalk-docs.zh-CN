---
title: "在 BizTalk 中配置 SAP 系统的 SOAP 操作 |Microsoft 文档"
description: "在表达式形状中，输入 SOAP 操作或使用 BizTalk 适配器包 (BAP) 中的 WCF 自定义或 WCF SAP 适配器"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76084bc5-7a10-4c4c-be22-bee83779a011
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36a474d53d3fcaf61668800094a1d98d0e061aa5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-soap-action-for-the-sap-system"></a><span data-ttu-id="36fcb-103">配置 SAP 系统的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="36fcb-103">Configure the SOAP action for the SAP system</span></span>
<span data-ttu-id="36fcb-104">若要对使用基于 WCF 的 SAP 系统执行任何操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，适配器用户必须指定 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="36fcb-104">To perform any operation on the SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], adapter users must specify a SOAP action.</span></span> <span data-ttu-id="36fcb-105">SOAP 操作进行通信的适配器应执行什么操作。</span><span class="sxs-lookup"><span data-stu-id="36fcb-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="36fcb-106">你可以指定在设计时或在运行时的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="36fcb-106">You can specify the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="36fcb-107">但是，如果你指定的 SOAP 操作这两个在设计时和运行时，将替代在设计时指定的操作。</span><span class="sxs-lookup"><span data-stu-id="36fcb-107">However, if you specify the SOAP action both at design time and run time, the action you specified at design time will be overridden.</span></span>  
  
 <span data-ttu-id="36fcb-108">有关指定 SOAP 操作的详细信息，请参阅[指定 WCF 发送适配器的 SOAP 操作](../../core/specifying-soap-actions-for-wcf-send-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="36fcb-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>
  
## <a name="enter-soap-action-at-design-time"></a><span data-ttu-id="36fcb-109">输入在设计时的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="36fcb-109">Enter SOAP Action at Design Time</span></span>  
 <span data-ttu-id="36fcb-110">为设计时，你必须指定的 SOAP 操作的业务流程的一部分包括表达式形状。</span><span class="sxs-lookup"><span data-stu-id="36fcb-110">For design time, you must specify the SOAP action as part of orchestration by including an expression shape.</span></span>  
  
 
1.  <span data-ttu-id="36fcb-111">在 BizTalk 业务流程，包括表达式形状通过拖动从**BizTalk 业务流程**工具箱。</span><span class="sxs-lookup"><span data-stu-id="36fcb-111">In the BizTalk orchestration, include an Expression shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="36fcb-112">双击**表达式**形状以打开 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="36fcb-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="36fcb-113">在 BizTalk 表达式编辑器中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="36fcb-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="36fcb-114">例如：</span><span class="sxs-lookup"><span data-stu-id="36fcb-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET"  
    ```  
  
     <span data-ttu-id="36fcb-115">有关详细信息**表达式**形状和 BizTalk 表达式编辑器，请参阅[如何创建表达式](../../core/how-to-create-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="36fcb-115">For more information about the **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>
  
## <a name="enter-soap-action-at-run-time"></a><span data-ttu-id="36fcb-116">输入在运行时的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="36fcb-116">Enter SOAP Action at Run Time</span></span>  
 <span data-ttu-id="36fcb-117">对于运行时，你可以作为 WCF 自定义或 WCF SAP 端口配置的一部分指定的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="36fcb-117">For run time, you can specify the SOAP action as part of the WCF-Custom or WCF-SAP port configuration.</span></span>  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="36fcb-118">输入 WCF 自定义端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="36fcb-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="36fcb-119">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="36fcb-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="36fcb-120">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="36fcb-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="36fcb-121">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="36fcb-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="36fcb-122">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="36fcb-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="36fcb-123">在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="36fcb-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="36fcb-124">在**操作**文本框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="36fcb-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="36fcb-125">你可以通过以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="36fcb-125">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="36fcb-126">**通过单个操作格式**。</span><span class="sxs-lookup"><span data-stu-id="36fcb-126">**By using the single action format**.</span></span> <span data-ttu-id="36fcb-127">如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="36fcb-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="36fcb-128">例如：</span><span class="sxs-lookup"><span data-stu-id="36fcb-128">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
        ```  
  
    -   <span data-ttu-id="36fcb-129">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="36fcb-129">**By using the action mapping format**.</span></span> <span data-ttu-id="36fcb-130">如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="36fcb-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="36fcb-131">例如，如果单个 WCF 自定义端口发送和接收 Op1 （来调用 RFC_CUSTOMER_GET RFC） 和 Op2 （来调用 BAPI_SALESORDER_CREATEFROMDAT2 BAPI） 的消息，则可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="36fcb-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to invoke RFC_CUSTOMER_GET RFC) and Op2 (to invoke BAPI_SALESORDER_CREATEFROMDAT2 BAPI), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="36fcb-132">此方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过相同端口。</span><span class="sxs-lookup"><span data-stu-id="36fcb-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="36fcb-133">SOAP 操作的格式为每个操作不同。</span><span class="sxs-lookup"><span data-stu-id="36fcb-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="36fcb-134">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="36fcb-134">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>
  
### <a name="enter-a-soap-action-for-the-wcf-sap-port"></a><span data-ttu-id="36fcb-135">输入 WCF SAP 端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="36fcb-135">Enter a SOAP action for the WCF-SAP port</span></span>  
  
1.  <span data-ttu-id="36fcb-136">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="36fcb-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="36fcb-137">添加到 WCF SAP 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="36fcb-137">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="36fcb-138">有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="36fcb-138">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="36fcb-139">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="36fcb-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="36fcb-140">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="36fcb-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="36fcb-141">在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加的 WCF SAP 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="36fcb-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="36fcb-142">在传输属性对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="36fcb-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="36fcb-143">在**操作**文本框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="36fcb-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="36fcb-144">你可以通过以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="36fcb-144">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="36fcb-145">**通过单个操作格式**。</span><span class="sxs-lookup"><span data-stu-id="36fcb-145">**By using the single action format**.</span></span> <span data-ttu-id="36fcb-146">如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="36fcb-146">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="36fcb-147">例如：</span><span class="sxs-lookup"><span data-stu-id="36fcb-147">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
        ```  
  
    -   <span data-ttu-id="36fcb-148">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="36fcb-148">**By using the action mapping format**.</span></span> <span data-ttu-id="36fcb-149">如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="36fcb-149">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="36fcb-150">例如，如果单个 WCF 自定义端口发送和接收 Op1 （来调用 RFC_CUSTOMER_GET RFC） 和 Op2 （来调用 BAPI_SALESORDER_CREATEFROMDAT2 BAPI） 的消息，则可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="36fcb-150">For example, if a single WCF-Custom port sends and receives messages for Op1 (to invoke RFC_CUSTOMER_GET RFC) and Op2 (to invoke BAPI_SALESORDER_CREATEFROMDAT2 BAPI), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="36fcb-151">此方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过相同端口。</span><span class="sxs-lookup"><span data-stu-id="36fcb-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="36fcb-152">SOAP 操作的格式为每个操作不同。</span><span class="sxs-lookup"><span data-stu-id="36fcb-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="36fcb-153">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="36fcb-153">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="36fcb-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36fcb-154">See Also</span></span>  
[<span data-ttu-id="36fcb-155">若要创建的 SAP 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="36fcb-155">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)