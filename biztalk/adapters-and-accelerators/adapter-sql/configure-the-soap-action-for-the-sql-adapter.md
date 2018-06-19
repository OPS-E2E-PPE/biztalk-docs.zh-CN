---
title: 在 BizTalk 中配置 SQL 适配器的 SOAP 操作 |Microsoft 文档
description: 在 Visual Studio 中，输入 SOAP 操作或使用 BizTalk 适配器包 (BAP) 中的 WCF 自定义或 WCF SQL 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: acd7f60b-c27f-4988-a67c-e56ef8d38f66
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d4e342353b13848cca1c332d4568f541e59924cc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22223493"
---
# <a name="configure-the-soap-action-for-the-sql-adapter"></a><span data-ttu-id="8ba56-103">配置 SQL 适配器的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="8ba56-103">Configure the SOAP action for the SQL adapter</span></span>
<span data-ttu-id="8ba56-104">若要对使用基于 WCF 的 SQL Server 执行任何操作[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]，您必须指定 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="8ba56-104">To perform any operation on SQL Server using the WCF-based [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)], you must specify a SOAP action.</span></span> <span data-ttu-id="8ba56-105">SOAP 操作进行通信的适配器应执行什么操作。</span><span class="sxs-lookup"><span data-stu-id="8ba56-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="8ba56-106">可以从指定的 SOAP 操作[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="8ba56-106">You can specify the SOAP action either from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="8ba56-107">但是，如果你指定的 SOAP 操作从这两个位置，你指定操作从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]将重写。</span><span class="sxs-lookup"><span data-stu-id="8ba56-107">However, if you specify the SOAP action from both locations, the action you specified from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] will be overridden.</span></span>  
  
 <span data-ttu-id="8ba56-108">有关指定 SOAP 操作的详细信息，请参阅[指定 WCF 发送适配器的 SOAP 操作](../../core/specifying-soap-actions-for-wcf-send-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba56-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>
  
## <a name="enter-the-soap-action-in-visual-studio"></a><span data-ttu-id="8ba56-109">在 Visual Studio 中输入的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="8ba56-109">Enter the SOAP action in Visual Studio</span></span>  
 <span data-ttu-id="8ba56-110">从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，你必须通过使用指定为业务流程的一部分的 SOAP 操作**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="8ba56-110">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="8ba56-111">在 BizTalk 业务流程，包括**表达式**通过拖动从形状**BizTalk 业务流程**工具箱。</span><span class="sxs-lookup"><span data-stu-id="8ba56-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="8ba56-112">双击**表达式**形状以打开 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="8ba56-112">Double-click the **Expression** shape to open BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="8ba56-113">在 BizTalk 表达式编辑器中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="8ba56-113">Specify the action in BizTalk Expression Editor.</span></span> <span data-ttu-id="8ba56-114">例如：</span><span class="sxs-lookup"><span data-stu-id="8ba56-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="TableOp/Insert/dbo/Employee"  
    ```  
  
     <span data-ttu-id="8ba56-115">有关详细信息**表达式**形状和 BizTalk 表达式编辑器，请参阅[如何创建表达式](../../core/how-to-create-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba56-115">For more information about the **Expression** shape and BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>
  
## <a name="enter-the-soap-action-from-the-biztalk-server-administration-console"></a><span data-ttu-id="8ba56-116">从 BizTalk Server 管理控制台中输入的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="8ba56-116">Enter the SOAP action from the BizTalk Server Administration console</span></span>  
 <span data-ttu-id="8ba56-117">从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，你可以指定的 SOAP 操作作为 WCF 自定义或 WCF SQL 端口配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="8ba56-117">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you can specify the SOAP action as part of the WCF-Custom or WCF-SQL port configuration.</span></span>  
  
### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="8ba56-118">输入 WCF 自定义端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="8ba56-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1.  <span data-ttu-id="8ba56-119">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="8ba56-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="8ba56-120">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="8ba56-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="8ba56-121">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="8ba56-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="8ba56-122">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="8ba56-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="8ba56-123">在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="8ba56-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="8ba56-124">在**操作**文本框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="8ba56-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="8ba56-125">你可以通过以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="8ba56-125">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="8ba56-126">**通过单个操作格式**。</span><span class="sxs-lookup"><span data-stu-id="8ba56-126">**By using the single action format**.</span></span> <span data-ttu-id="8ba56-127">如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="8ba56-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="8ba56-128">例如：</span><span class="sxs-lookup"><span data-stu-id="8ba56-128">For example:</span></span>  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
    -   <span data-ttu-id="8ba56-129">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="8ba56-129">**By using the action mapping format**.</span></span> <span data-ttu-id="8ba56-130">如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="8ba56-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="8ba56-131">例如，如果单个 WCF 自定义端口发送和接收 Op1 （若要在员工表中插入记录） 和 Op2 （若要更新员工表中的记录） 的消息，则可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="8ba56-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the Employee table) and Op2 (to update records in the Employee table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
          <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="8ba56-132">操作映射方法提供了更加灵活的指定一组操作，并因此启用属于不同的操作类型都通过相同端口的消息。</span><span class="sxs-lookup"><span data-stu-id="8ba56-132">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="8ba56-133">SOAP 操作的格式为每个操作不同。</span><span class="sxs-lookup"><span data-stu-id="8ba56-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="8ba56-134">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba56-134">For more information about the action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>
  
### <a name="enter-a-soap-action-for-the-wcf-sql-port"></a><span data-ttu-id="8ba56-135">输入 WCF SQL 端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="8ba56-135">Enter a SOAP action for the WCF-SQL port</span></span>  
  
1.  <span data-ttu-id="8ba56-136">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="8ba56-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="8ba56-137">添加到 WCF SQL 适配器[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="8ba56-137">Add the WCF-SQL adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="8ba56-138">有关说明，请参阅[将 SQL 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba56-138">For instructions, see [Adding the SQL Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-sql/adding-the-sql-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="8ba56-139">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="8ba56-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="8ba56-140">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="8ba56-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="8ba56-141">在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加了 WCF SQL 适配器，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="8ba56-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-SQL adapter you added earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="8ba56-142">在传输属性对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="8ba56-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="8ba56-143">在**操作**文本框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="8ba56-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="8ba56-144">你可以通过以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="8ba56-144">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="8ba56-145">**通过单个操作格式**。</span><span class="sxs-lookup"><span data-stu-id="8ba56-145">**By using the single action format**.</span></span> <span data-ttu-id="8ba56-146">如果 WCF SQL 端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="8ba56-146">Use this format if the WCF-SQL port sends and receive messages for a single operation.</span></span> <span data-ttu-id="8ba56-147">例如：</span><span class="sxs-lookup"><span data-stu-id="8ba56-147">For example:</span></span>  
  
        ```  
        TableOp/Insert/dbo/Employee  
        ```  
  
    -   <span data-ttu-id="8ba56-148">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="8ba56-148">**By using the action mapping format**.</span></span> <span data-ttu-id="8ba56-149">如果单个 WCF SQL 端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="8ba56-149">Use this format if a single WCF-SQL port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="8ba56-150">例如，如果单个 WCF SQL 端口发送和接收 Op1 （若要在员工表中插入记录） 和 Op2 （若要更新员工表中的记录） 的消息，则可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="8ba56-150">For example, if a single WCF-SQL port sends and receives messages for Op1 (to insert records in the Employee table) and Op2 (to update records in the Employee table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="TableOp/Insert/dbo/Employee" />  
          <Operation Name="Op2" Action="TableOp/Update/dbo/Employee" />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="8ba56-151">操作映射方法提供了更加灵活的指定一组操作，并因此启用属于不同的操作类型都通过相同端口的消息。</span><span class="sxs-lookup"><span data-stu-id="8ba56-151">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="8ba56-152">SOAP 操作的格式为每个操作不同。</span><span class="sxs-lookup"><span data-stu-id="8ba56-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="8ba56-153">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md)。</span><span class="sxs-lookup"><span data-stu-id="8ba56-153">For more information about the action format for each operation, see [Messages and message schemas](messages-and-message-schemas-for-biztalk-adapter-for-sql-server.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8ba56-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8ba56-154">See Also</span></span>  
[<span data-ttu-id="8ba56-155">开发具有 SQL 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="8ba56-155">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)