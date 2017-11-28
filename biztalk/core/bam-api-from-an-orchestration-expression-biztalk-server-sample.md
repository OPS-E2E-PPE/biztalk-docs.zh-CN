---
title: "BAM API 从 Orchestration 表达式 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, BAM
- examples, orchestrations
- BAM, examples
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: "23"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26b9cbc21eb93cad52a421b7df0912a37708978c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a><span data-ttu-id="57c18-102">业务流程表达式中的 BAM API（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="57c18-102">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>
<span data-ttu-id="57c18-103">此示例演示如何：</span><span class="sxs-lookup"><span data-stu-id="57c18-103">This sample demonstrates how to:</span></span>  
  
-   <span data-ttu-id="57c18-104">使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程表达式中的 BAM API。</span><span class="sxs-lookup"><span data-stu-id="57c18-104">Use the BAM API from a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration expression.</span></span>  
  
-   <span data-ttu-id="57c18-105">跟踪消息内部作为单独活动实例的重复项。</span><span class="sxs-lookup"><span data-stu-id="57c18-105">Track repeating items inside a message as separate activity instances.</span></span>  
  
-   <span data-ttu-id="57c18-106">在使用跟踪配置文件跟踪的 BAM 数据和使用 BAM API 跟踪的 BAM 数据之间创建关系。</span><span class="sxs-lookup"><span data-stu-id="57c18-106">Create a relationship between BAM data that is tracked by using a tracking profile, and BAM data tracked by using the BAM API.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="57c18-107">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="57c18-107">Where to Find This Sample</span></span>  
 <span data-ttu-id="57c18-108">你可以找到在此示例*\<示例路径 >*\BAM\BamFromExpression。</span><span class="sxs-lookup"><span data-stu-id="57c18-108">You can find this sample at *\<Samples Path>*\BAM\BamFromExpression.</span></span>  
  
 <span data-ttu-id="57c18-109">下表列出了本示例中的文件及其用途说明。</span><span class="sxs-lookup"><span data-stu-id="57c18-109">The following table lists the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="57c18-110">文件</span><span class="sxs-lookup"><span data-stu-id="57c18-110">File</span></span>|<span data-ttu-id="57c18-111">Description</span><span class="sxs-lookup"><span data-stu-id="57c18-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="57c18-112">BamDefinition.xls</span><span class="sxs-lookup"><span data-stu-id="57c18-112">BamDefinition.xls</span></span>|<span data-ttu-id="57c18-113">BAM 定义样式表。</span><span class="sxs-lookup"><span data-stu-id="57c18-113">BAM definition stylesheet.</span></span>|  
