---
title: BAM API 示例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 32a925f2-c7f4-4111-9c59-8865f15c6a89
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4dbc1adba5ef1b0c0a86c456a86ac3cce627d34f
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528533"
---
# <a name="bam-api-biztalk-server-sample"></a><span data-ttu-id="957bf-102">BAM API （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="957bf-102">BAM API (BizTalk Server Sample)</span></span>
<span data-ttu-id="957bf-103">BAM API 示例说明了如何将对 BAM API 的调用合并到应用程序以保存可以监视的关键信息。</span><span class="sxs-lookup"><span data-stu-id="957bf-103">The BAM API sample illustrates how to incorporate calls to the BAM API into an application to save key information that you can monitor.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="957bf-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="957bf-104">What This Sample Does</span></span>  
 <span data-ttu-id="957bf-105">此示例实现一个简单的购买方案。</span><span class="sxs-lookup"><span data-stu-id="957bf-105">This sample implements a simple purchasing scenario.</span></span> <span data-ttu-id="957bf-106">它生成采购订单、 处理每个采购订单、 创建装运并创建和处理发票。</span><span class="sxs-lookup"><span data-stu-id="957bf-106">It generates purchase orders, processes each purchase order, creates shipments, and creates and processes invoices.</span></span> <span data-ttu-id="957bf-107">在示例运行时，它将创建并更新 BAM 活动，以反映的详细信息和处置的采购订单和发票。</span><span class="sxs-lookup"><span data-stu-id="957bf-107">As the sample runs, it creates and updates BAM activities to reflect the details and disposition of the purchase orders and invoices.</span></span>  
  
## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="957bf-108">此示例设计的方式和原因</span><span class="sxs-lookup"><span data-stu-id="957bf-108">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="957bf-109">此示例旨在演示了如何使用 BAM 存储不是 BizTalk 业务流程的应用程序中的信息。</span><span class="sxs-lookup"><span data-stu-id="957bf-109">This sample was designed to illustrate how to use BAM to store information from an application that is not a BizTalk orchestration.</span></span> <span data-ttu-id="957bf-110">简单应用程序时，它说明了可能会在生产应用程序中使用的 BAM 的几个方面。</span><span class="sxs-lookup"><span data-stu-id="957bf-110">While the application is simple, it illustrates several aspects of BAM that you are likely to use in a production application.</span></span> <span data-ttu-id="957bf-111">其中包括：</span><span class="sxs-lookup"><span data-stu-id="957bf-111">These include the following:</span></span>  
  
- <span data-ttu-id="957bf-112">向单个活动分配多个线程</span><span class="sxs-lookup"><span data-stu-id="957bf-112">Multiple threads that contribute to a single activity</span></span>  
  
- <span data-ttu-id="957bf-113">创建两个活动之间的关系</span><span class="sxs-lookup"><span data-stu-id="957bf-113">Creating a relationship between two activities</span></span>  
  
- <span data-ttu-id="957bf-114">使用继续功能允许使用不同的 Id 访问同一活动</span><span class="sxs-lookup"><span data-stu-id="957bf-114">Using a continuation to allow the same activity to be accessed with different IDs</span></span>  
  
  <span data-ttu-id="957bf-115">BAM API 示例由三个主要类组成： 一个处理采购订单，一个处理发货和一个处理发票。</span><span class="sxs-lookup"><span data-stu-id="957bf-115">The BAM API sample consists of three main classes: one to process purchase orders, one to process shipments, and one to process invoices.</span></span> <span data-ttu-id="957bf-116">每个类具有**RunOnce**方法从队列检索消息，然后处理该消息。</span><span class="sxs-lookup"><span data-stu-id="957bf-116">Each class has a **RunOnce** method that retrieves a message from a queue, and then processes the message.</span></span> <span data-ttu-id="957bf-117">每个类还具有**运行**持续调用的方法**RunOnce**方法。</span><span class="sxs-lookup"><span data-stu-id="957bf-117">Each class also has a **Run** method that continually calls the **RunOnce** method.</span></span>  
  
  <span data-ttu-id="957bf-118">**RunOnce**方法**PoApplication**类执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="957bf-118">The **RunOnce** method of the **PoApplication** class does the following:</span></span>  
  
1. <span data-ttu-id="957bf-119">创建表示采购订单的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="957bf-119">Creates an XML message that represents a purchase order.</span></span>  
  
