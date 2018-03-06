---
title: "BAM API 示例 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 32a925f2-c7f4-4111-9c59-8865f15c6a89
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e181af5766231ed9a7d828b49e2d840a47f216c
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="bam-api-biztalk-server-sample"></a><span data-ttu-id="5998e-102">BAM API（BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="5998e-102">BAM API (BizTalk Server Sample)</span></span>
<span data-ttu-id="5998e-103">BAM API 示例显示如何将对 BAM API 的调用合并到应用程序中，以保存可以监视的关键信息。</span><span class="sxs-lookup"><span data-stu-id="5998e-103">The BAM API sample illustrates how to incorporate calls to the BAM API into an application to save key information that you can monitor.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="5998e-104">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="5998e-104">What This Sample Does</span></span>  
 <span data-ttu-id="5998e-105">本示例用于实现简单的购买方案。</span><span class="sxs-lookup"><span data-stu-id="5998e-105">This sample implements a simple purchasing scenario.</span></span> <span data-ttu-id="5998e-106">它将生成采购订单、处理每个采购订单、创建装运并创建和处理发票。</span><span class="sxs-lookup"><span data-stu-id="5998e-106">It generates purchase orders, processes each purchase order, creates shipments, and creates and processes invoices.</span></span> <span data-ttu-id="5998e-107">在本示例运行时，将创建和更新 BAM 活动，以反映采购订单和发票的详细信息和对它们的处置。</span><span class="sxs-lookup"><span data-stu-id="5998e-107">As the sample runs, it creates and updates BAM activities to reflect the details and disposition of the purchase orders and invoices.</span></span>  
  
## <a name="how-this-sample-was-designed-and-why"></a><span data-ttu-id="5998e-108">本示例的设计方式和原因</span><span class="sxs-lookup"><span data-stu-id="5998e-108">How This Sample Was Designed and Why</span></span>  
 <span data-ttu-id="5998e-109">本示例旨在说明如何使用 BAM 存储不是来自 BizTalk 业务流程的应用程序提供的信息。</span><span class="sxs-lookup"><span data-stu-id="5998e-109">This sample was designed to illustrate how to use BAM to store information from an application that is not a BizTalk orchestration.</span></span> <span data-ttu-id="5998e-110">当应用程序比较简单时，将介绍很可能需要在生产应用程序中使用的多个方面的 BAM。</span><span class="sxs-lookup"><span data-stu-id="5998e-110">While the application is simple, it illustrates several aspects of BAM that you are likely to use in a production application.</span></span> <span data-ttu-id="5998e-111">其中包括：</span><span class="sxs-lookup"><span data-stu-id="5998e-111">These include the following:</span></span>  
  
-   <span data-ttu-id="5998e-112">向单个活动分配多个线程</span><span class="sxs-lookup"><span data-stu-id="5998e-112">Multiple threads that contribute to a single activity</span></span>  
  
-   <span data-ttu-id="5998e-113">创建两个活动之间的关系</span><span class="sxs-lookup"><span data-stu-id="5998e-113">Creating a relationship between two activities</span></span>  
  
-   <span data-ttu-id="5998e-114">使用继续功能允许通过不同的 ID 访问同一活动</span><span class="sxs-lookup"><span data-stu-id="5998e-114">Using a continuation to allow the same activity to be accessed with different IDs</span></span>  
  
 <span data-ttu-id="5998e-115">BAM API 示例由三个主要类组成︰ 一个用于处理采购订单、 处理装运到一个，另一个以处理发票。</span><span class="sxs-lookup"><span data-stu-id="5998e-115">The BAM API sample consists of three main classes: one to process purchase orders, one to process shipments, and one to process invoices.</span></span> <span data-ttu-id="5998e-116">每个类具有 **RunOnce** 从队列检索消息，然后处理该消息的方法。</span><span class="sxs-lookup"><span data-stu-id="5998e-116">Each class has a **RunOnce** method that retrieves a message from a queue, and then processes the message.</span></span> <span data-ttu-id="5998e-117">每个类还具有 **运行** 不断地调用的方法 **RunOnce** 方法。</span><span class="sxs-lookup"><span data-stu-id="5998e-117">Each class also has a **Run** method that continually calls the **RunOnce** method.</span></span>  
  
 <span data-ttu-id="5998e-118">**RunOnce** 方法 **PoApplication** 类执行下列任务︰</span><span class="sxs-lookup"><span data-stu-id="5998e-118">The **RunOnce** method of the **PoApplication** class does the following:</span></span>  
  
1.  <span data-ttu-id="5998e-119">创建表示采购订单的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="5998e-119">Creates an XML message that represents a purchase order.</span></span>  
  
