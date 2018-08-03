---
title: 从 Orchestration 表达式示例 BAM API |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 341bc333-9bfc-484c-b431-9a71f9188792
caps.latest.revision: 23
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5413940eaba97e6f68d5e068e26625f320e6e817
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
ms.locfileid: "29710980"
---
# <a name="bam-api-from-an-orchestration-expression-biztalk-server-sample"></a><span data-ttu-id="e8500-102">业务流程表达式中的 BAM API（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="e8500-102">BAM API from an Orchestration Expression (BizTalk Server Sample)</span></span>
<span data-ttu-id="e8500-103">此示例演示如何：</span><span class="sxs-lookup"><span data-stu-id="e8500-103">This sample demonstrates how to:</span></span>  
  
-   <span data-ttu-id="e8500-104">使用从 BizTalk Server 业务流程表达式 BAM API。</span><span class="sxs-lookup"><span data-stu-id="e8500-104">Use the BAM API from a BizTalk Server orchestration expression.</span></span>  
  
-   <span data-ttu-id="e8500-105">跟踪消息内部作为单独活动实例的重复项。</span><span class="sxs-lookup"><span data-stu-id="e8500-105">Track repeating items inside a message as separate activity instances.</span></span>  
  
-   <span data-ttu-id="e8500-106">在使用跟踪配置文件跟踪的 BAM 数据和使用 BAM API 跟踪的 BAM 数据之间创建关系。</span><span class="sxs-lookup"><span data-stu-id="e8500-106">Create a relationship between BAM data that is tracked by using a tracking profile, and BAM data tracked by using the BAM API.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="e8500-107">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="e8500-107">Where to Find This Sample</span></span>  
 <span data-ttu-id="e8500-108">你可以找到在此示例*\<示例路径\>* \BAM\BamFromExpression。</span><span class="sxs-lookup"><span data-stu-id="e8500-108">You can find this sample at *\<Samples Path\>* \BAM\BamFromExpression.</span></span>  
  
 <span data-ttu-id="e8500-109">下表列出了本示例中的文件及其用途说明。</span><span class="sxs-lookup"><span data-stu-id="e8500-109">The following table lists the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="e8500-110">文件</span><span class="sxs-lookup"><span data-stu-id="e8500-110">File</span></span>|<span data-ttu-id="e8500-111">Description</span><span class="sxs-lookup"><span data-stu-id="e8500-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="e8500-112">BamDefinition.xls</span><span class="sxs-lookup"><span data-stu-id="e8500-112">BamDefinition.xls</span></span>|<span data-ttu-id="e8500-113">BAM 定义样式表。</span><span class="sxs-lookup"><span data-stu-id="e8500-113">BAM definition stylesheet.</span></span>|  