2. <span data-ttu-id="957bf-120">开始 BAMApiPo 活动，并添加有关采购订单和收到它时的信息。</span><span class="sxs-lookup"><span data-stu-id="957bf-120">Begins a BAMApiPo activity and adds to the activity information about the purchase order and when it was received.</span></span>  
  
3. <span data-ttu-id="957bf-121">任意批准或拒绝采购订单。</span><span class="sxs-lookup"><span data-stu-id="957bf-121">Arbitrarily approves or rejects the purchase order.</span></span>  
  
4. <span data-ttu-id="957bf-122">更新 BAMApiPo 活动以记录采购订单 （接受或拒绝） 的状态。</span><span class="sxs-lookup"><span data-stu-id="957bf-122">Updates the BAMApiPo activity to record the status of the purchase order (accepted or rejected).</span></span>  
  
5. <span data-ttu-id="957bf-123">如果已接受采购订单， **RunOnce**方法还执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="957bf-123">If the purchase order was accepted, the **RunOnce** method also does the following:</span></span>  
  
   1.  <span data-ttu-id="957bf-124">创建 XML 消息，以表示包要寄送，并将消息添加到发货队列。</span><span class="sxs-lookup"><span data-stu-id="957bf-124">Creates an XML message to represent a package to be shipped, and adds the message to the queue of shipments.</span></span>  
  
   2.  <span data-ttu-id="957bf-125">将添加到要包含在发票中的采购订单队列表示采购订单的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="957bf-125">Adds the XML message that represents the purchase order to the queue of purchase orders to be included in an invoice.</span></span>  
  
   3.  <span data-ttu-id="957bf-126">启用 BAMApiPo 活动的继续符。</span><span class="sxs-lookup"><span data-stu-id="957bf-126">Enables continuation for the BAMApiPo activity.</span></span>  
  
   4.  <span data-ttu-id="957bf-127">结束 BAMApiPo 活动。</span><span class="sxs-lookup"><span data-stu-id="957bf-127">Ends the BAMApiPo activity.</span></span>  
  
   <span data-ttu-id="957bf-128">**RunOnce**方法**ShipmentApplication**类执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="957bf-128">The **RunOnce** method of the **ShipmentApplication** class does the following:</span></span>  
  
6. <span data-ttu-id="957bf-129">从其队列中检索代表要发运的货包的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="957bf-129">Retrieves from its queue an XML message that represents a package to be shipped.</span></span>  
  
7. <span data-ttu-id="957bf-130">更新 BAMApiPo 活动以记录货包的时间。</span><span class="sxs-lookup"><span data-stu-id="957bf-130">Updates the BAMApiPo activity to record the time that the package was shipped.</span></span>  
  
8. <span data-ttu-id="957bf-131">结束 BAMApiPo 活动。</span><span class="sxs-lookup"><span data-stu-id="957bf-131">Ends the BAMApiPo activity.</span></span>  
  
   <span data-ttu-id="957bf-132">**RunOnce**方法**InvoiceApplication**类执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="957bf-132">The **RunOnce** method of the **InvoiceApplication** class does the following:</span></span>  
  
9. <span data-ttu-id="957bf-133">从其队列中检索代表开发票的采购订单的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="957bf-133">Retrieves from its queue an XML message that represents a purchase order to be invoiced.</span></span>  
  
10. <span data-ttu-id="957bf-134">开始 BAMApiInvoice 活动。</span><span class="sxs-lookup"><span data-stu-id="957bf-134">Begins a BAMApiInvoice activity.</span></span>  
  
11. <span data-ttu-id="957bf-135">创建 BAM 关系 BAMApiInvoice 活动和 BAMApiPo 活动将要开发票的采购订单之间。</span><span class="sxs-lookup"><span data-stu-id="957bf-135">Creates a BAM relationship between the BAMApiInvoice activity and the BAMApiPo activity for the purchase order that is being invoiced.</span></span>  
  
12. <span data-ttu-id="957bf-136">向 BAMApiPo 活动有关的信息和发票时创建它。</span><span class="sxs-lookup"><span data-stu-id="957bf-136">Adds to the BAMApiPo activity information about the invoice and the time it was created.</span></span>  
  
13. <span data-ttu-id="957bf-137">在任意延迟模拟等待要付款的发票后, 向 BAMApiInvoice 活动发票支付的时间。</span><span class="sxs-lookup"><span data-stu-id="957bf-137">After an arbitrary delay to simulate waiting for the invoice to be paid, adds to the BAMApiInvoice activity the time the invoice was paid.</span></span>  
  