2.  <span data-ttu-id="5998e-120">开始 BAMApiPo 活动，向获得添加有关采购订单及接收时间的信息。</span><span class="sxs-lookup"><span data-stu-id="5998e-120">Begins a BAMApiPo activity and adds to the activity information about the purchase order and when it was received.</span></span>  
  
3.  <span data-ttu-id="5998e-121">任意批准或拒绝采购订单。</span><span class="sxs-lookup"><span data-stu-id="5998e-121">Arbitrarily approves or rejects the purchase order.</span></span>  
  
4.  <span data-ttu-id="5998e-122">更新 BAMApiPo 活动以记录采购订单的状态（接受或拒绝）。</span><span class="sxs-lookup"><span data-stu-id="5998e-122">Updates the BAMApiPo activity to record the status of the purchase order (accepted or rejected).</span></span>  
  
5.  <span data-ttu-id="5998e-123">如果已接受的采购订单， **RunOnce** 方法还执行以下︰</span><span class="sxs-lookup"><span data-stu-id="5998e-123">If the purchase order was accepted, the **RunOnce** method also does the following:</span></span>  
  
    1.  <span data-ttu-id="5998e-124">创建 XML 消息以代表要发运的货包，并将该消息添加到发货队列。</span><span class="sxs-lookup"><span data-stu-id="5998e-124">Creates an XML message to represent a package to be shipped, and adds the message to the queue of shipments.</span></span>  
  
    2.  <span data-ttu-id="5998e-125">将表示采购订单的 XML 消息添加到要包含在发票中的采购订单队列中。</span><span class="sxs-lookup"><span data-stu-id="5998e-125">Adds the XML message that represents the purchase order to the queue of purchase orders to be included in an invoice.</span></span>  
  
    3.  <span data-ttu-id="5998e-126">启用 BAMApiPo 活动的继续。</span><span class="sxs-lookup"><span data-stu-id="5998e-126">Enables continuation for the BAMApiPo activity.</span></span>  
  
    4.  <span data-ttu-id="5998e-127">结束 BAMApiPo 活动。</span><span class="sxs-lookup"><span data-stu-id="5998e-127">Ends the BAMApiPo activity.</span></span>  
  
 <span data-ttu-id="5998e-128">**RunOnce** 方法 **ShipmentApplication** 类执行下列任务︰</span><span class="sxs-lookup"><span data-stu-id="5998e-128">The **RunOnce** method of the **ShipmentApplication** class does the following:</span></span>  
  
1.  <span data-ttu-id="5998e-129">从其队列中检索代表要发运的货包的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="5998e-129">Retrieves from its queue an XML message that represents a package to be shipped.</span></span>  
  
2.  <span data-ttu-id="5998e-130">更新 BAMApiPo 活动以记录发运货包的时间。</span><span class="sxs-lookup"><span data-stu-id="5998e-130">Updates the BAMApiPo activity to record the time that the package was shipped.</span></span>  
  
3.  <span data-ttu-id="5998e-131">结束 BAMApiPo 活动。</span><span class="sxs-lookup"><span data-stu-id="5998e-131">Ends the BAMApiPo activity.</span></span>  
  
 <span data-ttu-id="5998e-132">**RunOnce** 方法 **InvoiceApplication** 类执行下列任务︰</span><span class="sxs-lookup"><span data-stu-id="5998e-132">The **RunOnce** method of the **InvoiceApplication** class does the following:</span></span>  
  
1.  <span data-ttu-id="5998e-133">从其队列中检索代表要开发票的采购订单的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="5998e-133">Retrieves from its queue an XML message that represents a purchase order to be invoiced.</span></span>  
  
2.  <span data-ttu-id="5998e-134">开始 BAMApiInvoice 活动。</span><span class="sxs-lookup"><span data-stu-id="5998e-134">Begins a BAMApiInvoice activity.</span></span>  
  
3.  <span data-ttu-id="5998e-135">为将要开发票的采购订单在 BAMApiInvoice 活动和 BAMApiPo 活动之间创建 BAM 关系。</span><span class="sxs-lookup"><span data-stu-id="5998e-135">Creates a BAM relationship between the BAMApiInvoice activity and the BAMApiPo activity for the purchase order that is being invoiced.</span></span>  
  
4.  <span data-ttu-id="5998e-136">向 BAMApiPo 活动中添加有关发票和创建时间的信息。</span><span class="sxs-lookup"><span data-stu-id="5998e-136">Adds to the BAMApiPo activity information about the invoice and the time it was created.</span></span>  
  
