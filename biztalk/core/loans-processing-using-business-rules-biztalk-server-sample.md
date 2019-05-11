---
title: 加载处理使用业务规则 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: 3e1c80c6-adc1-4a0f-83fd-409ce1b8f21f
caps.latest.revision: 28
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8b878b782c49f1fc4827577444b8bffbec346fe
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65380620"
---
# <a name="loans-processing-using-business-rules-biztalk-server-sample"></a><span data-ttu-id="d0c9f-102">贷款处理使用业务规则 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="d0c9f-102">Loans Processing Using Business Rules (BizTalk Server Sample)</span></span>
<span data-ttu-id="d0c9f-103">贷款处理使用业务规则的示例演示如何使用管理业务流程中的规则集以及如何使用的输入称为事实，组合来计算正在处理的文档中某些字段的设置。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-103">The Loans Processing Using Business Rules sample demonstrates how to use a set of rules managed within an orchestration, and how to use a combination of inputs known as facts, to calculate settings for some fields within a document being processed.</span></span> <span data-ttu-id="d0c9f-104">事实可以是调用的结果。基于 NET 的程序集，从消息的 XML 中检索的值或从数据库检索到的数据。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-104">Facts can be the result of calling a .NET-based assembly, the values retrieved from the XML of the message, or the data retrieved from a database.</span></span> <span data-ttu-id="d0c9f-105">此示例还演示如何更改这些规则在任何时候，会影响随后的计算，而无需重新部署。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-105">The sample also demonstrates how you can change the rules at any time, affecting subsequent calculations without the need to redeploy.</span></span>  

## <a name="what-this-sample-does"></a><span data-ttu-id="d0c9f-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="d0c9f-106">What This Sample Does</span></span>  
 <span data-ttu-id="d0c9f-107">此示例演示简化的贷款处理方案的上下文中的这些功能。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-107">This sample demonstrates these capabilities within the context of a simplified loan processing scenario.</span></span> <span data-ttu-id="d0c9f-108">BizTalk Server 业务流程提取并处理的贷款申请，也称为贷款案例，XML 消息格式。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-108">BizTalk Server orchestration picks up and processes a loan application, also known as a loan case, in XML message format.</span></span> <span data-ttu-id="d0c9f-109">此业务流程使用业务规则引擎评估传入消息根据规则，修改结果的规则，该应用程序的消息，然后将消息写入一个文件作为输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-109">This orchestration uses the Business Rule Engine to evaluate incoming messages according to the rules, modifying the message with the result of the application of the rules, and then writing the message as a file to an output folder.</span></span>  

 <span data-ttu-id="d0c9f-110">基于多个源，包括正在处理的消息的事实此示例设置**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，并且**ResidencyStatus**正在处理的消息的元素。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-110">Based on facts from several sources, including the message being processed, this sample sets the **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus** elements of the message being processed.</span></span>  

## <a name="where-to-find-this-sample"></a><span data-ttu-id="d0c9f-111">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="d0c9f-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="d0c9f-112">\<*示例路径*\>\Business Rules\Loans 处理使用业务 Rules\\</span><span class="sxs-lookup"><span data-stu-id="d0c9f-112">\<*Samples Path*\>\Business Rules\Loans Processing using Business Rules\\</span></span>  

 <span data-ttu-id="d0c9f-113">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="d0c9f-113">The following table shows the files in this sample and describes their purpose.</span></span>  


