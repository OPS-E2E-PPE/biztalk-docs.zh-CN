---
title: 在 BizTalk 中配置 Oracle 数据库的 SOAP 操作 |Microsoft Docs
description: 在 Visual Studio 中，输入 SOAP 操作或使用 BizTalk 适配器包 (BAP) 中的 WCF 自定义或 Wcf-oracledb 适配器
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d0d21cca-3907-4f99-af76-c1e7286e1bcf
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 62bb4567a73411c28ba68010b7def22a121ddda2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377004"
---
# <a name="configure-the-soap-action-for-oracle-database"></a><span data-ttu-id="566b8-103">配置 Oracle 数据库的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="566b8-103">Configure the SOAP action for Oracle Database</span></span>
<span data-ttu-id="566b8-104">若要完成对使用基于 WCF 的 Oracle 数据库的任何操作[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]，适配器的用户必须输入 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="566b8-104">To complete any operation on the Oracle database using the WCF-based [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)], adapter users must enter a SOAP action.</span></span> <span data-ttu-id="566b8-105">SOAP 操作与适配器通信应完成的操作。</span><span class="sxs-lookup"><span data-stu-id="566b8-105">The SOAP action communicates to the adapter what action should be completed.</span></span> <span data-ttu-id="566b8-106">您可以输入在设计时或在运行时的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="566b8-106">You can enter the SOAP action either at design time or at run time.</span></span> <span data-ttu-id="566b8-107">但是，如果输入的 SOAP 操作这两个在设计时和运行时，会覆盖在设计时输入的操作。</span><span class="sxs-lookup"><span data-stu-id="566b8-107">However, if you enter the SOAP action both at design time and run time, the action you enter at design time is overridden.</span></span>  
  
 <span data-ttu-id="566b8-108">有关指定 SOAP 操作的详细信息，请参阅[对于 WCF 发送适配器指定 SOAP 操作](../../core/specifying-soap-actions-for-wcf-send-adapters.md)。</span><span class="sxs-lookup"><span data-stu-id="566b8-108">For more information about specifying SOAP action, see [Specifying SOAP Actions for WCF Send Adapters](../../core/specifying-soap-actions-for-wcf-send-adapters.md).</span></span>  
  
## <a name="enter-soap-action-from-visual-studio"></a><span data-ttu-id="566b8-109">从 Visual Studio 输入 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="566b8-109">Enter SOAP Action from Visual Studio</span></span>  
 <span data-ttu-id="566b8-110">从 Visual Studio 中，您必须指定 SOAP 操作作为业务流程的一部分通过使用**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="566b8-110">From Visual Studio, you must specify the SOAP action as part of the orchestration by using an **Expression** shape.</span></span>  
  
1.  <span data-ttu-id="566b8-111">在 BizTalk 业务流程，包括**表达式**通过将其从拖动形状**BizTalk 业务流程**工具箱。</span><span class="sxs-lookup"><span data-stu-id="566b8-111">In the BizTalk orchestration, include an **Expression** shape by dragging it from the **BizTalk Orchestration** toolbox.</span></span>  
  
2.  <span data-ttu-id="566b8-112">双击**表达式**形状以打开 BizTalk 表达式编辑器。</span><span class="sxs-lookup"><span data-stu-id="566b8-112">Double-click the **Expression** shape to open the BizTalk Expression Editor.</span></span>  
  