|<span data-ttu-id="57c18-114">BamDefinition.xml</span><span class="sxs-lookup"><span data-stu-id="57c18-114">BamDefinition.xml</span></span>|<span data-ttu-id="57c18-115">BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="57c18-115">BAM definition.</span></span>|  
|<span data-ttu-id="57c18-116">BamFromExpression.btproj</span><span class="sxs-lookup"><span data-stu-id="57c18-116">BamFromExpression.btproj</span></span>|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="57c18-117"> 跟踪文件项目。</span><span class="sxs-lookup"><span data-stu-id="57c18-117"> tracking file project.</span></span>|  
|<span data-ttu-id="57c18-118">BamFromExpression.sln</span><span class="sxs-lookup"><span data-stu-id="57c18-118">BamFromExpression.sln</span></span>|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]<span data-ttu-id="57c18-119"> 解决方案。</span><span class="sxs-lookup"><span data-stu-id="57c18-119"> solution.</span></span>|  
|<span data-ttu-id="57c18-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="57c18-120">Cleanup.bat</span></span>|<span data-ttu-id="57c18-121">用于取消部署本示例的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="57c18-121">Batch file to undeploy the sample.</span></span>|  
|<span data-ttu-id="57c18-122">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="57c18-122">InputMessage.xml</span></span>|<span data-ttu-id="57c18-123">输入消息。</span><span class="sxs-lookup"><span data-stu-id="57c18-123">Input message.</span></span>|  
|<span data-ttu-id="57c18-124">Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="57c18-124">Orchestration1.odx</span></span>|<span data-ttu-id="57c18-125">业务流程。</span><span class="sxs-lookup"><span data-stu-id="57c18-125">Orchestration.</span></span>|  
|<span data-ttu-id="57c18-126">PoSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="57c18-126">PoSchema.xsd</span></span>|<span data-ttu-id="57c18-127">采购订单架构。</span><span class="sxs-lookup"><span data-stu-id="57c18-127">Purchase order schema.</span></span>|  
|<span data-ttu-id="57c18-128">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="57c18-128">PropertySchema.xsd</span></span>|<span data-ttu-id="57c18-129">属性架构。</span><span class="sxs-lookup"><span data-stu-id="57c18-129">Property schema.</span></span>|  
|<span data-ttu-id="57c18-130">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="57c18-130">Setup.bat</span></span>|<span data-ttu-id="57c18-131">用于编译和部署本示例的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="57c18-131">Batch file to compile and deploy the sample.</span></span>|  
|<span data-ttu-id="57c18-132">QueryBam.sql</span><span class="sxs-lookup"><span data-stu-id="57c18-132">QueryBam.sql</span></span>|<span data-ttu-id="57c18-133">SQL 脚本</span><span class="sxs-lookup"><span data-stu-id="57c18-133">SQL script.</span></span>|  
  
## <a name="how-to-use-this-sample"></a><span data-ttu-id="57c18-134">如何使用本示例</span><span class="sxs-lookup"><span data-stu-id="57c18-134">How to Use This Sample</span></span>  
 <span data-ttu-id="57c18-135">使用以下过程创建跟踪配置文件，运行示例，并查看结果。</span><span class="sxs-lookup"><span data-stu-id="57c18-135">Use the following procedures to create the tracking profile, run the sample, and view the results.</span></span>  
  
#### <a name="to-create-the-tracking-profile"></a><span data-ttu-id="57c18-136">若要创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="57c18-136">To create the tracking profile</span></span>  
  