|                                                                                    <span data-ttu-id="d0c9f-114">文件</span><span class="sxs-lookup"><span data-stu-id="d0c9f-114">File(s)</span></span>                                                                                    |                                                                                                                <span data-ttu-id="d0c9f-115">Description</span><span class="sxs-lookup"><span data-stu-id="d0c9f-115">Description</span></span>                                                                                                                 |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                                                   <span data-ttu-id="d0c9f-116">Case.xsd</span><span class="sxs-lookup"><span data-stu-id="d0c9f-116">Case.xsd</span></span>                                                                                    |                                                                                 <span data-ttu-id="d0c9f-117">对于入站的贷款应用程序，也称为贷款案例的架构文件。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-117">Schema file for inbound loan applications, otherwise known as loan cases.</span></span>                                                                                  |
|                                                                                  <span data-ttu-id="d0c9f-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="d0c9f-118">Cleanup.bat</span></span>                                                                                  |                   <span data-ttu-id="d0c9f-119">用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-119">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="d0c9f-120">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-120">Removes send and receive ports.</span></span> <span data-ttu-id="d0c9f-121">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-121">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>                   |
|                                                                           <span data-ttu-id="d0c9f-122">Create_CustInfo_Table.sql</span><span class="sxs-lookup"><span data-stu-id="d0c9f-122">Create_CustInfo_Table.sql</span></span>                                                                           |                                                                              <span data-ttu-id="d0c9f-123">在 SQL Northwind 示例数据库中创建 CustInfo 表的 SQL 脚本。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-123">SQL script for creating the CustInfo table in the SQL Northwind sample database.</span></span>                                                                              |
|                                                                           <span data-ttu-id="d0c9f-124">LoanProcessorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="d0c9f-124">LoanProcessorBinding.xml</span></span>                                                                            |                                                                                               <span data-ttu-id="d0c9f-125">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-125">Used for automated setup such as port binding.</span></span>                                                                                               |
|                                                                   <span data-ttu-id="d0c9f-126">LoansProcessor.btproj, LoansProcessor.sln</span><span class="sxs-lookup"><span data-stu-id="d0c9f-126">LoansProcessor.btproj, LoansProcessor.sln</span></span>                                                                   |                                                                                            <span data-ttu-id="d0c9f-127">此示例的 BizTalk 项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-127">BizTalk project and solution files for this sample.</span></span>                                                                                             |
|                                                                             <span data-ttu-id="d0c9f-128">我的示例 Service.odx</span><span class="sxs-lookup"><span data-stu-id="d0c9f-128">My Sample Service.odx</span></span>                                                                             |                                                             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="d0c9f-129">此示例的业务流程。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-129">orchestration for this sample.</span></span>                                                              |
|                                                                                <span data-ttu-id="d0c9f-130">sampleLoan.xml</span><span class="sxs-lookup"><span data-stu-id="d0c9f-130">sampleLoan.xml</span></span>                                                                                 |                                                               <span data-ttu-id="d0c9f-131">示例输入的文件，与在文件中的 XML 结构末尾的四个状态元素的空值。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-131">Sample input file, with empty values for the four status elements at the end of the XML structure in the file.</span></span>                                                               |
|                                                                                   <span data-ttu-id="d0c9f-132">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="d0c9f-132">Setup.bat</span></span>                                                                                   |                                                                                                 <span data-ttu-id="d0c9f-133">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-133">Used to build and initialize this sample.</span></span>                                                                                                  |
|         <span data-ttu-id="d0c9f-134">在 \CreateRules 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d0c9f-134">In the \CreateRules folder:</span></span><br /><br /> <span data-ttu-id="d0c9f-135">App.ico、 AssemblyInfo.cs、 Case.xsd、 CreateLoanProcessingPolicy.csproj、 CreateLoanProcessingPolicy.sln、 WriteToBRL.cs</span><span class="sxs-lookup"><span data-stu-id="d0c9f-135">App.ico, AssemblyInfo.cs, Case.xsd, CreateLoanProcessingPolicy.csproj, CreateLoanProcessingPolicy.sln, WriteToBRL.cs</span></span>          | <span data-ttu-id="d0c9f-136">Visual C# 项目、 解决方案、 源和用于创建以编程方式创建的规则，在集中的应用程序的相关的文件。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-136">Visual C# project, solution, source, and related files used to create the application that programmatically creates the rules in the set.</span></span> <span data-ttu-id="d0c9f-137">有关以编程方式构建的规则集的示例，请参阅源文件 WriteToBRL.cs。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-137">For examples of programmatically building sets of rules, refer to the source file WriteToBRL.cs.</span></span> |
| <span data-ttu-id="d0c9f-138">在 \myFactRetriever 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d0c9f-138">In the \myFactRetriever folder:</span></span><br /><br /> <span data-ttu-id="d0c9f-139">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="d0c9f-139">AssemblyInfo.cs</span></span><br /><br /> <span data-ttu-id="d0c9f-140">FactRetrieverForLoansProcessing.cs</span><span class="sxs-lookup"><span data-stu-id="d0c9f-140">FactRetrieverForLoansProcessing.cs</span></span><br /><br /> <span data-ttu-id="d0c9f-141">myFactRetriever.csproj</span><span class="sxs-lookup"><span data-stu-id="d0c9f-141">myFactRetriever.csproj</span></span><br /><br /> <span data-ttu-id="d0c9f-142">myFactRetriever.sln</span><span class="sxs-lookup"><span data-stu-id="d0c9f-142">myFactRetriever.sln</span></span> |                 <span data-ttu-id="d0c9f-143">Visual C# 项目、 解决方案、 源和相关的文件，用于创建使用从先前添加到 Northwind 示例 SQL Server 数据库的 CustInfo 表检索信息的程序集。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-143">Visual C# project, solution, source, and related files used to create an assembly that you use to retrieve information from the CustInfo table added earlier to the Northwind sample SQL Server database.</span></span>                  |

## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="d0c9f-144">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="d0c9f-144">Building and Initializing This Sample</span></span>  

#### <a name="to-build-and-initialize-the-loans-processing-using-business-rules-sample"></a><span data-ttu-id="d0c9f-145">若要生成并初始化贷款处理使用业务规则示例</span><span class="sxs-lookup"><span data-stu-id="d0c9f-145">To build and initialize the Loans Processing Using Business Rules sample</span></span>  

1. <span data-ttu-id="d0c9f-146">请确保你的计算机上具有 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-146">Make sure that you have the Northwind database on your machine.</span></span>  

   > [!IMPORTANT]
   >  <span data-ttu-id="d0c9f-147">若要运行此示例，必须具有 Northwind SQL Server 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-147">To run this sample, you must have the Northwind SQL Server sample database.</span></span> <span data-ttu-id="d0c9f-148">[下载](https://www.microsoft.com/download/details.aspx?id=23654)，并安装。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-148">[Download](https://www.microsoft.com/download/details.aspx?id=23654), and install.</span></span> 

2. <span data-ttu-id="d0c9f-149">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="d0c9f-149">In a command window, navigate to the following folder:</span></span>  

    <span data-ttu-id="d0c9f-150">\<*示例路径*\>\Business Rules\Loans 处理使用业务规则</span><span class="sxs-lookup"><span data-stu-id="d0c9f-150">\<*Samples Path*\>\Business Rules\Loans Processing using Business Rules</span></span>  

3. <span data-ttu-id="d0c9f-151">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d0c9f-151">Run the file Setup.bat, which performs the following actions:</span></span>  

   - <span data-ttu-id="d0c9f-152">清理 GAC 以消除之前运行此示例中的任何剩余数据。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-152">Cleans up the GAC to eliminate any residual data from previous runs of this sample.</span></span>  

   - <span data-ttu-id="d0c9f-153">编译并部署事实检索器程序 myFactRetreiever.dll。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-153">Compiles and deploys the fact retriever program, myFactRetreiever.dll.</span></span>  

   - <span data-ttu-id="d0c9f-154">使用 SQL 脚本文件 Create_CustInfo_Table.sql，将添加到 Northwind 示例 SQL 数据库名为 CustInfo 的表。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-154">Using the SQL script file Create_CustInfo_Table.sql, adds a table named CustInfo to the Northwind sample SQL database.</span></span>  

   - <span data-ttu-id="d0c9f-155">清理共享 SQL 规则存储以消除之前运行此示例的剩余部分。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-155">Cleans up the shared SQL rule store to eliminate residue of previous runs of this sample.</span></span>  

   - <span data-ttu-id="d0c9f-156">创建、 发布，并部署贷款处理规则集的最新版本 (1.0)。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-156">Creates, publishes, and deploys the most recent version (1.0) of the loans processing rule set.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="d0c9f-157">可以使用业务规则编辑器工具提供与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]检查以编程方式设置的规则。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-157">You can use the Business Rule Composer tool supplied with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to examine the rules that have been set programmatically.</span></span>  

   - <span data-ttu-id="d0c9f-158">创建输入 (In) 和输出 (Out) 文件夹对于此示例。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-158">Creates the input (In) and output (Out) folders for this sample.</span></span>  

   - <span data-ttu-id="d0c9f-159">编译并部署剩余[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]对于此示例，其中包括包含用于协调本示例的业务流程的 BizTalk 项目的项目。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-159">Compiles and deploys the remaining [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, including the BizTalk project that contains the orchestration you use to coordinate this sample.</span></span>  

   - <span data-ttu-id="d0c9f-160">创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-160">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  

     > [!NOTE]
     >  <span data-ttu-id="d0c9f-161">此示例将显示以下警告时创建并绑定端口：</span><span class="sxs-lookup"><span data-stu-id="d0c9f-161">This sample displays the following warnings when creating and binding ports:</span></span>  
     >   
     >  `Warning: Receive handler not specified for receive location "LoansProcessor_1.0.0.0_LoansProcessor.My_Sample_Service_Incoming_ReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "LoansProcessor.My_Sample_Service"; updating with first available host.`  
     >   
     >  <span data-ttu-id="d0c9f-162">您可以放心地忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-162">You can safely ignore these warnings.</span></span> <span data-ttu-id="d0c9f-163">（若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）</span><span class="sxs-lookup"><span data-stu-id="d0c9f-163">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  

   - <span data-ttu-id="d0c9f-164">启用该接收位置，并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-164">Enables the receive location, and starts the send port.</span></span>  

   - <span data-ttu-id="d0c9f-165">登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-165">Enlists and starts the orchestration.</span></span>  

> [!NOTE]
>  <span data-ttu-id="d0c9f-166">如果你的 BizTalk 主机名不是 BizTalkServerApplication，修改的文件 Setup.bat 文件和 LoanProcessorBinding.xml 以反映正确的主机名。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-166">If your BizTalk host name is not BizTalkServerApplication, modify the file Setup.bat and the file LoanProcessorBinding.xml to reflect the proper host name.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="d0c9f-167">您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-167">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="d0c9f-168">如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-168">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="d0c9f-169">使用此密钥对生成程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-169">Use this key pair to sign the resulting assemblies.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="d0c9f-170">若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-170">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="d0c9f-171">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-171">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  

## <a name="running-this-sample"></a><span data-ttu-id="d0c9f-172">运行本示例</span><span class="sxs-lookup"><span data-stu-id="d0c9f-172">Running This Sample</span></span>  

#### <a name="to-run-the-loans-processing-using-business-rules-sample"></a><span data-ttu-id="d0c9f-173">若要运行的贷款处理使用业务规则示例</span><span class="sxs-lookup"><span data-stu-id="d0c9f-173">To run the Loans Processing Using Business Rules sample</span></span>  

1. <span data-ttu-id="d0c9f-174">到文件 sampleLoan.xml 的副本粘贴**\In**文件夹。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-174">Paste a copy of the file sampleLoan.xml into the **\In** folder.</span></span>  

2. <span data-ttu-id="d0c9f-175">查看文件夹中创建的.xml 文件**出**。它包含输入的 XML 消息添加到以下四个状态元素的 XML 结构末尾的数据：**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，并且**ResidencyStatus**。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-175">Observe the .xml file created in the folder **Out**. It contains the input XML message with data added to the following four status elements at the end of the XML structure: **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus**.</span></span>  

   <span data-ttu-id="d0c9f-176">可以使用业务规则编辑器工具更改规则集中规则并重新部署这些规则。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-176">You can use the Business Rule Composer tool to change the rules in the rule set, and then redeploy those rules.</span></span>  

#### <a name="to-use-the-business-rule-composer-tool-to-change-one-or-more-of-the-rules-in-a-rule-set"></a><span data-ttu-id="d0c9f-177">若要使用业务规则编辑器工具更改一个或多个规则组中的规则</span><span class="sxs-lookup"><span data-stu-id="d0c9f-177">To use the Business Rule Composer tool to change one or more of the rules in a rule set</span></span>  

1. <span data-ttu-id="d0c9f-178">单击**启动**，依次指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-178">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rule Composer**.</span></span>  

   > [!NOTE]
   >  <span data-ttu-id="d0c9f-179">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-179">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d0c9f-180">要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-180">To do this, right-click the application, and then select **Run as administrator**.</span></span>  

2. <span data-ttu-id="d0c9f-181">在中**SQL Server**对话框中，单击**确定**连接到规则存储。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-181">In the **SQL Server** dialog box, click **OK** to connect to the rule store.</span></span>  

3. <span data-ttu-id="d0c9f-182">在**策略浏览器**，节点的下级**LoanProcessing**，右键单击**版本 1.0 – 已部署**节点，并单击**复制**。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-182">In **Policy Explorer**, below the node **LoanProcessing**, right-click the **Version 1.0 – Deployed** node, and then click **Copy**.</span></span>  

4. <span data-ttu-id="d0c9f-183">右键单击**LoanProcessing**，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-183">Right-click **LoanProcessing**, and then click **Paste**.</span></span>  

5. <span data-ttu-id="d0c9f-184">更改任何规则或操作将导致不同的值的方式**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，和**ResidencyStatus**元素。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-184">Change any rule or action in a way that will result in different values for the **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus** elements.</span></span> <span data-ttu-id="d0c9f-185">确保也更改的值求反运算部分 (实质上， **Else**子句) 选择要更改任何规则。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-185">Ensure that you also change the value of the negation portion (essentially, the **Else** clause) of any rule that you choose to change.</span></span>  

    <span data-ttu-id="d0c9f-186">下表显示了此示例使用的规则集。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-186">The following table shows the set of rules used by this sample.</span></span> <span data-ttu-id="d0c9f-187">除非明确提及，否则事实是从传入的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-187">Unless specifically mentioned otherwise, facts are from the incoming XML message.</span></span> <span data-ttu-id="d0c9f-188">字符串 (db) 表示数据库作为事实的源。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-188">The string (db) indicates a database as the source of a fact.</span></span>  


   |  <span data-ttu-id="d0c9f-189">规则编号</span><span class="sxs-lookup"><span data-stu-id="d0c9f-189">Rule number</span></span>   |        <span data-ttu-id="d0c9f-190">规则名称</span><span class="sxs-lookup"><span data-stu-id="d0c9f-190">Rule name</span></span>        |                                                                             <span data-ttu-id="d0c9f-191">Description</span><span class="sxs-lookup"><span data-stu-id="d0c9f-191">Description</span></span>                                                                             |
   |----------------|-------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |       <span data-ttu-id="d0c9f-192">1</span><span class="sxs-lookup"><span data-stu-id="d0c9f-192">1</span></span>        |   <span data-ttu-id="d0c9f-193">收入状态规则</span><span class="sxs-lookup"><span data-stu-id="d0c9f-193">Income Status Rule</span></span>    |                                       <span data-ttu-id="d0c9f-194">IF **BasicSalary** + **OtherIncome** > 0</span><span class="sxs-lookup"><span data-stu-id="d0c9f-194">IF **BasicSalary** + **OtherIncome** > 0</span></span><br /><br /> <span data-ttu-id="d0c9f-195">然后**IncomeStatus** = **有效**</span><span class="sxs-lookup"><span data-stu-id="d0c9f-195">THEN **IncomeStatus** = **Valid**</span></span>                                        |
   |       <span data-ttu-id="d0c9f-196">2</span><span class="sxs-lookup"><span data-stu-id="d0c9f-196">2</span></span>        | <span data-ttu-id="d0c9f-197">承诺状态规则</span><span class="sxs-lookup"><span data-stu-id="d0c9f-197">Commitments Status Rule</span></span> | <span data-ttu-id="d0c9f-198">如果**ID** == **ID (db)**</span><span class="sxs-lookup"><span data-stu-id="d0c9f-198">IF **ID** == **ID (db)**</span></span><br /><br /> <span data-ttu-id="d0c9f-199">和</span><span class="sxs-lookup"><span data-stu-id="d0c9f-199">AND</span></span><br /><br /> <span data-ttu-id="d0c9f-200">IF **CreditCardBalance (db)** > 500</span><span class="sxs-lookup"><span data-stu-id="d0c9f-200">IF **CreditCardBalance (db)** > 500</span></span><br /><br /> <span data-ttu-id="d0c9f-201">然后**CommitmentsStatus** =</span><span class="sxs-lookup"><span data-stu-id="d0c9f-201">THEN **CommitmentsStatus** =</span></span><br /><br /> <span data-ttu-id="d0c9f-202">"计算承诺"</span><span class="sxs-lookup"><span data-stu-id="d0c9f-202">"Compute Commitments"</span></span> |
   |       <span data-ttu-id="d0c9f-203">3</span><span class="sxs-lookup"><span data-stu-id="d0c9f-203">3</span></span>        | <span data-ttu-id="d0c9f-204">就业状态规则</span><span class="sxs-lookup"><span data-stu-id="d0c9f-204">Employment Status Rule</span></span>  |                                  <span data-ttu-id="d0c9f-205">如果**EmploymentType &#124; TimeInMonths** > 18</span><span class="sxs-lookup"><span data-stu-id="d0c9f-205">IF **EmploymentType &#124; TimeInMonths** > 18</span></span><br /><br /> <span data-ttu-id="d0c9f-206">然后**EmploymentStatus** = **有效**</span><span class="sxs-lookup"><span data-stu-id="d0c9f-206">THEN **EmploymentStatus** = **Valid**</span></span>                                   |
   |       <span data-ttu-id="d0c9f-207">4</span><span class="sxs-lookup"><span data-stu-id="d0c9f-207">4</span></span>        |  <span data-ttu-id="d0c9f-208">Residency Status Rule</span><span class="sxs-lookup"><span data-stu-id="d0c9f-208">Residency Status Rule</span></span>  |                                  <span data-ttu-id="d0c9f-209">IF **PlaceOfResidence &#124; TimeInMonths** > 18</span><span class="sxs-lookup"><span data-stu-id="d0c9f-209">IF **PlaceOfResidence &#124; TimeInMonths** > 18</span></span><br /><br /> <span data-ttu-id="d0c9f-210">然后**ResidencyStatus** = **有效**</span><span class="sxs-lookup"><span data-stu-id="d0c9f-210">THEN **ResidencyStatus** = **Valid**</span></span>                                  |
   | <span data-ttu-id="d0c9f-211">!1, !2, !3, !4</span><span class="sxs-lookup"><span data-stu-id="d0c9f-211">!1, !2, !3, !4</span></span> |     <span data-ttu-id="d0c9f-212">求反运算规则</span><span class="sxs-lookup"><span data-stu-id="d0c9f-212">Negation Rules</span></span>      |    <span data-ttu-id="d0c9f-213">条件的逻辑**不**规则 1 – 4 中所述相应条件。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-213">Conditions that are a logical **NOT** of the corresponding condition described in rules 1–4.</span></span> <span data-ttu-id="d0c9f-214">引发的操作是更改正在设置的字符串。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-214">Resulting actions are a change in the string that is being set.</span></span>     |


6. <span data-ttu-id="d0c9f-215">右键单击**版本 1.1 （未保存）** 节点，并单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-215">Right-click the **Version 1.1(not saved)** node, and then click **Save**.</span></span>  

7. <span data-ttu-id="d0c9f-216">右键单击**1.1 版**节点，并单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-216">Right-click the **Version 1.1** node, and then click **Publish**.</span></span>  

8. <span data-ttu-id="d0c9f-217">右键单击**1.1 版**节点，并单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-217">Right-click the **Version 1.1** node, and then click **Deploy**.</span></span>  

9. <span data-ttu-id="d0c9f-218">等待 60 秒以使更改传播到共享 SQL Server 规则存储。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-218">Wait for 60 seconds for the changes to propagate to the shared SQL Server rule store.</span></span>  

10. <span data-ttu-id="d0c9f-219">将文件 sampleLoan.xml 的副本粘贴到文件夹**在**。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-219">Paste a copy of the file sampleLoan.xml into the folder **In**.</span></span>  

11. <span data-ttu-id="d0c9f-220">查看文件夹中创建的.xml 文件**出**。它包含输入的 XML 消息添加到以下四个状态元素的 XML 结构末尾的数据：**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，并且**ResidencyStatus**。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-220">Observe the .xml file created in the folder **Out**. It contains the input XML message with data added to the following four status elements at the end of the XML structure: **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus**.</span></span> <span data-ttu-id="d0c9f-221">添加到这些元素的数据将可能不同，从上一个运行，基于此过程的步骤 5 中所做的更改的性质。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-221">The data added to these elements will differ, or not, from the previous run, based on the nature of the changes made in step 5in this procedure.</span></span>  

## <a name="comments"></a><span data-ttu-id="d0c9f-222">注释</span><span class="sxs-lookup"><span data-stu-id="d0c9f-222">Comments</span></span>  
 <span data-ttu-id="d0c9f-223">如果你想要查看此示例的跟踪信息，必须取消部署和使用业务规则引擎部署向导，然后重新部署相关规则集 （贷款处理）。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-223">If you want to view the tracking information for this sample, you must undeploy and then redeploy the relevant rule set (Loans Processing) by using the Business Rules Engine Deployment Wizard.</span></span>  

 <span data-ttu-id="d0c9f-224">此示例演示如何使用业务规则应用形式的业务流程内规则的业务策略。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-224">This sample demonstrates how you can use business rules to apply business policies in the form of rules within an orchestration.</span></span> <span data-ttu-id="d0c9f-225">它还演示了如何更改策略，并在业务流程内动态反映而无需重新编译或重新部署业务流程解决方案在策略中已更改。</span><span class="sxs-lookup"><span data-stu-id="d0c9f-225">It also demonstrates how you can change the policies, and have the change in the policy reflected dynamically within the orchestration without having to recompile or redeploy the orchestration solution.</span></span>  

 <span data-ttu-id="d0c9f-226">输入的贷款案例为此示例是具有以下结构的 XML 消息：</span><span class="sxs-lookup"><span data-stu-id="d0c9f-226">Input loan cases to this sample are XML messages that have the following structure:</span></span>  

```  
    Name  
    ID  
    Income  
        BasicSalary  
        OtherIncome  
    EmploymentType  
        TimeInMonths  
    PlaceOfResidence  
        TimeInMonths  
    CommitmentsStatus  
    IncomeStatus  
    EmploymentStatus  
    ResidencyStatus  
```  

## <a name="see-also"></a><span data-ttu-id="d0c9f-227">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0c9f-227">See Also</span></span>  
 [<span data-ttu-id="d0c9f-228">业务规则（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="d0c9f-228">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)