14. <span data-ttu-id="957bf-138">结束 BAMApiInvoice 活动。</span><span class="sxs-lookup"><span data-stu-id="957bf-138">Ends the BAMApiInvoice activity.</span></span>  
  
    <span data-ttu-id="957bf-139">**Main**方法**MainApp**类初始化应用程序。</span><span class="sxs-lookup"><span data-stu-id="957bf-139">The **Main** method of the **MainApp** class initializes the application.</span></span> <span data-ttu-id="957bf-140">它执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="957bf-140">It does the following:</span></span>  
  
15. <span data-ttu-id="957bf-141">创建**DirectEventStream**对象。</span><span class="sxs-lookup"><span data-stu-id="957bf-141">Creates a **DirectEventStream** object.</span></span>  
  
16. <span data-ttu-id="957bf-142">启动多个线程，并调用**运行**方法**POApplication**中每个线程对象。</span><span class="sxs-lookup"><span data-stu-id="957bf-142">Starts several threads, and calls the **Run** method of the **POApplication** object in each thread.</span></span>  
  
17. <span data-ttu-id="957bf-143">启动多个线程，并调用**运行**方法**ShipmentApplication**中每个线程对象。</span><span class="sxs-lookup"><span data-stu-id="957bf-143">Starts several threads, and calls the **Run** method of the **ShipmentApplication** object in each thread.</span></span>  
  
18. <span data-ttu-id="957bf-144">启动多个线程，并调用**运行**方法**InvoiceApplication**中每个线程对象。</span><span class="sxs-lookup"><span data-stu-id="957bf-144">Starts several threads, and calls the **Run** method of the **InvoiceApplication** object in each thread.</span></span>  
  
    <span data-ttu-id="957bf-145">**Global**类定义一些常量，由示例应用程序，如要创建的线程数和拒绝采购订单的百分比。</span><span class="sxs-lookup"><span data-stu-id="957bf-145">The **Global** class defines constants that are used by the sample application, such as the number of threads to create and the percentage of purchase orders to reject.</span></span>  
  
    <span data-ttu-id="957bf-146">除了 Visual Studio 解决方案中，该示例还包含用于定义活动的 Microsoft Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="957bf-146">In addition to the Visual Studio solution, the sample also contains a Microsoft Excel file that defines the activities.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="957bf-147">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="957bf-147">Where to Find This Sample</span></span>  
 <span data-ttu-id="957bf-148">您可以找到在此示例*\<示例路径\>* \BAM\BamApiSample。</span><span class="sxs-lookup"><span data-stu-id="957bf-148">You can find this sample at *\<Samples Path\>* \BAM\BamApiSample.</span></span>  
  
 <span data-ttu-id="957bf-149">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="957bf-149">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="957bf-150">文件</span><span class="sxs-lookup"><span data-stu-id="957bf-150">File</span></span>|<span data-ttu-id="957bf-151">Description</span><span class="sxs-lookup"><span data-stu-id="957bf-151">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="957bf-152">BamApiSample.cs</span><span class="sxs-lookup"><span data-stu-id="957bf-152">BamApiSample.cs</span></span>|<span data-ttu-id="957bf-153">已检测应用程序。</span><span class="sxs-lookup"><span data-stu-id="957bf-153">Instrumented application.</span></span>|  
