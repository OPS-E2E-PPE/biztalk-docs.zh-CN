---
title: 在 BizTalk 中配置 SAP 系统的 SOAP 操作 |Microsoft Docs
description: 在表达式形状中，输入 SOAP 操作或使用 BizTalk 适配器包 (BAP) 中的 WCF 自定义或 WCF SAP 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 76084bc5-7a10-4c4c-be22-bee83779a011
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 963c4b3c8d8287b430774813487e924837880a01
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004870"
---
# <a name="configure-the-soap-action-for-the-sap-system"></a><span data-ttu-id="b6016-103">配置用于 SAP 系统的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="b6016-103">Configure the SOAP action for the SAP system</span></span>
<span data-ttu-id="b6016-104">若要对使用基于 WCF 的 SAP 系统执行任何操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，适配器的用户必须指定 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="b6016-104">To perform any operation on the SAP system using the WCF-based [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], adapter users must specify a SOAP action.</span></span> <span data-ttu-id="b6016-105">SOAP 操作通信适配器应执行什么操作。</span><span class="sxs-lookup"><span data-stu-id="b6016-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="b6016-106">可以指定在设计时或在运行时的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="b6016-106">You can specify the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="b6016-107">但是，如果指定的 SOAP 操作这两个在设计时和运行时，将替代在设计时指定的操作。</span><span class="sxs-lookup"><span data-stu-id="b6016-107">However, if you specify the SOAP action both at design time and run time, the action you specified at design time will be overridden.</span></span>  
  
 <span data-ttu-id="b6016-108">有关指定 SOAP 操作的详细信息，请参阅[对于 WCF 发送适配器指定 SOAP 操作](../../core/specifying-soap-actions-for-wcf-send-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="b6016-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>
  
## <a name="enter-soap-action-at-design-time"></a><span data-ttu-id="b6016-109">输入在设计时的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="b6016-109">Enter SOAP Action at Design Time</span></span>  
 <span data-ttu-id="b6016-110">为设计时，你必须指定 SOAP 操作作为业务流程的一部分包括的表达式形状。</span><span class="sxs-lookup"><span data-stu-id="b6016-110">For design time, you must specify the SOAP action as part of orchestration by including an expression shape.</span></span>  
  
 
1.  <span data-ttu-id="b6016-111">在 BizTalk 业务流程，包括的表达式形状将其从拖**BizTalk 业务流程**工具箱。</span><span class="sxs-lookup"><span data-stu-id="b6016-111">In the BizTalk orchestration, include an Expression shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="b6016-112">双击**表达式**形状以打开 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="b6016-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="b6016-113">在 BizTalk 表达式编辑器中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="b6016-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="b6016-114">例如：</span><span class="sxs-lookup"><span data-stu-id="b6016-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET"  
    ```  
  
     <span data-ttu-id="b6016-115">有关详细信息**表达式**形状和 BizTalk 表达式编辑器中，请参阅[如何创建表达式](../../core/how-to-create-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="b6016-115">For more information about the **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>
  
## <a name="enter-soap-action-at-run-time"></a><span data-ttu-id="b6016-116">输入在运行时的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="b6016-116">Enter SOAP Action at Run Time</span></span>  
 <span data-ttu-id="b6016-117">对于运行时，可以为 WCF 自定义或 WCF SAP 端口配置的一部分来指定 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="b6016-117">For run time, you can specify the SOAP action as part of the WCF-Custom or WCF-SAP port configuration.</span></span>  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="b6016-118">输入 WCF 自定义端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="b6016-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1. <span data-ttu-id="b6016-119">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b6016-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="b6016-120">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b6016-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="b6016-121">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="b6016-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3. <span data-ttu-id="b6016-122">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b6016-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="b6016-123">在中**Wcf-custom 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b6016-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5. <span data-ttu-id="b6016-124">在中**操作**文字框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="b6016-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="b6016-125">您可以按以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="b6016-125">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="b6016-126">**通过使用单一操作格式**。</span><span class="sxs-lookup"><span data-stu-id="b6016-126">**By using the single action format**.</span></span> <span data-ttu-id="b6016-127">如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="b6016-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="b6016-128">例如：</span><span class="sxs-lookup"><span data-stu-id="b6016-128">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   <span data-ttu-id="b6016-129">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="b6016-129">**By using the action mapping format**.</span></span> <span data-ttu-id="b6016-130">如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="b6016-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="b6016-131">例如，如果单个 WCF 自定义端口发送和接收 （若要调用 RFC_CUSTOMER_GET RFC） 的 Op1 和 Op2 （若要调用 BAPI_SALESORDER_CREATEFROMDAT2 BAPI） 的消息，可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="b6016-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to invoke RFC_CUSTOMER_GET RFC) and Op2 (to invoke BAPI_SALESORDER_CREATEFROMDAT2 BAPI), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="b6016-132">这种方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过同一端口。</span><span class="sxs-lookup"><span data-stu-id="b6016-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="b6016-133">SOAP 操作的格式是不同的每个操作。</span><span class="sxs-lookup"><span data-stu-id="b6016-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="b6016-134">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="b6016-134">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>
  
### <a name="enter-a-soap-action-for-the-wcf-sap-port"></a><span data-ttu-id="b6016-135">输入 WCF SAP 端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="b6016-135">Enter a SOAP action for the WCF-SAP port</span></span>  
  
1. <span data-ttu-id="b6016-136">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b6016-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="b6016-137">添加 WCF SAP 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="b6016-137">Add the WCF-SAP adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="b6016-138">有关说明，请参阅[将 SAP 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="b6016-138">For instructions, see [Add the SAP Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sap/add-the-sap-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="b6016-139">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="b6016-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="b6016-140">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="b6016-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4. <span data-ttu-id="b6016-141">在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加的 WCF-SAP 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="b6016-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SAP adapter you added earlier, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="b6016-142">在传输属性对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="b6016-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6. <span data-ttu-id="b6016-143">在中**操作**文字框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="b6016-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="b6016-144">您可以按以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="b6016-144">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="b6016-145">**通过使用单一操作格式**。</span><span class="sxs-lookup"><span data-stu-id="b6016-145">**By using the single action format**.</span></span> <span data-ttu-id="b6016-146">如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="b6016-146">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="b6016-147">例如：</span><span class="sxs-lookup"><span data-stu-id="b6016-147">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET  
       ```  
  
   -   <span data-ttu-id="b6016-148">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="b6016-148">**By using the action mapping format**.</span></span> <span data-ttu-id="b6016-149">如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="b6016-149">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="b6016-150">例如，如果单个 WCF 自定义端口发送和接收 （若要调用 RFC_CUSTOMER_GET RFC） 的 Op1 和 Op2 （若要调用 BAPI_SALESORDER_CREATEFROMDAT2 BAPI） 的消息，可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="b6016-150">For example, if a single WCF-Custom port sends and receives messages for Op1 (to invoke RFC_CUSTOMER_GET RFC) and Op2 (to invoke BAPI_SALESORDER_CREATEFROMDAT2 BAPI), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_CUSTOMER_GET " />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.Sap/2007/03/Bapi/BUS2032/CREATEFROMDAT2/BAPI_SALESORDER_CREATEFROMDAT2" />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="b6016-151">这种方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过同一端口。</span><span class="sxs-lookup"><span data-stu-id="b6016-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="b6016-152">SOAP 操作的格式是不同的每个操作。</span><span class="sxs-lookup"><span data-stu-id="b6016-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="b6016-153">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="b6016-153">For more information about action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b6016-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6016-154">See Also</span></span>  
[<span data-ttu-id="b6016-155">生成块以创建 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="b6016-155">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)