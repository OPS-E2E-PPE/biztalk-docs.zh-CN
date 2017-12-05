---
title: "HTTPSolicitResponse |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP adapters, examples
- examples, HTTP adapters
ms.assetid: b149544e-3279-4ac9-b31f-fff3e41ec8e7
caps.latest.revision: "27"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 500ec05df9a3a365a350571e8b3e66f5d584f92d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="httpsolicitresponse"></a><span data-ttu-id="5b4e3-102">HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="5b4e3-102">HTTPSolicitResponse</span></span>
<span data-ttu-id="5b4e3-103">HTTPSolicitResponse 示例演示如何创建 Microsoft[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]利用 ASP.NET 应用程序以帮助处理 orchestration 数据的业务流程。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-103">The HTTPSolicitResponse sample demonstrates how to create a Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration that leverages an ASP.NET application to help process orchestration data.</span></span> <span data-ttu-id="5b4e3-104">在本示例中，业务流程利用请求/响应端口将消息发送到 ASP.NET 应用程序以及检索响应。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-104">In this sample, the orchestration makes use of a request/response port to send a message to the ASP.NET application and to retrieve the response.</span></span> <span data-ttu-id="5b4e3-105">使用 HTTP 适配器，您可以在 BizTalk Server 业务流程和 ASP.NET 应用程序之间实现集成。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-105">You achieve the integration between the BizTalk Server orchestration and the ASP.NET application by using the HTTP adapter.</span></span> <span data-ttu-id="5b4e3-106">有关详细信息，请参阅[HTTP 适配器](../core/http-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-106">For more information, see [HTTP Adapter](../core/http-adapter.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="5b4e3-107">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="5b4e3-107">What This Sample Does</span></span>  
 <span data-ttu-id="5b4e3-108">本示例包括通过以下步骤序列接收包含两个数字相乘的请求并满足该请求的 BizTalk Server 业务流程：</span><span class="sxs-lookup"><span data-stu-id="5b4e3-108">This sample consists of a BizTalk Server orchestration that receives a request containing two numbers to be multiplied, and satisfies that request using the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="5b4e3-109">BizTalk Server 业务流程从特定文件夹检索 .xml 输入文件。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-109">The BizTalk Server orchestration retrieves an .xml input file from a specific folder.</span></span>  
  
2.  <span data-ttu-id="5b4e3-110">业务流程使用 HTTP 请求将文件中的 XML 转发到乘数 ASP.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-110">The orchestration uses an HTTP request to forward the XML from the file to a multiplier ASP.NET application.</span></span>  
  
3.  <span data-ttu-id="5b4e3-111">乘数 ASP.NET 应用程序通过执行乘法并在 HTTP 响应中返回 XML 形式的结果，响应 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-111">The multiplier ASP.NET application responds to the HTTP request by performing the multiplication and returning the result as XML in the HTTP response.</span></span>  
  
4.  <span data-ttu-id="5b4e3-112">业务流程在 HTTP 响应中接收 XML 形式的结果，并将该结果写入特定文件夹中的 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-112">The orchestration receives the result as XML in an HTTP response, and writes that result to an .xml file in a specific folder.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="5b4e3-113">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="5b4e3-113">Where to Find This Sample</span></span>  
 <span data-ttu-id="5b4e3-114">\<*示例路径*\>\AdaptersUsage\HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="5b4e3-114">\<*Samples Path*\>\AdaptersUsage\HTTPSolicitResponse</span></span>  
  
 <span data-ttu-id="5b4e3-115">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="5b4e3-115">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="5b4e3-116">文件</span><span class="sxs-lookup"><span data-stu-id="5b4e3-116">File(s)</span></span>|<span data-ttu-id="5b4e3-117">Description</span><span class="sxs-lookup"><span data-stu-id="5b4e3-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5b4e3-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="5b4e3-118">Cleanup.bat</span></span>|<span data-ttu-id="5b4e3-119">取消部署程序集并将其从全局程序集缓存 (GAC) 中删除；删除发送和接收端口；根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-119">Undeploys assemblies and removes them from the global assembly cache (GAC); removes send and receive ports; removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="5b4e3-120">HttpSolicitResponse.btproj、HttpSolicitResponse.sln</span><span class="sxs-lookup"><span data-stu-id="5b4e3-120">HttpSolicitResponse.btproj, HttpSolicitResponse.sln</span></span>|<span data-ttu-id="5b4e3-121">提供 BizTalk 项目的项目和源文件，该项目包含使用乘数 ASP.NET 应用程序、关联架构等的业务流程。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-121">Provides project and source files for the BizTalk project that contains the orchestration that uses the multiplier ASP.NET application, the associated schemas, and so on.</span></span>|  
|<span data-ttu-id="5b4e3-122">HttpSolicitResponseBinding.xml</span><span class="sxs-lookup"><span data-stu-id="5b4e3-122">HttpSolicitResponseBinding.xml</span></span>|<span data-ttu-id="5b4e3-123">用于进行自动设置，如端口绑定。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-123">Provides for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="5b4e3-124">MultiplyRequest.xsd、MultiplyResponse.xsd</span><span class="sxs-lookup"><span data-stu-id="5b4e3-124">MultiplyRequest.xsd, MultiplyResponse.xsd</span></span>|<span data-ttu-id="5b4e3-125">分别提供乘法请求和响应 XML 消息的架构。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-125">Provides schemas for the multiplication request and response XML messages, respectively.</span></span>|  
|<span data-ttu-id="5b4e3-126">MultiplyTwoIntegers.odx</span><span class="sxs-lookup"><span data-stu-id="5b4e3-126">MultiplyTwoIntegers.odx</span></span>|<span data-ttu-id="5b4e3-127">提供接收请求乘法运算的 .xml 文件，将请求转发到乘数 ASP.NET 应用程序，并将其响应写入文件的 BizTalk Server 业务流程。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-127">Provides a BizTalk Server orchestration that receives an .xml file requesting a multiplication operation, forwards the request to the multiplier ASP.NET application, and writes its response to a file.</span></span>|  
|<span data-ttu-id="5b4e3-128">request_in.xml</span><span class="sxs-lookup"><span data-stu-id="5b4e3-128">request_in.xml</span></span>|<span data-ttu-id="5b4e3-129">示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-129">Sample input file.</span></span>|  
|<span data-ttu-id="5b4e3-130">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="5b4e3-130">Setup.bat</span></span>|<span data-ttu-id="5b4e3-131">生成并初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-131">Builds and initializes this sample.</span></span>|  
|<span data-ttu-id="5b4e3-132">在 \Multiplier 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="5b4e3-132">In the \Multiplier folder:</span></span><br /><br /> <span data-ttu-id="5b4e3-133">Multiplier.aspx、 Multiplier.aspx.cs，Multiplier.sln</span><span class="sxs-lookup"><span data-stu-id="5b4e3-133">Multiplier.aspx, Multiplier.aspx.cs, Multiplier.sln</span></span>|<span data-ttu-id="5b4e3-134">包含构成实现乘数服务的 ASP.NET 应用程序的文件，其中包括项目和解决方案文件、ASPX 文件以及 Microsoft Visual C# .NET 源文件等。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-134">Contains files that constitute the ASP.NET application that implements the multiplier service, including project and solution files, ASPX files, Microsoft Visual C# .NET source files, and so on.</span></span>|  
  
## <a name="building-and-initializing-the-sample"></a><span data-ttu-id="5b4e3-135">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="5b4e3-135">Building and Initializing the Sample</span></span>  
 <span data-ttu-id="5b4e3-136">使用以下过程可以生成并初始化 HTTPSolicitResponse 示例。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-136">Use the following procedure to build and initialize the HTTPSolicitResponse sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5b4e3-137">如果接收位置的名称包含任何大写字符，则本示例无法运行。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-137">This sample doesn't work if the name of the receive location contains any uppercase characters.</span></span>  
  
#### <a name="to-build-and-initialize-the-sample"></a><span data-ttu-id="5b4e3-138">生成并初始化示例</span><span class="sxs-lookup"><span data-stu-id="5b4e3-138">To build and initialize the sample</span></span>  
  
1.  <span data-ttu-id="5b4e3-139">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="5b4e3-139">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="5b4e3-140">\<*示例路径*\>\AdaptersUsage\HTTPSolicitResponse</span><span class="sxs-lookup"><span data-stu-id="5b4e3-140">\<*Samples Path*\>\AdaptersUsage\HTTPSolicitResponse</span></span>  
  
2.  <span data-ttu-id="5b4e3-141">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="5b4e3-141">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="5b4e3-142">为本示例创建输入和输出文件夹：</span><span class="sxs-lookup"><span data-stu-id="5b4e3-142">Creates the input and output folders for this sample:</span></span>  
  
         <span data-ttu-id="5b4e3-143">\<*示例路径*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseInput</span><span class="sxs-lookup"><span data-stu-id="5b4e3-143">\<*Samples Path*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseInput</span></span>  
  
         <span data-ttu-id="5b4e3-144">\<*示例路径*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseOutput</span><span class="sxs-lookup"><span data-stu-id="5b4e3-144">\<*Samples Path*\>\AdaptersUsage\HttpSolicitResponse\HttpSolicitResponseOutput</span></span>  
  
    -   <span data-ttu-id="5b4e3-145">编译并配置本示例使用的 ASP.NET 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-145">Compiles and configures the multiplier ASP.NET application used by this sample.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5b4e3-146">在创建应用程序池在 IIS 管理器，设置**DefaultAppPool**到.NET Framework 版本**.Net Framework v4.0**。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-146">While creating application pool in IIS Manager, set the **DefaultAppPool** .NET Framework version to **.Net Framework v4.0**.</span></span>  
  
    -   <span data-ttu-id="5b4e3-147">编译并部署本示例中使用的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-147">Compiles and deploys the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration used in this sample.</span></span>  
  
    -   <span data-ttu-id="5b4e3-148">创建并绑定必需的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置和端口。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-148">Creates and binds the necessary [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location and ports.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5b4e3-149">在创建并绑定端口时，本示例将显示以下警告：</span><span class="sxs-lookup"><span data-stu-id="5b4e3-149">This sample displays the following warnings when creating and binding the ports:</span></span>  
  
        > [!NOTE]
        >  `Warning: Receive handler not specified for receive location "HttpSolicitResponseReceiveLocation"; updating with first receive handler with matching transport type.`  
  
        > [!NOTE]
        >  `Warning: Host not specified for orchestration "Microsoft.Samples.BizTalk.HttpSolicitResponse.MultiplyTwoIntegers"; updating with first available host.`  
  
    -   <span data-ttu-id="5b4e3-150">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-150">Enables the receive location, and starts the send port.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5b4e3-151">本示例中的业务流程使用双向端口与 ASP.NET 应用程序进行 HTTP 交互。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-151">The orchestration in this sample uses a two-way port for the HTTP interaction with the ASP.NET application.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5b4e3-152">在尝试运行本示例之前，应确认在生成和初始化过程中 BizTalk 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-152">You should confirm that BizTalk did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5b4e3-153">如果选择在不运行 Setup.bat 文件的情况下打开并生成本示例中的项目，则必须先使用 .NET Framework 强名称实用工具 (sn.exe) 创建一个强名称密钥对。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-153">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name Utility (sn.exe).</span></span> <span data-ttu-id="5b4e3-154">使用该密钥对可以对生成的程序集签名。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-154">Use this key pair to sign the resulting assemblies.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="5b4e3-155">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-155">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="5b4e3-156">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-156">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-the-sample"></a><span data-ttu-id="5b4e3-157">运行示例</span><span class="sxs-lookup"><span data-stu-id="5b4e3-157">Running the Sample</span></span>  
 <span data-ttu-id="5b4e3-158">使用以下过程可以运行 HTTPSolicitResponse 示例。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-158">Use the following procedure to run the HTTPSolicitResponse sample.</span></span>  
  
#### <a name="to-run-the-sample"></a><span data-ttu-id="5b4e3-159">运行示例</span><span class="sxs-lookup"><span data-stu-id="5b4e3-159">To run the sample</span></span>  
  
1.  <span data-ttu-id="5b4e3-160">将文件 request_in.xml 的副本粘贴到文件夹 HttpSolicitResponseInput 中。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-160">Paste a copy of the file request_in.xml into the folder HttpSolicitResponseInput.</span></span>  
  
2.  <span data-ttu-id="5b4e3-161">查看在 HttpSolicitResponseOutput 文件夹中创建的 .xml 文件。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-161">Observe the .xml file created in the folder HttpSolicitResponseOutput.</span></span> <span data-ttu-id="5b4e3-162">此 .xml 文件是根据消息 ID GUID 命名的。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-162">The name of this .xml file is based on the message ID GUID.</span></span> <span data-ttu-id="5b4e3-163">此文件包含 XML 格式的乘法运算结果。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-163">This file contains the XML-formatted result of the multiplication operation.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5b4e3-164">若要执行不同的乘法运算，可以更改输入文件中的操作数的值。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-164">You can change the operand values in the input file to perform a different multiplication operation.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="5b4e3-165">注释</span><span class="sxs-lookup"><span data-stu-id="5b4e3-165">Comments</span></span>  
 <span data-ttu-id="5b4e3-166">可以调整本示例以与公开 HTTP 接口的不同外部系统进行通信。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-166">You can adapt this sample to communicate with a different external system that exposes an HTTP interface.</span></span>  
  
 <span data-ttu-id="5b4e3-167">文件 MultiplyRequest.xsd 和 MultiplyResponse.xsd 是为乘数 ASP.NET 应用程序定义输入和输出数据格式的 XML 架构。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-167">The files MultiplyRequest.xsd and MultiplyResponse.xsd are the XML schemas that define the format of the input and output data for the multiplier ASP.NET application.</span></span> <span data-ttu-id="5b4e3-168">业务流程使用这些文件定义请求和响应消息类型。</span><span class="sxs-lookup"><span data-stu-id="5b4e3-168">The orchestration uses these files to define the request and response message types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b4e3-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5b4e3-169">See Also</span></span>  
 [<span data-ttu-id="5b4e3-170">HTTP 适配器示例</span><span class="sxs-lookup"><span data-stu-id="5b4e3-170">HTTP Adapter Samples</span></span>](../core/http-adapter-samples.md)