1.  <span data-ttu-id="57c18-137">打开命令提示符并运行*\<示例路径 >*\BAM\BAMFromExpression\Setup.bat。</span><span class="sxs-lookup"><span data-stu-id="57c18-137">Open a command prompt and run *\<Samples Path>*\BAM\BAMFromExpression\Setup.bat.</span></span> <span data-ttu-id="57c18-138">如果你使用的是 [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请以管理员身份打开命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="57c18-138">If you are using [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], open the command prompt as administrator.</span></span> <span data-ttu-id="57c18-139">Setup.bat 可初始化此示例的 BAM 基础结构，并部署 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="57c18-139">Setup.bat initializes the BAM infrastructure for this sample, and deploys the BAM activity.</span></span>  
  
2.  <span data-ttu-id="57c18-140">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**跟踪配置文件编辑器**。</span><span class="sxs-lookup"><span data-stu-id="57c18-140">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Tracking Profile Editor**.</span></span> <span data-ttu-id="57c18-141">如果你使用[!INCLUDE[btsWinVista](../includes/btswinvista-md.md)]或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，右键单击**跟踪配置文件编辑器**，然后单击**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="57c18-141">If you are using [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], right-click **Tracking Profile Editor** and then click **Run as administrator**.</span></span>  
  
3.  <span data-ttu-id="57c18-142">在左窗格中**跟踪配置文件编辑器**窗口中，单击**单击此处以导入 BAM 活动定义**。</span><span class="sxs-lookup"><span data-stu-id="57c18-142">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  
  
4.  <span data-ttu-id="57c18-143">在**BAM 活动定义名称**部分**导入 BAM 活动定义**对话框中，选择**FromExpressionPo**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="57c18-143">In the **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **FromExpressionPo**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="57c18-144">在右窗格中**跟踪配置文件编辑器**窗口中，单击**单击此处选择的事件源**。</span><span class="sxs-lookup"><span data-stu-id="57c18-144">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  
  
6.  <span data-ttu-id="57c18-145">在**程序集名称**部分**选择事件源父程序集**对话框中，选择**Microsoft.Samples.BizTalk.BamFromExpression**，然后单击**下一步**。</span><span class="sxs-lookup"><span data-stu-id="57c18-145">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamFromExpression**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="57c18-146">在**Orchestration 名称**部分**选择业务流程**对话框中，选择**BamFromExpression.Orchestration1**，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="57c18-146">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamFromExpression.Orchestration1**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="57c18-147">右键单击**Receive_1**形状，并依次**消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="57c18-147">Right-click the **Receive_1** shape, and then click **Message Payload Schema**.</span></span>  
  
9. <span data-ttu-id="57c18-148">展开**\<架构 >**，展开**PurchaseOrder**，展开**从**，然后拖动**PoID**到右窗格中**ActivityID**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="57c18-148">Expand **\<Schema>**, expand **PurchaseOrder**, expand **From**, and then drag **PoID** in the right pane to **ActivityID** in the left pane.</span></span>  
  
10. <span data-ttu-id="57c18-149">拖动右窗格中的以下元素，并将它们放到左窗格中已命名节点上：</span><span class="sxs-lookup"><span data-stu-id="57c18-149">Drag the following elements from the right pane, and drop them onto the named nodes in the left pane:</span></span>  
  
    |<span data-ttu-id="57c18-150">From</span><span class="sxs-lookup"><span data-stu-id="57c18-150">From</span></span>|<span data-ttu-id="57c18-151">若要</span><span class="sxs-lookup"><span data-stu-id="57c18-151">To</span></span>|  
    |----------|--------|  
    |<span data-ttu-id="57c18-152">Name</span><span class="sxs-lookup"><span data-stu-id="57c18-152">Name</span></span>|<span data-ttu-id="57c18-153">From</span><span class="sxs-lookup"><span data-stu-id="57c18-153">From</span></span>|  
    |<span data-ttu-id="57c18-154">State</span><span class="sxs-lookup"><span data-stu-id="57c18-154">State</span></span>|<span data-ttu-id="57c18-155">State</span><span class="sxs-lookup"><span data-stu-id="57c18-155">State</span></span>|  
    |<span data-ttu-id="57c18-156">City</span><span class="sxs-lookup"><span data-stu-id="57c18-156">City</span></span>|<span data-ttu-id="57c18-157">City</span><span class="sxs-lookup"><span data-stu-id="57c18-157">City</span></span>|  
    |<span data-ttu-id="57c18-158">Phone</span><span class="sxs-lookup"><span data-stu-id="57c18-158">Phone</span></span>|<span data-ttu-id="57c18-159">Phone</span><span class="sxs-lookup"><span data-stu-id="57c18-159">Phone</span></span>|  
    |<span data-ttu-id="57c18-160">总计</span><span class="sxs-lookup"><span data-stu-id="57c18-160">Total</span></span>|<span data-ttu-id="57c18-161">PoTotal</span><span class="sxs-lookup"><span data-stu-id="57c18-161">PoTotal</span></span>|  
  
11. <span data-ttu-id="57c18-162">单击文件夹图标带有箭头 (![使用文件夹和向上按钮 &#45; 箭头](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 以显示业务流程。</span><span class="sxs-lookup"><span data-stu-id="57c18-162">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) to display the orchestration.</span></span>  
  
12. <span data-ttu-id="57c18-163">拖动**Receive_1**到右窗格中的形状**Received**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="57c18-163">Drag the **Receive_1** shape in the right pane to **Received** in the left pane.</span></span>  
  
13. <span data-ttu-id="57c18-164">拖动**Send_1**到右窗格中的形状**发送**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="57c18-164">Drag the **Send_1** shape in the right pane to **Send** in the left pane.</span></span>  
  
14. <span data-ttu-id="57c18-165">保存跟踪配置文件到*\<示例路径 >*\BAM\BamFromExpression\ BamFromExpression.btt。</span><span class="sxs-lookup"><span data-stu-id="57c18-165">Save the tracking profile to *\<Samples Path>*\BAM\BamFromExpression\ BamFromExpression.btt.</span></span>  
  
15. <span data-ttu-id="57c18-166">上**工具**菜单上，单击**应用跟踪配置文件**。</span><span class="sxs-lookup"><span data-stu-id="57c18-166">On the **Tools** menu, click **Apply Tracking Profile**.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="57c18-167">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="57c18-167">To build and initialize this sample</span></span>  
  
-   <span data-ttu-id="57c18-168">部署 BamFromExpression.btt 跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="57c18-168">Deploy the BamFromExpression.btt tracking profile.</span></span> <span data-ttu-id="57c18-169">有关详细信息，请参阅[如何部署跟踪配置文件使用跟踪配置文件管理实用程序](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)。</span><span class="sxs-lookup"><span data-stu-id="57c18-169">For more information, see [How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md).</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="57c18-170">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="57c18-170">To run this sample</span></span>  
  
-   <span data-ttu-id="57c18-171">将文件复制*\<示例路径 >*到 \BamFromExpression\InputMessage.xml *\<示例路径 >*\BamFromExpression\Input。</span><span class="sxs-lookup"><span data-stu-id="57c18-171">Copy the file *\<Samples Path>*\BamFromExpression\InputMessage.xml to *\<Samples Path>*\BamFromExpression\Input.</span></span>  
  
     <span data-ttu-id="57c18-172">在大约 10 秒输出消息将出现在*\<示例路径 >*\BamFromExpression\Output。</span><span class="sxs-lookup"><span data-stu-id="57c18-172">In about 10 seconds the output message will appear in *\<Samples Path>*\BamFromExpression\Output.</span></span>  
  
#### <a name="to-view-the-bam-data"></a><span data-ttu-id="57c18-173">查看 BAM 数据的步骤</span><span class="sxs-lookup"><span data-stu-id="57c18-173">To view the BAM data</span></span>  
  
1.  <span data-ttu-id="57c18-174">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="57c18-174">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="57c18-175">在 SQL Server Management Studio，展开服务器，展开**数据库**，展开**BAMPrimaryImport**，然后展开**表**。</span><span class="sxs-lookup"><span data-stu-id="57c18-175">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="57c18-176">右键单击**dbo.bam_FromExpressionPo_Completed**，然后单击**打开表**。</span><span class="sxs-lookup"><span data-stu-id="57c18-176">Right-click **dbo.bam_FromExpressionPo_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="57c18-177">如果你使用[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]，单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="57c18-177">If you are using [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="57c18-178">将在右窗格中显示 bam_FromExpressionPo_Completed 表中的内容。</span><span class="sxs-lookup"><span data-stu-id="57c18-178">The contents of the bam_FromExpressionPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="57c18-179">具有活动 ID 123 的一行，表示包含在输入消息中 345 美元的采购订单。</span><span class="sxs-lookup"><span data-stu-id="57c18-179">The one row, which has an activity ID of 123, represents the purchase order for $345 that was contained in the input message.</span></span>  
  
4.  <span data-ttu-id="57c18-180">右键单击**dbo.bam_FromExpressionPoItem_Completed**，然后单击**打开表**。</span><span class="sxs-lookup"><span data-stu-id="57c18-180">Right-click **dbo.bam_FromExpressionPoItem_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="57c18-181">如果你使用[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]，单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="57c18-181">If you are using [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="57c18-182">将在右窗格中显示 bam_FromExpressionPoItem_Completed 表中的内容。</span><span class="sxs-lookup"><span data-stu-id="57c18-182">The contents of the bam_FromExpressionPoItem_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="57c18-183">两个行，它有活动 Id 123_0 和 123_1，表示该采购订单中的项： Flash MC 和红外的解码器。</span><span class="sxs-lookup"><span data-stu-id="57c18-183">The two rows, which have activity IDs 123_0 and 123_1, represent the items in the purchase order: Flash MC and Infrared Decoder.</span></span>  
  
5.  <span data-ttu-id="57c18-184">右键单击**dbo.bam_FromExpressionPoItem_CompletedRelationships**，然后单击**打开表**。</span><span class="sxs-lookup"><span data-stu-id="57c18-184">Right-click **dbo.bam_FromExpressionPoItem_CompletedRelationships**, and then click **Open Table**.</span></span> <span data-ttu-id="57c18-185">如果你使用[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]，单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="57c18-185">If you are using [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)], click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="57c18-186">将在右窗格中显示 bam_FromExpressionPoItem_CompletedRelationships 表中的内容。</span><span class="sxs-lookup"><span data-stu-id="57c18-186">The contents of the bam_FromExpressionPoItem_CompletedRelationships table are displayed in the right pane.</span></span> <span data-ttu-id="57c18-187">表中的每一行，都表示 FromExpressionPoItem 活动和 FromExpressionPo 活动之间的一种关系。</span><span class="sxs-lookup"><span data-stu-id="57c18-187">Each row in the table represents a relationship between a FromExpressionPoItem activity and a FromExpressionPo activity.</span></span> <span data-ttu-id="57c18-188">中的值**ActivityID**列是指 FromExpressionPoItem 活动的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="57c18-188">The value in the **ActivityID** column refers to the activity ID of the FromExpressionPoItem activity.</span></span> <span data-ttu-id="57c18-189">中的值**ReferenceData**列是指 FromExpressionPo 活动的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="57c18-189">The value in the **ReferenceData** column refers to the activity ID of the FromExpressionPo activity.</span></span> <span data-ttu-id="57c18-190">在这种情况下，这两个记录表示 Flash MC 和红外解码器项与 345 美元的采购订单相关。</span><span class="sxs-lookup"><span data-stu-id="57c18-190">In this case, the two records indicate that the Flash MC and Infrared Decoder items are associated with the purchase order for $345.</span></span>  
  
#### <a name="to-re-run-the-sample"></a><span data-ttu-id="57c18-191">重新运行该示例的步骤</span><span class="sxs-lookup"><span data-stu-id="57c18-191">To re-run the sample</span></span>  
  
1.  <span data-ttu-id="57c18-192">打开命令提示符并运行*\<示例路径 >*\BAM\BamFromExpression\Cleanup.bat 若要删除的跟踪配置文件和其他 BAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="57c18-192">Open a command prompt and run *\<Samples Path>*\BAM\BamFromExpression\Cleanup.bat to remove the tracking profile and other BAM infrastructure.</span></span> <span data-ttu-id="57c18-193">如果你使用的是 [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请以管理员身份打开命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="57c18-193">If you are using [!INCLUDE[btsWinVista](../includes/btswinvista-md.md)] or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], open the command prompt as administrator.</span></span>  
  
2.  <span data-ttu-id="57c18-194">运行*\<示例路径 >*\BAM\BamFromExpression\Setup.bat 编译该示例并将其部署。</span><span class="sxs-lookup"><span data-stu-id="57c18-194">Run *\<Samples Path>*\BAM\BamFromExpression\Setup.bat to compile the sample and deploy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c18-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57c18-195">See Also</span></span>  
 <span data-ttu-id="57c18-196">[业务活动监视 （BizTalk Server 示例文件夹中）](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="57c18-196">[Business Activity Monitoring (BizTalk Server Samples Folder)](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="57c18-197">活动关系</span><span class="sxs-lookup"><span data-stu-id="57c18-197">Activity Relationships</span></span>](../core/activity-relationships.md)