|<span data-ttu-id="957bf-154">BamApiSample.csproj</span><span class="sxs-lookup"><span data-stu-id="957bf-154">BamApiSample.csproj</span></span>|<span data-ttu-id="957bf-155">已检测应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="957bf-155">Instrumented application project.</span></span>|  
|<span data-ttu-id="957bf-156">BamApiSample.sln</span><span class="sxs-lookup"><span data-stu-id="957bf-156">BamApiSample.sln</span></span>|<span data-ttu-id="957bf-157">检测应用程序解决方案。</span><span class="sxs-lookup"><span data-stu-id="957bf-157">Instrumented application solution.</span></span>|  
|<span data-ttu-id="957bf-158">BamApiSample.xls</span><span class="sxs-lookup"><span data-stu-id="957bf-158">BamApiSample.xls</span></span>|<span data-ttu-id="957bf-159">BAM 定义样式表。</span><span class="sxs-lookup"><span data-stu-id="957bf-159">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="957bf-160">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="957bf-160">Cleanup.bat</span></span>|<span data-ttu-id="957bf-161">若要删除已部署的示例文件的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="957bf-161">Batch file to remove deployed sample files.</span></span>|  
|<span data-ttu-id="957bf-162">Input.txt</span><span class="sxs-lookup"><span data-stu-id="957bf-162">Input.txt</span></span>|<span data-ttu-id="957bf-163">输入示例侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="957bf-163">Sample interceptor configuration input.</span></span>|  
|<span data-ttu-id="957bf-164">InterceptorConfig.cs</span><span class="sxs-lookup"><span data-stu-id="957bf-164">InterceptorConfig.cs</span></span>|<span data-ttu-id="957bf-165">API 示例的侦听器配置代码。</span><span class="sxs-lookup"><span data-stu-id="957bf-165">Interceptor configuration code for API sample.</span></span>|  
|<span data-ttu-id="957bf-166">InterceptorConfig.csproj</span><span class="sxs-lookup"><span data-stu-id="957bf-166">InterceptorConfig.csproj</span></span>|<span data-ttu-id="957bf-167">侦听器配置项目。</span><span class="sxs-lookup"><span data-stu-id="957bf-167">Interceptor configuration project.</span></span>|  
|<span data-ttu-id="957bf-168">Invoice_config.xml</span><span class="sxs-lookup"><span data-stu-id="957bf-168">Invoice_config.xml</span></span>|<span data-ttu-id="957bf-169">Invoice 侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="957bf-169">Invoice interceptor configuration.</span></span>|  
|<span data-ttu-id="957bf-170">Invoice_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="957bf-170">Invoice_interceptor.bin</span></span>|<span data-ttu-id="957bf-171">序列化的 invoice 侦听器。</span><span class="sxs-lookup"><span data-stu-id="957bf-171">Serialized invoice interceptor.</span></span>|  
|<span data-ttu-id="957bf-172">PurchaseOrder_config.xml</span><span class="sxs-lookup"><span data-stu-id="957bf-172">PurchaseOrder_config.xml</span></span>|<span data-ttu-id="957bf-173">PurchaseOrder 侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="957bf-173">PurchaseOrder interceptor configuration.</span></span>|  
|<span data-ttu-id="957bf-174">PurchaseOrder_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="957bf-174">PurchaseOrder_interceptor.bin</span></span>|<span data-ttu-id="957bf-175">序列化的 PurchaseOrder 侦听器。</span><span class="sxs-lookup"><span data-stu-id="957bf-175">Serialized PurchaseOrder interceptor.</span></span>|  
|<span data-ttu-id="957bf-176">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="957bf-176">Setup.bat</span></span>|<span data-ttu-id="957bf-177">若要部署和登记示例文件的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="957bf-177">Batch file to deploy and enlist sample files.</span></span>|  
|<span data-ttu-id="957bf-178">Shipment_config.xml</span><span class="sxs-lookup"><span data-stu-id="957bf-178">Shipment_config.xml</span></span>|<span data-ttu-id="957bf-179">Shipment 侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="957bf-179">Shipment interceptor configuration.</span></span>|  
|<span data-ttu-id="957bf-180">Shipment_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="957bf-180">Shipment_interceptor.bin</span></span>|<span data-ttu-id="957bf-181">序列化的 shipment 侦听器。</span><span class="sxs-lookup"><span data-stu-id="957bf-181">Serialized shipment interceptor.</span></span>|  
  
## <a name="run-the-bam-api-sample"></a><span data-ttu-id="957bf-182">运行 BAM API 示例</span><span class="sxs-lookup"><span data-stu-id="957bf-182">Run the BAM API sample</span></span>  
  
1.  <span data-ttu-id="957bf-183">打开命令提示符下以管理员身份，并运行*\<示例路径\>* \BAM\ BamApiSample\setup.bat。</span><span class="sxs-lookup"><span data-stu-id="957bf-183">Open a command prompt as Administrator, and run *\<Samples Path\>* \BAM\ BamApiSample\setup.bat.</span></span>  
  