5.  <span data-ttu-id="5998e-137">在任意延迟模拟等待要付款的发票之后，向 BAMApiInvoice 活动中添加发票的付款时间。</span><span class="sxs-lookup"><span data-stu-id="5998e-137">After an arbitrary delay to simulate waiting for the invoice to be paid, adds to the BAMApiInvoice activity the time the invoice was paid.</span></span>  
  
6.  <span data-ttu-id="5998e-138">结束 BAMApiInvoice 活动。</span><span class="sxs-lookup"><span data-stu-id="5998e-138">Ends the BAMApiInvoice activity.</span></span>  
  
 <span data-ttu-id="5998e-139">**Main** 方法 **MainApp** 类初始化应用程序。</span><span class="sxs-lookup"><span data-stu-id="5998e-139">The **Main** method of the **MainApp** class initializes the application.</span></span> <span data-ttu-id="5998e-140">它执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5998e-140">It does the following:</span></span>  
  
1.  <span data-ttu-id="5998e-141">创建 **DirectEventStream** 对象。</span><span class="sxs-lookup"><span data-stu-id="5998e-141">Creates a **DirectEventStream** object.</span></span>  
  
2.  <span data-ttu-id="5998e-142">启动多个线程和调用 **运行** 方法 **POApplication** 中每个线程对象。</span><span class="sxs-lookup"><span data-stu-id="5998e-142">Starts several threads, and calls the **Run** method of the **POApplication** object in each thread.</span></span>  
  
3.  <span data-ttu-id="5998e-143">启动多个线程和调用 **运行** 方法 **ShipmentApplication** 中每个线程对象。</span><span class="sxs-lookup"><span data-stu-id="5998e-143">Starts several threads, and calls the **Run** method of the **ShipmentApplication** object in each thread.</span></span>  
  
4.  <span data-ttu-id="5998e-144">启动多个线程和调用 **运行** 方法 **InvoiceApplication** 中每个线程对象。</span><span class="sxs-lookup"><span data-stu-id="5998e-144">Starts several threads, and calls the **Run** method of the **InvoiceApplication** object in each thread.</span></span>  
  
 <span data-ttu-id="5998e-145">**全局** 类定义使用的示例应用程序，例如要创建的线程数和要拒绝的采购订单的百分比的常量。</span><span class="sxs-lookup"><span data-stu-id="5998e-145">The **Global** class defines constants that are used by the sample application, such as the number of threads to create and the percentage of purchase orders to reject.</span></span>  
  
 <span data-ttu-id="5998e-146">除了 Visual Studio 解决方案中，该示例还包含定义的活动的 Microsoft Excel 文件。</span><span class="sxs-lookup"><span data-stu-id="5998e-146">In addition to the Visual Studio solution, the sample also contains a Microsoft Excel file that defines the activities.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="5998e-147">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="5998e-147">Where to Find This Sample</span></span>  
 <span data-ttu-id="5998e-148">你可以找到在此示例*\<示例路径\>*\BAM\BamApiSample。</span><span class="sxs-lookup"><span data-stu-id="5998e-148">You can find this sample at *\<Samples Path\>*\BAM\BamApiSample.</span></span>  
  
 <span data-ttu-id="5998e-149">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="5998e-149">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="5998e-150">文件</span><span class="sxs-lookup"><span data-stu-id="5998e-150">File</span></span>|<span data-ttu-id="5998e-151">Description</span><span class="sxs-lookup"><span data-stu-id="5998e-151">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="5998e-152">BamApiSample.cs</span><span class="sxs-lookup"><span data-stu-id="5998e-152">BamApiSample.cs</span></span>|<span data-ttu-id="5998e-153">开发的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5998e-153">Instrumented application.</span></span>|  