|<span data-ttu-id="e8500-114">BamDefinition.xml</span><span class="sxs-lookup"><span data-stu-id="e8500-114">BamDefinition.xml</span></span>|<span data-ttu-id="e8500-115">BAM 定义。</span><span class="sxs-lookup"><span data-stu-id="e8500-115">BAM definition.</span></span>|  
|<span data-ttu-id="e8500-116">BamFromExpression.btproj</span><span class="sxs-lookup"><span data-stu-id="e8500-116">BamFromExpression.btproj</span></span>|<span data-ttu-id="e8500-117">跟踪文件项目的 visual Studio。</span><span class="sxs-lookup"><span data-stu-id="e8500-117">Visual Studio tracking file project.</span></span>|  
|<span data-ttu-id="e8500-118">BamFromExpression.sln</span><span class="sxs-lookup"><span data-stu-id="e8500-118">BamFromExpression.sln</span></span>|<span data-ttu-id="e8500-119">Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="e8500-119">Visual Studio solution.</span></span>|  
|<span data-ttu-id="e8500-120">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="e8500-120">Cleanup.bat</span></span>|<span data-ttu-id="e8500-121">用于取消部署本示例的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="e8500-121">Batch file to undeploy the sample.</span></span>|  
|<span data-ttu-id="e8500-122">InputMessage.xml</span><span class="sxs-lookup"><span data-stu-id="e8500-122">InputMessage.xml</span></span>|<span data-ttu-id="e8500-123">输入消息。</span><span class="sxs-lookup"><span data-stu-id="e8500-123">Input message.</span></span>|  
|<span data-ttu-id="e8500-124">Orchestration1.odx</span><span class="sxs-lookup"><span data-stu-id="e8500-124">Orchestration1.odx</span></span>|<span data-ttu-id="e8500-125">业务流程。</span><span class="sxs-lookup"><span data-stu-id="e8500-125">Orchestration.</span></span>|  
|<span data-ttu-id="e8500-126">PoSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="e8500-126">PoSchema.xsd</span></span>|<span data-ttu-id="e8500-127">采购订单架构。</span><span class="sxs-lookup"><span data-stu-id="e8500-127">Purchase order schema.</span></span>|  
|<span data-ttu-id="e8500-128">PropertySchema.xsd</span><span class="sxs-lookup"><span data-stu-id="e8500-128">PropertySchema.xsd</span></span>|<span data-ttu-id="e8500-129">属性架构。</span><span class="sxs-lookup"><span data-stu-id="e8500-129">Property schema.</span></span>|  
|<span data-ttu-id="e8500-130">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="e8500-130">Setup.bat</span></span>|<span data-ttu-id="e8500-131">用于编译和部署本示例的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="e8500-131">Batch file to compile and deploy the sample.</span></span>|  
|<span data-ttu-id="e8500-132">QueryBam.sql</span><span class="sxs-lookup"><span data-stu-id="e8500-132">QueryBam.sql</span></span>|<span data-ttu-id="e8500-133">SQL 脚本</span><span class="sxs-lookup"><span data-stu-id="e8500-133">SQL script.</span></span>|  
  
## <a name="create-the-tracking-profile"></a><span data-ttu-id="e8500-134">创建跟踪配置文件</span><span class="sxs-lookup"><span data-stu-id="e8500-134">Create the tracking profile</span></span>  
  
1.  <span data-ttu-id="e8500-135">打开命令提示符以管理员身份，并运行*\<示例路径\>* \BAM\BAMFromExpression\Setup.bat。</span><span class="sxs-lookup"><span data-stu-id="e8500-135">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\BAMFromExpression\Setup.bat.</span></span> <span data-ttu-id="e8500-136">Setup.bat 可初始化此示例的 BAM 基础结构，并部署 BAM 活动。</span><span class="sxs-lookup"><span data-stu-id="e8500-136">Setup.bat initializes the BAM infrastructure for this sample, and deploys the BAM activity.</span></span>  
  
2.  <span data-ttu-id="e8500-137">从你**程序** > **Microsoft BizTalk Server**，右键单击**跟踪配置文件编辑器**，和**以管理员身份运行**.</span><span class="sxs-lookup"><span data-stu-id="e8500-137">From your **Programs** > **Microsoft BizTalk Server**, right-click **Tracking Profile Editor**, and **Run as administrator**.</span></span>
  
3.  <span data-ttu-id="e8500-138">在左窗格中 **跟踪配置文件编辑器** 窗口中，单击 **单击此处以导入 BAM 活动定义**。</span><span class="sxs-lookup"><span data-stu-id="e8500-138">In the left pane of the **Tracking Profile Editor** window, click **Click here to import a BAM Activity Definition**.</span></span>  
  
4.  <span data-ttu-id="e8500-139">在 **BAM 活动定义名称** 部分 **导入 BAM 活动定义** 对话框中，选择 **FromExpressionPo**, ，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="e8500-139">In the **BAM Activity Definition Name** section of the **Import BAM Activity Definition** dialog box, select **FromExpressionPo**, and then click **OK**.</span></span>  
  
5.  <span data-ttu-id="e8500-140">在右窗格中 **跟踪配置文件编辑器** 窗口中，单击 **单击此处选择的事件源**。</span><span class="sxs-lookup"><span data-stu-id="e8500-140">In the right pane of the **Tracking Profile Editor** window, click **Click here to select an event source**.</span></span>  
  