2.  <span data-ttu-id="957bf-184">以管理员身份启动 Visual Studio 并打开*\<示例路径\>* BAMAPISAMPLE\BAMAPISAMPLE.SLN 解决方案。</span><span class="sxs-lookup"><span data-stu-id="957bf-184">Start Visual Studio as Administrator, and open the *\<Samples Path\>* \BAM\ BamApiSample\BamApiSample.sln solution.</span></span> 
  
    > [!IMPORTANT]
    >  <span data-ttu-id="957bf-185">在行`//#define Interceptor`中 BamApiSample.cs 文件必须注释掉。不要删除"/ /"从该行。</span><span class="sxs-lookup"><span data-stu-id="957bf-185">The line `//#define Interceptor` in the BamApiSample.cs file must be commented out. Do not remove the “//” from this line.</span></span> <span data-ttu-id="957bf-186">BAM API 示例使用的不是深入了解代码`#if Interceptor`预处理器指令。</span><span class="sxs-lookup"><span data-stu-id="957bf-186">The BAM API sample uses only the code that is not inside an `#if Interceptor` preprocessor directive.</span></span>  
  
3.  <span data-ttu-id="957bf-187">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="957bf-187">Build the solution.</span></span>  
  
4.  <span data-ttu-id="957bf-188">运行*\<示例路径\>* \BAM\BamApiSample\bin\debug\BamApiSample.exe。</span><span class="sxs-lookup"><span data-stu-id="957bf-188">Run *\<Samples Path\>* \BAM\BamApiSample\bin\debug\BamApiSample.exe.</span></span>  
  
     <span data-ttu-id="957bf-189">输出将如下所示：</span><span class="sxs-lookup"><span data-stu-id="957bf-189">The output will resemble the following:</span></span>  
  
    ```  
    ...  
    New Purchase Order #17 Received  
    8 was shipped as pkg#87  
    New Purchase Order #18 Received.  
    Shipping package pkg#87 via DHL  
    13 was Approved.  
    18 was Rejected.  
    17 was Rejected.  
    11 was shipped as pkg#114  
    16 wsas Rejected.  
    Shipping package pkg#114 via DHL  
    Invoice #5 send for {2 5 1 9 4 8 11 }  
    Package pkg#49 was delivered  
    New Purchase Order #19 Received.  
    ...  
    ```  
  
5.  <span data-ttu-id="957bf-190">后一分钟左右，按 CTRL + C 或关闭命令提示符窗口以停止 BamApiSample 程序。</span><span class="sxs-lookup"><span data-stu-id="957bf-190">After a minute or so, press CTRL+C or close the Command Prompt window to stop the BamApiSample program.</span></span>  
  
## <a name="view-the-results"></a><span data-ttu-id="957bf-191">查看结果</span><span class="sxs-lookup"><span data-stu-id="957bf-191">View the results</span></span>
  
1.  <span data-ttu-id="957bf-192">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="957bf-192">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="957bf-193">在 SQL Server Management Studio 中，展开服务器，展开**数据库**，展开**BAMPrimaryImport**，然后展开**表**。</span><span class="sxs-lookup"><span data-stu-id="957bf-193">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="957bf-194">右键单击**dbo.bam_BAMApiInvoice_Active** ，然后单击**打开表**。</span><span class="sxs-lookup"><span data-stu-id="957bf-194">Right-click **dbo.bam_BAMApiInvoice_Active** and then click **Open Table**.</span></span> <span data-ttu-id="957bf-195">如果使用 SQL Server，请单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="957bf-195">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="957bf-196">Bam_BAMApiInvoice_Active 表的内容显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="957bf-196">The contents of the bam_BAMApiInvoice_Active table are displayed in the right pane.</span></span> <span data-ttu-id="957bf-197">在表中的每一行表示已经启动但尚未完成的 BAMApiInvoice 活动。</span><span class="sxs-lookup"><span data-stu-id="957bf-197">Each row in the table represents a BAMApiInvoice activity that has been started, but  has not been completed.</span></span>  
  
4.  <span data-ttu-id="957bf-198">右键单击**dbo.bam_BAMApiPo_Completed** ，然后单击**打开表**。</span><span class="sxs-lookup"><span data-stu-id="957bf-198">Right-click **dbo.bam_BAMApiPo_Completed** and then click **Open Table**.</span></span> <span data-ttu-id="957bf-199">如果使用 SQL Server，请单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="957bf-199">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="957bf-200">Bam_BAMApiPo_Completed 表的内容显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="957bf-200">The contents of the bam_BAMApiPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="957bf-201">表中的每一行表示已完成的 BAMApiPo 活动。</span><span class="sxs-lookup"><span data-stu-id="957bf-201">Each row in the table represents a BAMApiPo activity that has been completed.</span></span>