---
title: 在 BizTalk Server 中配置适用于 Oracle E-business Suite 的 SOAP 操作 |Microsoft Docs
description: 在 Visual Studio 中，输入 SOAP 操作或使用 BizTalk 适配器包 (BAP) 中的 WCF 自定义或 Wcf-oracleebs 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ca799d96-66e4-4d4e-a632-cb5505e999b4
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 29a829ced566e5a969cce5257a64da0999cce7be
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36968102"
---
# <a name="configure-the-soap-action-for-oracle-e-business-suite"></a><span data-ttu-id="ec37a-103">配置用于 Oracle E-business Suite 的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="ec37a-103">Configure the SOAP action for Oracle E-Business Suite</span></span>
<span data-ttu-id="ec37a-104">若要执行任何操作上使用基于 WCF 的 Oracle E-business Suite [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]，你必须指定 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="ec37a-104">To perform any operation on Oracle E-Business Suite using the WCF-based [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)], you must specify a SOAP action.</span></span> <span data-ttu-id="ec37a-105">SOAP 操作通信适配器应执行什么操作。</span><span class="sxs-lookup"><span data-stu-id="ec37a-105">The SOAP action communicates to the adapter what action should be performed.</span></span> <span data-ttu-id="ec37a-106">可以从指定的 SOAP 操作[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]或从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ec37a-106">You can specify the SOAP action either from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] or from the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="ec37a-107">但是，如果指定的 SOAP 操作从这两个位置，指定的操作，从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]被重写。</span><span class="sxs-lookup"><span data-stu-id="ec37a-107">However, if you specify the SOAP action from both locations, the action you specified from [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)] is overridden.</span></span>  
  
 <span data-ttu-id="ec37a-108">有关指定 SOAP 操作的详细信息，请参阅[对于 WCF 发送适配器指定 SOAP 操作](../../core/specifying-soap-actions-for-wcf-send-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="ec37a-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>  
  
## <a name="enter-soap-action-from-visual-studio"></a><span data-ttu-id="ec37a-109">从 Visual Studio 输入 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="ec37a-109">Enter SOAP Action from Visual Studio</span></span>  
 <span data-ttu-id="ec37a-110">从[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]，必须使用作为业务流程的一部分指定的 SOAP 操作**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="ec37a-110">From [!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)], you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="ec37a-111">在 BizTalk 业务流程，包括**表达式**通过将其从拖动形状**BizTalk 业务流程**工具箱。</span><span class="sxs-lookup"><span data-stu-id="ec37a-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="ec37a-112">双击**表达式**形状以打开 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="ec37a-112">Double-click the **Expression** shape to open BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="ec37a-113">在 BizTalk 表达式编辑器中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="ec37a-113">Specify the action in BizTalk Expression Editor.</span></span> <span data-ttu-id="ec37a-114">例如：</span><span class="sxs-lookup"><span data-stu-id="ec37a-114">For example:</span></span>  
  
    ```  
    OutboundMessage(WCF.Action)="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY"  
    ```  
  
     <span data-ttu-id="ec37a-115">有关详细信息**表达式**形状和 BizTalk 表达式编辑器，请参阅[如何创建表达式](../../core/how-to-create-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="ec37a-115">For more information about the **Expression** shape and BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a><span data-ttu-id="ec37a-116">从 BizTalk Server 管理输入 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="ec37a-116">Enter SOAP Action from BizTalk Server Administration</span></span>  
 <span data-ttu-id="ec37a-117">从[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台中，您必须指定 SOAP 操作作为 WCF 自定义或 WCF OracleEBS 端口配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="ec37a-117">From the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console, you must specify the SOAP action as part of the WCF-Custom or WCF-OracleEBS port configuration.</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="ec37a-118">输入 WCF 自定义端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="ec37a-118">Enter a SOAP action for the WCF-Custom port</span></span>  
  
1. <span data-ttu-id="ec37a-119">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ec37a-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="ec37a-120">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="ec37a-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="ec37a-121">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="ec37a-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3. <span data-ttu-id="ec37a-122">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="ec37a-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="ec37a-123">在中**Wcf-custom 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ec37a-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5. <span data-ttu-id="ec37a-124">在中**操作**文字框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="ec37a-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="ec37a-125">您可以按以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="ec37a-125">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="ec37a-126">**通过使用单一操作格式**。</span><span class="sxs-lookup"><span data-stu-id="ec37a-126">**By using the single action format**.</span></span> <span data-ttu-id="ec37a-127">如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="ec37a-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="ec37a-128">例如：</span><span class="sxs-lookup"><span data-stu-id="ec37a-128">For example:</span></span>  
  
       ```  
       InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
       ```  
  
   -   <span data-ttu-id="ec37a-129">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="ec37a-129">**By using the action mapping format**.</span></span> <span data-ttu-id="ec37a-130">如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="ec37a-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="ec37a-131">例如，如果单个 WCF 自定义端口发送和接收消息 （若要在 GL_ALLOC_HISTORY 表中插入记录） 的 Op1 和 Op2 （为了更新 GL_ALLOC_HISTORY 表中的记录），可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="ec37a-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the GL_ALLOC_HISTORY table) and Op2 (to update records in the GL_ALLOC_HISTORY table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
         <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="ec37a-132">操作映射方法提供了更加灵活的指定一组操作，并因此启用属于不同的操作类型都通过相同端口的消息。</span><span class="sxs-lookup"><span data-stu-id="ec37a-132">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="ec37a-133">SOAP 操作的格式是不同的每个操作。</span><span class="sxs-lookup"><span data-stu-id="ec37a-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="ec37a-134">有关每个操作的操作格式的详细信息，请参阅[的消息和消息架构 Oracle EBS 适配器](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="ec37a-134">For more information about the action format for each operation, see [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>
  
#### <a name="enter-a-soap-action-for-the-wcf-oracleebs-port"></a><span data-ttu-id="ec37a-135">输入 WCF OracleEBS 端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="ec37a-135">Enter a SOAP action for the WCF-OracleEBS port</span></span>  
  
1. <span data-ttu-id="ec37a-136">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ec37a-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="ec37a-137">添加 WCF OracleEBS 适配器添加到[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="ec37a-137">Add the WCF-OracleEBS adapter to the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="ec37a-138">有关说明，请参阅[将 Oracle E-business Suite 适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="ec37a-138">For instructions, see [Adding the Oracle E-Business Suite Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-ebs/add-the-oracle-ebs-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="ec37a-139">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="ec37a-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, and then click **Send Ports**.</span></span> <span data-ttu-id="ec37a-140">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="ec37a-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4. <span data-ttu-id="ec37a-141">在端口属性对话框中，从**类型**下拉列表中，选择 WCF OracleEBS 适配器添加更早版本，然后依次**配置**。</span><span class="sxs-lookup"><span data-stu-id="ec37a-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleEBS adapter you add earlier, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="ec37a-142">在传输属性对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="ec37a-142">In the transport properties dialog box, click the **General** tab.</span></span>  
  
6. <span data-ttu-id="ec37a-143">在中**操作**文字框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="ec37a-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="ec37a-144">您可以按以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="ec37a-144">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="ec37a-145">**通过使用单一操作格式**。</span><span class="sxs-lookup"><span data-stu-id="ec37a-145">**By using the single action format**.</span></span> <span data-ttu-id="ec37a-146">如果 WCF OracleEBS 端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="ec37a-146">Use this format if the WCF-OracleEBS port sends and receive messages for a single operation.</span></span> <span data-ttu-id="ec37a-147">例如：</span><span class="sxs-lookup"><span data-stu-id="ec37a-147">For example:</span></span>  
  
       ```  
       InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY  
       ```  
  
   -   <span data-ttu-id="ec37a-148">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="ec37a-148">**By using the action mapping format**.</span></span> <span data-ttu-id="ec37a-149">如果单个 WCF OracleEBS 端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="ec37a-149">Use this format if a single WCF-OracleEBS port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="ec37a-150">例如，如果单个 WCF OracleEBS 端口发送和接收消息 （若要在 GL_ALLOC_HISTORY 表中插入记录） 的 Op1 和 Op2 （为了更新 GL_ALLOC_HISTORY 表中的记录），可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="ec37a-150">For example, if a single WCF-OracleEBS port sends and receives messages for Op1 (to insert records in the GL_ALLOC_HISTORY table) and Op2 (to update records in the GL_ALLOC_HISTORY table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="InterfaceTables/Insert/SQLGL/GL/GL_ALLOC_HISTORY" />  
         <Operation Name="Op2" Action="InterfaceTables/Update/SQLGL/GL/GL_ALLOC_HISTORY " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="ec37a-151">操作映射方法提供了更加灵活的指定一组操作，并因此启用属于不同的操作类型都通过相同端口的消息。</span><span class="sxs-lookup"><span data-stu-id="ec37a-151">The action mapping approach provides greater flexibility in terms of specifying a set of actions, and hence enabling messages that belong to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="ec37a-152">SOAP 操作的格式是不同的每个操作。</span><span class="sxs-lookup"><span data-stu-id="ec37a-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="ec37a-153">有关每个操作的操作格式的详细信息，请参阅[的消息和消息架构 Oracle EBS 适配器](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md)。</span><span class="sxs-lookup"><span data-stu-id="ec37a-153">For more information about the action format for each operation, see [Messages and Message Schemas for Oracle EBS adapter](messages-and-message-schemas-for-biztalk-adapter-for-oracle-e-business-suite.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ec37a-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec37a-154">See Also</span></span>  
 [<span data-ttu-id="ec37a-155">若要创建 Oracle E-business Suite 的应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="ec37a-155">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)