3.  <span data-ttu-id="566b8-113">在 BizTalk 表达式编辑器中指定的操作。</span><span class="sxs-lookup"><span data-stu-id="566b8-113">Specify the action in the BizTalk Expression Editor.</span></span> <span data-ttu-id="566b8-114">例如：</span><span class="sxs-lookup"><span data-stu-id="566b8-114">For example:</span></span>  
  
    ```
    OutboundMessage(WCF.Action)="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert"  
    ```  
  
     <span data-ttu-id="566b8-115">有关详细信息**表达式**形状和 BizTalk 表达式编辑器中，请参阅[如何创建表达式](../../core/how-to-create-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="566b8-115">For more information about **Expression** shape and the BizTalk Expression Editor, see [How to Create Expressions](../../core/how-to-create-expressions.md).</span></span>  
  
## <a name="enter-soap-action-from-biztalk-server-administration"></a><span data-ttu-id="566b8-116">从 BizTalk Server 管理输入 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="566b8-116">Enter SOAP Action from BizTalk Server Administration</span></span>  
 <span data-ttu-id="566b8-117">从 BizTalk Server 管理控制台中，您必须指定 SOAP 操作作为 WCF 自定义或 Wcf-oracledb 端口配置的一部分。</span><span class="sxs-lookup"><span data-stu-id="566b8-117">From the BizTalk Server Administration console, you must specify the SOAP action as part of the WCF-Custom or WCF-OracleDB port configuration.</span></span> 

#### <a name="enter-a-soap-action-for-the-wcf-custom-port"></a><span data-ttu-id="566b8-118">输入 WCF 自定义端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="566b8-118">Enter a SOAP action for the WCF-Custom port</span></span>  
 
  
1. <span data-ttu-id="566b8-119">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="566b8-119">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="566b8-120">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用的程序**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="566b8-120">In the console tree, expand **BizTalk Group**, then expand **Applications**, then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="566b8-121">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="566b8-121">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
3. <span data-ttu-id="566b8-122">在端口属性对话框中，从**类型**下拉列表中，选择**WCF 自定义**，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="566b8-122">In the port properties dialog box, from the **Type** drop-down list, select **WCF-Custom**, and then click **Configure**.</span></span>  
  
4. <span data-ttu-id="566b8-123">在中**Wcf-custom 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="566b8-123">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
5. <span data-ttu-id="566b8-124">在中**操作**文字框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="566b8-124">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="566b8-125">您可以按以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="566b8-125">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="566b8-126">**通过使用单一操作格式**。</span><span class="sxs-lookup"><span data-stu-id="566b8-126">**By using the single action format**.</span></span> <span data-ttu-id="566b8-127">如果 WCF 自定义端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="566b8-127">Use this format if the WCF-Custom port sends and receive messages for a single operation.</span></span> <span data-ttu-id="566b8-128">例如：</span><span class="sxs-lookup"><span data-stu-id="566b8-128">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   <span data-ttu-id="566b8-129">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="566b8-129">**By using the action mapping format**.</span></span> <span data-ttu-id="566b8-130">如果单个 WCF 自定义端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="566b8-130">Use this format if a single WCF-Custom port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="566b8-131">例如，如果单个 WCF 自定义端口发送和接收消息 （若要在 EMP 表中插入记录） 的 Op1 和 Op2 （若要更新的 EMP 表中的记录），可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="566b8-131">For example, if a single WCF-Custom port sends and receives messages for Op1 (to insert records in the EMP table) and Op2 (to update records in the EMP table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="566b8-132">这种方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过同一端口。</span><span class="sxs-lookup"><span data-stu-id="566b8-132">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="566b8-133">SOAP 操作的格式是不同的每个操作。</span><span class="sxs-lookup"><span data-stu-id="566b8-133">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="566b8-134">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="566b8-134">For more information about action format for each operation, see [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>  
  
#### <a name="enter-a-soap-action-for-the-wcf-oracledb-port"></a><span data-ttu-id="566b8-135">输入 Wcf-oracledb 端口的 SOAP 操作</span><span class="sxs-lookup"><span data-stu-id="566b8-135">Enter a SOAP action for the WCF-OracleDB port</span></span>  
  
1. <span data-ttu-id="566b8-136">启动[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="566b8-136">Start the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  
  
2. <span data-ttu-id="566b8-137">将 Wcf-oracledb 适配器添加到 BizTalk Server 管理控制台。</span><span class="sxs-lookup"><span data-stu-id="566b8-137">Add the WCF-OracleDB adapter to the BizTalk Server Administration console.</span></span> <span data-ttu-id="566b8-138">有关说明，请参阅[将 Oracle 数据库适配器添加到 BizTalk Server 管理控制台](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md)。</span><span class="sxs-lookup"><span data-stu-id="566b8-138">For instructions, see [Adding the Oracle Database Adapter to BizTalk Server Administration Console](../../adapters-and-accelerators/adapter-oracle-database/adding-the-oracle-database-adapter-to-biztalk-server-administration-console.md).</span></span>  
  
3. <span data-ttu-id="566b8-139">在控制台树中，展开**BizTalk 组**，然后展开**应用程序**，然后展开要在其下创建一个端口，然后单击应用的程序**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="566b8-139">In the console tree, expand **BizTalk Group**, then expand **Applications**, then expand the application under which you want to create a port, and then click **Send Ports**.</span></span> <span data-ttu-id="566b8-140">在右窗格中，您可以选择创建一个端口或选择现有端口。</span><span class="sxs-lookup"><span data-stu-id="566b8-140">In the right pane, you can choose to create a port or select an existing port.</span></span>  
  
4. <span data-ttu-id="566b8-141">在端口属性对话框中，从**类型**下拉列表中，选择你前面，添加的 Wcf-oracledb 端口，然后单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="566b8-141">In the port properties dialog box, from the **Type** drop-down list, select the WCF-OracleDB port you added earlier, and then click **Configure**.</span></span>  
  
5. <span data-ttu-id="566b8-142">在中**Wcf-custom 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="566b8-142">In the **WCF-Custom Transport Properties** dialog box, click the **General** tab.</span></span>  
  
6. <span data-ttu-id="566b8-143">在中**操作**文字框中，指定该操作的 SOAP 操作。</span><span class="sxs-lookup"><span data-stu-id="566b8-143">In the **Action** text box, specify the SOAP action for the operation.</span></span> <span data-ttu-id="566b8-144">您可以按以下方式指定的操作：</span><span class="sxs-lookup"><span data-stu-id="566b8-144">You can specify the action in the following ways:</span></span>  
  
   -   <span data-ttu-id="566b8-145">**通过使用单一操作格式**。</span><span class="sxs-lookup"><span data-stu-id="566b8-145">**By using the single action format**.</span></span> <span data-ttu-id="566b8-146">如果 Wcf-oracledb 端口发送和接收消息的单个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="566b8-146">Use this format if the WCF-OracleDB port sends and receive messages for a single operation.</span></span> <span data-ttu-id="566b8-147">例如：</span><span class="sxs-lookup"><span data-stu-id="566b8-147">For example:</span></span>  
  
       ```  
       http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert  
       ```  
  
   -   <span data-ttu-id="566b8-148">**通过使用操作映射格式**。</span><span class="sxs-lookup"><span data-stu-id="566b8-148">**By using the action mapping format**.</span></span> <span data-ttu-id="566b8-149">如果单个 Wcf-oracledb 端口发送和接收消息的多个操作，请使用此格式。</span><span class="sxs-lookup"><span data-stu-id="566b8-149">Use this format if a single WCF-OracleDB port sends and receives messages for more than one operation.</span></span> <span data-ttu-id="566b8-150">例如，如果单个 Wcf-oracledb 端口发送和接收消息 （若要在 EMP 表中插入记录） 的 Op1 和 Op2 （若要更新的 EMP 表中的记录），可以按以下方式指定的 SOAP 操作：</span><span class="sxs-lookup"><span data-stu-id="566b8-150">For example, if a single WCF-OracleDB port sends and receives messages for Op1 (to insert records in the EMP table) and Op2 (to update records in the EMP table), the SOAP action can be specified in the following manner:</span></span>  
  
       ```  
       <BtsActionMapping>  
         <Operation Name="Op1" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Insert" />  
         <Operation Name="Op2" Action="http://Microsoft.LobServices.OracleDB/2007/03/SCOTT/Table/EMP/Update " />  
       </BtsActionMapping>  
       ```  
  
        <span data-ttu-id="566b8-151">这种方法提供了更加灵活的指定一组操作并因此启用消息属于不同的操作类型都通过同一端口。</span><span class="sxs-lookup"><span data-stu-id="566b8-151">This approach provides greater flexibility in terms of specifying a set of actions and hence enabling messages belonging to different action types to flow through the same port.</span></span>  
  
        <span data-ttu-id="566b8-152">SOAP 操作的格式是不同的每个操作。</span><span class="sxs-lookup"><span data-stu-id="566b8-152">The format for the SOAP action is different for each operation.</span></span> <span data-ttu-id="566b8-153">有关每个操作的操作格式的详细信息，请参阅[消息和消息架构](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="566b8-153">For more information about action format for each operation, see [Messages and Message Schemas](messages-and-message-schemas-for-biztalk-adapter-for-oracle-database.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="566b8-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="566b8-154">See Also</span></span>  
[<span data-ttu-id="566b8-155">若要开发与 Oracle 数据库的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="566b8-155">Building Blocks to develop BizTalk Applications with Oracle Database</span></span>](../../adapters-and-accelerators/adapter-oracle-database/building-blocks-to-develop-biztalk-applications-with-oracle-database.md)