6.  <span data-ttu-id="e8500-141">在 **程序集名称** 部分 **选择事件源父程序集** 对话框中，选择 **Microsoft.Samples.BizTalk.BamFromExpression**, ，然后单击 **下一步**。</span><span class="sxs-lookup"><span data-stu-id="e8500-141">In the **Assembly Name** section of the **Select Event Source Parent Assembly** dialog box, select **Microsoft.Samples.BizTalk.BamFromExpression**, and then click **Next**.</span></span>  
  
7.  <span data-ttu-id="e8500-142">在 **Orchestration 名称** 部分 **选择业务流程** 对话框中，选择 **BamFromExpression.Orchestration1**, ，然后单击 **确定**。</span><span class="sxs-lookup"><span data-stu-id="e8500-142">In the **Orchestration Name** section of the **Select Orchestration** dialog box, select **BamFromExpression.Orchestration1**, and then click **OK**.</span></span>  
  
8.  <span data-ttu-id="e8500-143">右键单击 **Receive_1** 形状，并依次 **消息负载架构**。</span><span class="sxs-lookup"><span data-stu-id="e8500-143">Right-click the **Receive_1** shape, and then click **Message Payload Schema**.</span></span>  
  
9. <span data-ttu-id="e8500-144">展开**\<架构\>**，展开**PurchaseOrder**，展开**从**，然后拖动**PoID**方窗格**ActivityID**的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="e8500-144">Expand **\<Schema\>**, expand **PurchaseOrder**, expand **From**, and then drag **PoID** in the right pane to **ActivityID** in the left pane.</span></span>  
  
10. <span data-ttu-id="e8500-145">拖动右窗格中的以下元素，并将它们放到左窗格中已命名节点上：</span><span class="sxs-lookup"><span data-stu-id="e8500-145">Drag the following elements from the right pane, and drop them onto the named nodes in the left pane:</span></span>  
  
    |<span data-ttu-id="e8500-146">From</span><span class="sxs-lookup"><span data-stu-id="e8500-146">From</span></span>|<span data-ttu-id="e8500-147">若要</span><span class="sxs-lookup"><span data-stu-id="e8500-147">To</span></span>|  
    |----------|--------|  
    |<span data-ttu-id="e8500-148">名称</span><span class="sxs-lookup"><span data-stu-id="e8500-148">Name</span></span>|<span data-ttu-id="e8500-149">From</span><span class="sxs-lookup"><span data-stu-id="e8500-149">From</span></span>|  
    |<span data-ttu-id="e8500-150">State</span><span class="sxs-lookup"><span data-stu-id="e8500-150">State</span></span>|<span data-ttu-id="e8500-151">State</span><span class="sxs-lookup"><span data-stu-id="e8500-151">State</span></span>|  
    |<span data-ttu-id="e8500-152">City</span><span class="sxs-lookup"><span data-stu-id="e8500-152">City</span></span>|<span data-ttu-id="e8500-153">City</span><span class="sxs-lookup"><span data-stu-id="e8500-153">City</span></span>|  
    |<span data-ttu-id="e8500-154">Phone</span><span class="sxs-lookup"><span data-stu-id="e8500-154">Phone</span></span>|<span data-ttu-id="e8500-155">Phone</span><span class="sxs-lookup"><span data-stu-id="e8500-155">Phone</span></span>|  
    |<span data-ttu-id="e8500-156">总计</span><span class="sxs-lookup"><span data-stu-id="e8500-156">Total</span></span>|<span data-ttu-id="e8500-157">PoTotal</span><span class="sxs-lookup"><span data-stu-id="e8500-157">PoTotal</span></span>|  
  