|<span data-ttu-id="5998e-154">BamApiSample.csproj</span><span class="sxs-lookup"><span data-stu-id="5998e-154">BamApiSample.csproj</span></span>|<span data-ttu-id="5998e-155">开发的应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="5998e-155">Instrumented application project.</span></span>|  
|<span data-ttu-id="5998e-156">BamApiSample.sln</span><span class="sxs-lookup"><span data-stu-id="5998e-156">BamApiSample.sln</span></span>|<span data-ttu-id="5998e-157">开发的应用程序解决方案。</span><span class="sxs-lookup"><span data-stu-id="5998e-157">Instrumented application solution.</span></span>|  
|<span data-ttu-id="5998e-158">BamApiSample.xls</span><span class="sxs-lookup"><span data-stu-id="5998e-158">BamApiSample.xls</span></span>|<span data-ttu-id="5998e-159">BAM 定义样式表。</span><span class="sxs-lookup"><span data-stu-id="5998e-159">BAM definition style sheet.</span></span>|  
|<span data-ttu-id="5998e-160">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="5998e-160">Cleanup.bat</span></span>|<span data-ttu-id="5998e-161">用于删除已部署示例文件的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="5998e-161">Batch file to remove deployed sample files.</span></span>|  
|<span data-ttu-id="5998e-162">Input.txt</span><span class="sxs-lookup"><span data-stu-id="5998e-162">Input.txt</span></span>|<span data-ttu-id="5998e-163">用于输入示例侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="5998e-163">Sample interceptor configuration input.</span></span>|  
|<span data-ttu-id="5998e-164">InterceptorConfig.cs</span><span class="sxs-lookup"><span data-stu-id="5998e-164">InterceptorConfig.cs</span></span>|<span data-ttu-id="5998e-165">API 示例的侦听器配置代码。</span><span class="sxs-lookup"><span data-stu-id="5998e-165">Interceptor configuration code for API sample.</span></span>|  
|<span data-ttu-id="5998e-166">InterceptorConfig.csproj</span><span class="sxs-lookup"><span data-stu-id="5998e-166">InterceptorConfig.csproj</span></span>|<span data-ttu-id="5998e-167">侦听器配置项目。</span><span class="sxs-lookup"><span data-stu-id="5998e-167">Interceptor configuration project.</span></span>|  
|<span data-ttu-id="5998e-168">Invoice_config.xml</span><span class="sxs-lookup"><span data-stu-id="5998e-168">Invoice_config.xml</span></span>|<span data-ttu-id="5998e-169">Invoice 侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="5998e-169">Invoice interceptor configuration.</span></span>|  
|<span data-ttu-id="5998e-170">Invoice_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="5998e-170">Invoice_interceptor.bin</span></span>|<span data-ttu-id="5998e-171">序列化的 Invoice 侦听器。</span><span class="sxs-lookup"><span data-stu-id="5998e-171">Serialized invoice interceptor.</span></span>|  
|<span data-ttu-id="5998e-172">PurchaseOrder_config.xml</span><span class="sxs-lookup"><span data-stu-id="5998e-172">PurchaseOrder_config.xml</span></span>|<span data-ttu-id="5998e-173">PurchaseOrder 侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="5998e-173">PurchaseOrder interceptor configuration.</span></span>|  
|<span data-ttu-id="5998e-174">PurchaseOrder_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="5998e-174">PurchaseOrder_interceptor.bin</span></span>|<span data-ttu-id="5998e-175">序列化的 PurchaseOrder 侦听器。</span><span class="sxs-lookup"><span data-stu-id="5998e-175">Serialized PurchaseOrder interceptor.</span></span>|  
|<span data-ttu-id="5998e-176">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="5998e-176">Setup.bat</span></span>|<span data-ttu-id="5998e-177">用于部署和登记示例文件的批处理文件。</span><span class="sxs-lookup"><span data-stu-id="5998e-177">Batch file to deploy and enlist sample files.</span></span>|  
|<span data-ttu-id="5998e-178">Shipment_config.xml</span><span class="sxs-lookup"><span data-stu-id="5998e-178">Shipment_config.xml</span></span>|<span data-ttu-id="5998e-179">Shipment 侦听器配置。</span><span class="sxs-lookup"><span data-stu-id="5998e-179">Shipment interceptor configuration.</span></span>|  
|<span data-ttu-id="5998e-180">Shipment_interceptor.bin</span><span class="sxs-lookup"><span data-stu-id="5998e-180">Shipment_interceptor.bin</span></span>|<span data-ttu-id="5998e-181">序列化的 Shipment 侦听器。</span><span class="sxs-lookup"><span data-stu-id="5998e-181">Serialized shipment interceptor.</span></span>|  
  
## <a name="run-the-bam-api-sample"></a><span data-ttu-id="5998e-182">运行 BAM API 示例</span><span class="sxs-lookup"><span data-stu-id="5998e-182">Run the BAM API sample</span></span>  
  
1.  <span data-ttu-id="5998e-183">打开命令提示符以管理员身份，并运行*\<示例路径\>*\BAM\ BamApiSample\setup.bat。</span><span class="sxs-lookup"><span data-stu-id="5998e-183">Open a command prompt as Administrator, and run *\<Samples Path\>*\BAM\ BamApiSample\setup.bat.</span></span>  
  
