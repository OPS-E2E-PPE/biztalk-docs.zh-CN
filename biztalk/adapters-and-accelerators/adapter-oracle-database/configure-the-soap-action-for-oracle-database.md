---
title: "在 BizTalk 中配置 Oracle 数据库的 SOAP 操作 |Microsoft 文档"
description: "在 Visual Studio 中，输入 SOAP 操作或使用 BizTalk 适配器包 (BAP) 中的 WCF 自定义或 WCF OracleDB 适配器"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d0d21cca-3907-4f99-af76-c1e7286e1bcf
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2577a221385cdef2e210798b3e8170433ff0e48
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="configure-the-soap-action-for-oracle-database"></a><span data-ttu-id="19ede-103">配置 Oracle 数据库的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="19ede-103">Configure the SOAP action for Oracle Database</span></span>
<span data-ttu-id="19ede-104">若要完成针对使用基于 WCF 的 Oracle 数据库的任何操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，适配器用户必须输入 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="19ede-104">To complete any operation on the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], adapter users must enter a SOAP action.</span></span> <span data-ttu-id="19ede-105">SOAP 操作进行通信的适配器应完成什么操作。</span><span class="sxs-lookup"><span data-stu-id="19ede-105">The SOAP action communicates to the adapter what action should be completed.</span></span> <span data-ttu-id="19ede-106">你可以输入在设计时或在运行时的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="19ede-106">You can enter the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="19ede-107">但是，如果输入的 SOAP 操作这两个在设计时和运行时，在设计时输入的操作被重写。</span><span class="sxs-lookup"><span data-stu-id="19ede-107">However, if you enter the SOAP action both at design time and run time, the action you enter at design time is overridden.</span></span>  
  
 <span data-ttu-id="19ede-108">有关指定 SOAP 操作的详细信息，请参阅[指定 WCF 发送适配器的 SOAP 操作](../../core/specifying-soap-actions-for-wcf-send-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="19ede-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>  
  
## <a name="enter-soap-action-from-visual-studio"></a><span data-ttu-id="19ede-109">从 Visual Studio 中输入 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="19ede-109">Enter SOAP Action from Visual Studio</span></span>  
 <span data-ttu-id="19ede-110">从 Visual Studio 中，你必须指定的 SOAP 操作作为业务流程的一部分使用**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="19ede-110">From Visual Studio, you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="19ede-111">在 BizTalk 业务流程，包括**表达式**通过拖动从形状**BizTalk 业务流程**工具箱。</span><span class="sxs-lookup"><span data-stu-id="19ede-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="19ede-112">双击**表达式**形状以打开 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="19ede-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="19ede-113">在 BizTalk 表达式编辑器中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="19ede-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="19ede-114">例如：</span><span class="sxs-lookup"><span data-stu-id="19ede-114">For example:</span></span>  
  
    ```
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
    ```  
  
     <span data-ttu-id="19ede-115">有关详细信息**表达式**形状和 BizTalk 表达式编辑器，请参阅[如何创建表达式](../../core/how-to-create-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="19ede-115">For more information about **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a><span data-ttu-id="19ede-116">从 BizTalk Server 管理输入 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="19ede-116">Enter SOAP Action from BizTalk Server Administration</span></span>  
 <span data-ttu-id="19ede-117">从 BizTalk Server 管理控制台中，你必须指定的 SOAP 操作作为 WCF 自定义或 WCF OracleDB 端口配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="19ede-117">From the BizTalk Server Administration console, you must specify the SOAP action as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span> 

#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="19ede-118">输入 WCF 自定义端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="19ede-118">Enter a SOAP action for the WCF-Custom port</span></span>  
 
  
1.  <span data-ttu-id="19ede-119">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="19ede-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="19ede-120">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用的程序**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="19ede-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="19ede-121">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="19ede-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3.  <span data-ttu-id="19ede-122">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="19ede-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4.  <span data-ttu-id="19ede-123">在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="19ede-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5.  <span data-ttu-id="19ede-124">在**操作**文本框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="19ede-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="19ede-125">你可以通过以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="19ede-125">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="19ede-126">**通过单个操作格式**。</span><span class="sxs-lookup"><span data-stu-id="19ede-126">**By using the single action format**.</span></span> <span data-ttu-id="19ede-127">如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="19ede-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="19ede-128">例如：</span><span class="sxs-lookup"><span data-stu-id="19ede-128">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
        ```  
  
    -   <span data-ttu-id="19ede-129">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="19ede-129">**By using the action mapping format**.</span></span> <span data-ttu-id="19ede-130">如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="19ede-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="19ede-131">例如，如果单个 WCF 自定义端口发送和接收 Op1 （若要在 EMP 表中插入记录） 和 Op2 （若要更新 EMP 表中的记录） 的消息，则可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="19ede-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the EMP table) and Op2 (to update records in the EMP table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="19ede-132">此方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过相同端口。</span><span class="sxs-lookup"><span data-stu-id="19ede-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="19ede-133">SOAP 操作的格式为每个操作不同。</span><span class="sxs-lookup"><span data-stu-id="19ede-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="19ede-134">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="19ede-134">For more information about action format for each operation, see [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-oracledb-port"></a><span data-ttu-id="19ede-135">输入 WCF OracleDB 端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="19ede-135">Enter a SOAP action for the WCF-OracleDB port</span></span>  
  
1.  <span data-ttu-id="19ede-136">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="19ede-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2.  <span data-ttu-id="19ede-137">将 WCF OracleDB 适配器添加到 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="19ede-137">Add the WCF-OracleDB adapter to the BizTalk Server Administration console.</span></span> <span data-ttu-id="19ede-138">有关说明，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="19ede-138">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3.  <span data-ttu-id="19ede-139">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开你要在其下创建一个端口，然后单击应用的程序**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="19ede-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="19ede-140">在右窗格中，你可以选择创建一个端口或选择现有的端口。</span><span class="sxs-lookup"><span data-stu-id="19ede-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4.  <span data-ttu-id="19ede-141">在端口属性对话框中，从**类型**下拉列表中，选择更早版本，添加的 WCF OracleDB 端口，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="19ede-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleDB port you added earlier, and then click **Configure**.</span></span>  
  
5.  <span data-ttu-id="19ede-142">在**WCF 自定义传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="19ede-142">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
6.  <span data-ttu-id="19ede-143">在**操作**文本框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="19ede-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="19ede-144">你可以通过以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="19ede-144">You can specify the action in the following ways:</span></span>  
  
    -   <span data-ttu-id="19ede-145">**通过单个操作格式**。</span><span class="sxs-lookup"><span data-stu-id="19ede-145">**By using the single action format**.</span></span> <span data-ttu-id="19ede-146">如果 WCF OracleDB 端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="19ede-146">Use this format if the WCF-OracleDB port sends and receive messages for a single operation.</span></span> <span data-ttu-id="19ede-147">例如：</span><span class="sxs-lookup"><span data-stu-id="19ede-147">For example:</span></span>  
  
        ```  
        http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
        ```  
  
    -   <span data-ttu-id="19ede-148">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="19ede-148">**By using the action mapping format**.</span></span> <span data-ttu-id="19ede-149">如果单个 WCF OracleDB 端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="19ede-149">Use this format if a single WCF-OracleDB port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="19ede-150">例如，如果单个 WCF OracleDB 端口发送和接收 Op1 （若要在 EMP 表中插入记录） 和 Op2 （若要更新 EMP 表中的记录） 的消息，则可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="19ede-150">For example, if a single WCF-OracleDB port sends and receives messages for Op1 (to insert records in the EMP table) and Op2 (to update records in the EMP table), the SOAP action can be specified in the following manner:</span></span>  
  
        ```  
        <BtsActionMapping>  
          <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
          <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
        </BtsActionMapping>  
        ```  
  
         <span data-ttu-id="19ede-151">此方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过相同端口。</span><span class="sxs-lookup"><span data-stu-id="19ede-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
         <span data-ttu-id="19ede-152">SOAP 操作的格式为每个操作不同。</span><span class="sxs-lookup"><span data-stu-id="19ede-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="19ede-153">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="19ede-153">For more information about action format for each operation, see [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="19ede-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19ede-154">See Also</span></span>  
[<span data-ttu-id="19ede-155">开发与 Oracle 数据库的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="19ede-155">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)