11. <span data-ttu-id="e8500-158">单击文件夹图标带有箭头 (![使用文件夹和向上按钮 & #45; 箭头](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 以显示业务流程。</span><span class="sxs-lookup"><span data-stu-id="e8500-158">Click the folder icon with the arrow (![button with folder and up&#45;arrow](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) to display the orchestration.</span></span>  
  
12. <span data-ttu-id="e8500-159">拖动 **Receive_1** 到右窗格中的形状 **Received** 的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="e8500-159">Drag the **Receive_1** shape in the right pane to **Received** in the left pane.</span></span>  
  
13. <span data-ttu-id="e8500-160">拖动 **Send_1** 到右窗格中的形状 **发送** 的左窗格中。</span><span class="sxs-lookup"><span data-stu-id="e8500-160">Drag the **Send_1** shape in the right pane to **Send** in the left pane.</span></span>  
  
14. <span data-ttu-id="e8500-161">保存跟踪配置文件到*\<示例路径\>* \BAM\BamFromExpression\ BamFromExpression.btt。</span><span class="sxs-lookup"><span data-stu-id="e8500-161">Save the tracking profile to *\<Samples Path\>* \BAM\BamFromExpression\ BamFromExpression.btt.</span></span>  
  
15. <span data-ttu-id="e8500-162">上 **工具** 菜单上，单击 **应用跟踪配置文件**。</span><span class="sxs-lookup"><span data-stu-id="e8500-162">On the **Tools** menu, click **Apply Tracking Profile**.</span></span>  
  
## <a name="build-and-initialize-this-sample"></a><span data-ttu-id="e8500-163">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="e8500-163">Build and initialize this sample</span></span>  
  
<span data-ttu-id="e8500-164">部署 BamFromExpression.btt 跟踪配置文件。</span><span class="sxs-lookup"><span data-stu-id="e8500-164">Deploy the BamFromExpression.btt tracking profile.</span></span> <span data-ttu-id="e8500-165">请参阅[如何部署跟踪配置文件使用跟踪配置文件管理实用工具](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)。</span><span class="sxs-lookup"><span data-stu-id="e8500-165">See [How to Deploy Tracking Profiles with the Tracking Profiles Management Utility](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md).</span></span>  
  
## <a name="run-this-sample"></a><span data-ttu-id="e8500-166">运行此示例</span><span class="sxs-lookup"><span data-stu-id="e8500-166">Run this sample</span></span>  
  
<span data-ttu-id="e8500-167">将文件复制*\<示例路径\>* 到 \BamFromExpression\InputMessage.xml *\<示例路径\>* \BamFromExpression\Input。</span><span class="sxs-lookup"><span data-stu-id="e8500-167">Copy the file *\<Samples Path\>* \BamFromExpression\InputMessage.xml to *\<Samples Path\>* \BamFromExpression\Input.</span></span>  
  
<span data-ttu-id="e8500-168">在大约 10 秒输出消息将出现在*\<示例路径\>* \BamFromExpression\Output。</span><span class="sxs-lookup"><span data-stu-id="e8500-168">In about 10 seconds the output message will appear in *\<Samples Path\>* \BamFromExpression\Output.</span></span>  
  
## <a name="view-the-bam-data"></a><span data-ttu-id="e8500-169">查看 BAM 数据</span><span class="sxs-lookup"><span data-stu-id="e8500-169">View the BAM data</span></span>  
  
1.  <span data-ttu-id="e8500-170">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="e8500-170">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="e8500-171">在 SQL Server Management Studio，展开服务器，展开 **数据库**, ，展开 **BAMPrimaryImport**, ，然后展开 **表**。</span><span class="sxs-lookup"><span data-stu-id="e8500-171">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="e8500-172">右键单击 **dbo.bam_FromExpressionPo_Completed**, ，然后单击 **打开表**。</span><span class="sxs-lookup"><span data-stu-id="e8500-172">Right-click **dbo.bam_FromExpressionPo_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="e8500-173">如果你使用的 SQL Server，请单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="e8500-173">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="e8500-174">将在右窗格中显示 bam_FromExpressionPo_Completed 表中的内容。</span><span class="sxs-lookup"><span data-stu-id="e8500-174">The contents of the bam_FromExpressionPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="e8500-175">具有活动 ID 123 的一行，表示包含在输入消息中 345 美元的采购订单。</span><span class="sxs-lookup"><span data-stu-id="e8500-175">The one row, which has an activity ID of 123, represents the purchase order for $345 that was contained in the input message.</span></span>  
  
4.  <span data-ttu-id="e8500-176">右键单击 **dbo.bam_FromExpressionPoItem_Completed**, ，然后单击 **打开表**。</span><span class="sxs-lookup"><span data-stu-id="e8500-176">Right-click **dbo.bam_FromExpressionPoItem_Completed**, and then click **Open Table**.</span></span> <span data-ttu-id="e8500-177">如果你使用的 SQL Server，请单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="e8500-177">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="e8500-178">将在右窗格中显示 bam_FromExpressionPoItem_Completed 表中的内容。</span><span class="sxs-lookup"><span data-stu-id="e8500-178">The contents of the bam_FromExpressionPoItem_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="e8500-179">两个行，它有活动 Id 123_0 和 123_1，表示该采购订单中的项︰ Flash MC 和红外的解码器。</span><span class="sxs-lookup"><span data-stu-id="e8500-179">The two rows, which have activity IDs 123_0 and 123_1, represent the items in the purchase order: Flash MC and Infrared Decoder.</span></span>  
  
5.  <span data-ttu-id="e8500-180">右键单击 **dbo.bam_FromExpressionPoItem_CompletedRelationships**, ，然后单击 **打开表**。</span><span class="sxs-lookup"><span data-stu-id="e8500-180">Right-click **dbo.bam_FromExpressionPoItem_CompletedRelationships**, and then click **Open Table**.</span></span> <span data-ttu-id="e8500-181">如果你使用的 SQL Server，请单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="e8500-181">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="e8500-182">将在右窗格中显示 bam_FromExpressionPoItem_CompletedRelationships 表中的内容。</span><span class="sxs-lookup"><span data-stu-id="e8500-182">The contents of the bam_FromExpressionPoItem_CompletedRelationships table are displayed in the right pane.</span></span> <span data-ttu-id="e8500-183">表中的每一行，都表示 FromExpressionPoItem 活动和 FromExpressionPo 活动之间的一种关系。</span><span class="sxs-lookup"><span data-stu-id="e8500-183">Each row in the table represents a relationship between a FromExpressionPoItem activity and a FromExpressionPo activity.</span></span> <span data-ttu-id="e8500-184">中的值 **ActivityID** 列是指 FromExpressionPoItem 活动的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="e8500-184">The value in the **ActivityID** column refers to the activity ID of the FromExpressionPoItem activity.</span></span> <span data-ttu-id="e8500-185">中的值 **ReferenceData** 列是指 FromExpressionPo 活动的活动 ID。</span><span class="sxs-lookup"><span data-stu-id="e8500-185">The value in the **ReferenceData** column refers to the activity ID of the FromExpressionPo activity.</span></span> <span data-ttu-id="e8500-186">在这种情况下，这两个记录表示 Flash MC 和红外解码器项与 345 美元的采购订单相关。</span><span class="sxs-lookup"><span data-stu-id="e8500-186">In this case, the two records indicate that the Flash MC and Infrared Decoder items are associated with the purchase order for $345.</span></span>  
  
## <a name="re-run-the-sample"></a><span data-ttu-id="e8500-187">重新运行此示例</span><span class="sxs-lookup"><span data-stu-id="e8500-187">Re-run the sample</span></span>  
  
1.  <span data-ttu-id="e8500-188">打开命令提示符以管理员身份，并运行*\<示例路径\>* \BAM\BamFromExpression\Cleanup.bat 若要删除的跟踪配置文件和其他 BAM 基础结构。</span><span class="sxs-lookup"><span data-stu-id="e8500-188">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\BamFromExpression\Cleanup.bat to remove the tracking profile and other BAM infrastructure.</span></span> 
  
2.  <span data-ttu-id="e8500-189">运行*\<示例路径\>* \BAM\BamFromExpression\Setup.bat 编译该示例并将其部署。</span><span class="sxs-lookup"><span data-stu-id="e8500-189">Run *\<Samples Path\>* \BAM\BamFromExpression\Setup.bat to compile the sample and deploy it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8500-190">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e8500-190">See Also</span></span>  
 <span data-ttu-id="e8500-191">[业务活动监视 （BizTalk Server 示例文件夹中）](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span><span class="sxs-lookup"><span data-stu-id="e8500-191">[Business Activity Monitoring (BizTalk Server Samples Folder)](../core/business-activity-monitoring-biztalk-server-samples-folder.md) </span></span>  
 [<span data-ttu-id="e8500-192">活动关系</span><span class="sxs-lookup"><span data-stu-id="e8500-192">Activity Relationships</span></span>](../core/activity-relationships.md)