2.  <span data-ttu-id="5998e-184">作为管理员，启动 Visual Studio 并打开*\<示例路径\>*\BAM\ BamApiSample\BamApiSample.sln 解决方案。</span><span class="sxs-lookup"><span data-stu-id="5998e-184">Start Visual Studio as Administrator, and open the *\<Samples Path\>*\BAM\ BamApiSample\BamApiSample.sln solution.</span></span> 
  
    > [!IMPORTANT]
    >  <span data-ttu-id="5998e-185">必须注释掉 BamApiSample.cs 文件中的行 `//#define Interceptor`。请勿从该行中删除 “//”。</span><span class="sxs-lookup"><span data-stu-id="5998e-185">The line `//#define Interceptor` in the BamApiSample.cs file must be commented out. Do not remove the “//” from this line.</span></span> <span data-ttu-id="5998e-186">BAM API 示例只使用不在 `#if Interceptor` 的预处理器指令内的代码。</span><span class="sxs-lookup"><span data-stu-id="5998e-186">The BAM API sample uses only the code that is not inside an `#if Interceptor` preprocessor directive.</span></span>  
  
3.  <span data-ttu-id="5998e-187">生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="5998e-187">Build the solution.</span></span>  
  
4.  <span data-ttu-id="5998e-188">运行*\<示例路径\>*\BAM\BamApiSample\bin\debug\BamApiSample.exe。</span><span class="sxs-lookup"><span data-stu-id="5998e-188">Run *\<Samples Path\>*\BAM\BamApiSample\bin\debug\BamApiSample.exe.</span></span>  
  
     <span data-ttu-id="5998e-189">输出将如下所示︰</span><span class="sxs-lookup"><span data-stu-id="5998e-189">The output will resemble the following:</span></span>  
  
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
  
5.  <span data-ttu-id="5998e-190">在大约一分钟后，按 Ctrl+C 或关闭命令提示符窗口，以停止 BamApiSample 程序。</span><span class="sxs-lookup"><span data-stu-id="5998e-190">After a minute or so, press CTRL+C or close the Command Prompt window to stop the BamApiSample program.</span></span>  
  
## <a name="view-the-results"></a><span data-ttu-id="5998e-191">查看结果</span><span class="sxs-lookup"><span data-stu-id="5998e-191">View the results</span></span>
  
1.  <span data-ttu-id="5998e-192">打开 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="5998e-192">Open SQL Server Management Studio.</span></span>  
  
2.  <span data-ttu-id="5998e-193">在 SQL Server Management Studio，展开服务器，展开 **数据库**, ，展开 **BAMPrimaryImport**, ，然后展开 **表**。</span><span class="sxs-lookup"><span data-stu-id="5998e-193">In SQL Server Management Studio, expand the server, expand **Databases**, expand **BAMPrimaryImport**, and then expand **Tables**.</span></span>  
  
3.  <span data-ttu-id="5998e-194">右键单击 **dbo.bam_BAMApiInvoice_Active** ，然后单击 **打开表**。</span><span class="sxs-lookup"><span data-stu-id="5998e-194">Right-click **dbo.bam_BAMApiInvoice_Active** and then click **Open Table**.</span></span> <span data-ttu-id="5998e-195">如果你使用的 SQL Server，请单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="5998e-195">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="5998e-196">bam_BAMApiInvoice_Active 表的内容将显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="5998e-196">The contents of the bam_BAMApiInvoice_Active table are displayed in the right pane.</span></span> <span data-ttu-id="5998e-197">表中的每行均表示已经启动但尚未完成的 BAMApiInvoice 活动。</span><span class="sxs-lookup"><span data-stu-id="5998e-197">Each row in the table represents a BAMApiInvoice activity that has been started, but  has not been completed.</span></span>  
  
4.  <span data-ttu-id="5998e-198">右键单击 **dbo.bam_BAMApiPo_Completed** ，然后单击 **打开表**。</span><span class="sxs-lookup"><span data-stu-id="5998e-198">Right-click **dbo.bam_BAMApiPo_Completed** and then click **Open Table**.</span></span> <span data-ttu-id="5998e-199">如果你使用的 SQL Server，请单击**选择前 1000年行**。</span><span class="sxs-lookup"><span data-stu-id="5998e-199">If you are using SQL Server, click **Select top 1000 rows**.</span></span>  
  
     <span data-ttu-id="5998e-200">bam_BAMApiPo_Completed 表的内容将显示在右窗格中。</span><span class="sxs-lookup"><span data-stu-id="5998e-200">The contents of the bam_BAMApiPo_Completed table are displayed in the right pane.</span></span> <span data-ttu-id="5998e-201">表中的每行均表示已完成的 BAMApiPo 活动。</span><span class="sxs-lookup"><span data-stu-id="5998e-201">Each row in the table represents a BAMApiPo activity that has been completed.</span></span>