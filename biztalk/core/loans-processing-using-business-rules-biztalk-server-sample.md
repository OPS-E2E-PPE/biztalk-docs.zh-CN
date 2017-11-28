---
title: "借处理使用业务规则 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, business rules
- business rules, examples
ms.assetid: 3e1c80c6-adc1-4a0f-83fd-409ce1b8f21f
caps.latest.revision: "28"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c51f0ff13b06bd57ccdd52ec6e35fdd7e0acf839
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="loans-processing-using-business-rules-biztalk-server-sample"></a><span data-ttu-id="0f64c-102">贷款处理使用业务规则 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="0f64c-102">Loans Processing Using Business Rules (BizTalk Server Sample)</span></span>
<span data-ttu-id="0f64c-103">使用业务规则的贷款处理示例说明如何使用在业务流程中管理的规则集，以及如何使用输入组合（称为事实）来计算正在处理的文档中某些字段的设置。</span><span class="sxs-lookup"><span data-stu-id="0f64c-103">The Loans Processing Using Business Rules sample demonstrates how to use a set of rules managed within an orchestration, and how to use a combination of inputs known as facts, to calculate settings for some fields within a document being processed.</span></span> <span data-ttu-id="0f64c-104">事实可以是调用基于 .NET 的程序集的结果、从 XML 格式的消息中检索的值或从数据库检索的数据。</span><span class="sxs-lookup"><span data-stu-id="0f64c-104">Facts can be the result of calling a .NET-based assembly, the values retrieved from the XML of the message, or the data retrieved from a database.</span></span> <span data-ttu-id="0f64c-105">本示例还说明如何随时更改规则以便影响随后的计算，而无需重新部署。</span><span class="sxs-lookup"><span data-stu-id="0f64c-105">The sample also demonstrates how you can change the rules at any time, affecting subsequent calculations without the need to redeploy.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="0f64c-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="0f64c-106">What This Sample Does</span></span>  
 <span data-ttu-id="0f64c-107">本示例将在简化的贷款处理方案的上下文中说明这些功能。</span><span class="sxs-lookup"><span data-stu-id="0f64c-107">This sample demonstrates these capabilities within the context of a simplified loan processing scenario.</span></span> [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="0f64c-108"> 业务流程提取并处理 XML 消息格式的贷款申请（也称为贷款案例）。</span><span class="sxs-lookup"><span data-stu-id="0f64c-108"> orchestration picks up and processes a loan application, also known as a loan case, in XML message format.</span></span> <span data-ttu-id="0f64c-109">此业务流程将使用业务规则引擎根据规则评估传入消息，并利用规则申请结果修改消息，然后将消息以文件的形式写入输出文件夹。</span><span class="sxs-lookup"><span data-stu-id="0f64c-109">This orchestration uses the Business Rule Engine to evaluate incoming messages according to the rules, modifying the message with the result of the application of the rules, and then writing the message as a file to an output folder.</span></span>  
  
 <span data-ttu-id="0f64c-110">基于事实从多个源，包括消息处理，此示例会将设置**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，和**ResidencyStatus**正在处理的消息的元素。</span><span class="sxs-lookup"><span data-stu-id="0f64c-110">Based on facts from several sources, including the message being processed, this sample sets the **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus** elements of the message being processed.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="0f64c-111">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="0f64c-111">Where to Find This Sample</span></span>  
 <span data-ttu-id="0f64c-112">\<*示例路径*> \Business Rules\Loans 处理使用业务 Rules\\</span><span class="sxs-lookup"><span data-stu-id="0f64c-112">\<*Samples Path*>\Business Rules\Loans Processing using Business Rules\\</span></span>  
  
 <span data-ttu-id="0f64c-113">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="0f64c-113">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="0f64c-114">文件</span><span class="sxs-lookup"><span data-stu-id="0f64c-114">File(s)</span></span>|<span data-ttu-id="0f64c-115">Description</span><span class="sxs-lookup"><span data-stu-id="0f64c-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0f64c-116">Case.xsd</span><span class="sxs-lookup"><span data-stu-id="0f64c-116">Case.xsd</span></span>|<span data-ttu-id="0f64c-117">入站贷款申请（也称为贷款案例）的架构文件。</span><span class="sxs-lookup"><span data-stu-id="0f64c-117">Schema file for inbound loan applications, otherwise known as loan cases.</span></span>|  
|<span data-ttu-id="0f64c-118">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="0f64c-118">Cleanup.bat</span></span>|<span data-ttu-id="0f64c-119">用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="0f64c-119">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="0f64c-120">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="0f64c-120">Removes send and receive ports.</span></span> <span data-ttu-id="0f64c-121">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="0f64c-121">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="0f64c-122">Create_CustInfo_Table.sql</span><span class="sxs-lookup"><span data-stu-id="0f64c-122">Create_CustInfo_Table.sql</span></span>|<span data-ttu-id="0f64c-123">SQL 脚本，用于在 SQL Northwind 示例数据库中创建 CustInfo 表。</span><span class="sxs-lookup"><span data-stu-id="0f64c-123">SQL script for creating the CustInfo table in the SQL Northwind sample database.</span></span>|  
|<span data-ttu-id="0f64c-124">LoanProcessorBinding.xml</span><span class="sxs-lookup"><span data-stu-id="0f64c-124">LoanProcessorBinding.xml</span></span>|<span data-ttu-id="0f64c-125">用于如端口绑定之类的自动化设置。</span><span class="sxs-lookup"><span data-stu-id="0f64c-125">Used for automated setup such as port binding.</span></span>|  
|<span data-ttu-id="0f64c-126">LoansProcessor.btproj、LoansProcessor.sln</span><span class="sxs-lookup"><span data-stu-id="0f64c-126">LoansProcessor.btproj, LoansProcessor.sln</span></span>|<span data-ttu-id="0f64c-127">本示例的 BizTalk 项目和解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="0f64c-127">BizTalk project and solution files for this sample.</span></span>|  
|<span data-ttu-id="0f64c-128">My Sample Service.odx</span><span class="sxs-lookup"><span data-stu-id="0f64c-128">My Sample Service.odx</span></span>|<span data-ttu-id="0f64c-129">本示例的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 业务流程。</span><span class="sxs-lookup"><span data-stu-id="0f64c-129">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] orchestration for this sample.</span></span>|  
|<span data-ttu-id="0f64c-130">sampleLoan.xml</span><span class="sxs-lookup"><span data-stu-id="0f64c-130">sampleLoan.xml</span></span>|<span data-ttu-id="0f64c-131">示例输入文件，文件中 XML 结构末尾的四个状态元素的值为空。</span><span class="sxs-lookup"><span data-stu-id="0f64c-131">Sample input file, with empty values for the four status elements at the end of the XML structure in the file.</span></span>|  
|<span data-ttu-id="0f64c-132">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="0f64c-132">Setup.bat</span></span>|<span data-ttu-id="0f64c-133">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="0f64c-133">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="0f64c-134">\CreateRules 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="0f64c-134">In the \CreateRules folder:</span></span><br /><br /> <span data-ttu-id="0f64c-135">App.ico、AssemblyInfo.cs、Case.xsd、CreateLoanProcessingPolicy.csproj、CreateLoanProcessingPolicy.sln、WriteToBRL.cs</span><span class="sxs-lookup"><span data-stu-id="0f64c-135">App.ico, AssemblyInfo.cs, Case.xsd, CreateLoanProcessingPolicy.csproj, CreateLoanProcessingPolicy.sln, WriteToBRL.cs</span></span>|<span data-ttu-id="0f64c-136">用于创建应用程序的 Visual C# 项目、解决方案、源和相关文件，该应用程序将以编程方式创建规则集中的规则。</span><span class="sxs-lookup"><span data-stu-id="0f64c-136">Visual C# project, solution, source, and related files used to create the application that programmatically creates the rules in the set.</span></span> <span data-ttu-id="0f64c-137">有关以编程方式生成规则集的示例，请参阅源文件 WriteToBRL.cs。</span><span class="sxs-lookup"><span data-stu-id="0f64c-137">For examples of programmatically building sets of rules, refer to the source file WriteToBRL.cs.</span></span>|  
|<span data-ttu-id="0f64c-138">\myFactRetriever 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="0f64c-138">In the \myFactRetriever folder:</span></span><br /><br /> <span data-ttu-id="0f64c-139">AssemblyInfo.cs</span><span class="sxs-lookup"><span data-stu-id="0f64c-139">AssemblyInfo.cs</span></span><br /><br /> <span data-ttu-id="0f64c-140">FactRetrieverForLoansProcessing.cs</span><span class="sxs-lookup"><span data-stu-id="0f64c-140">FactRetrieverForLoansProcessing.cs</span></span><br /><br /> <span data-ttu-id="0f64c-141">myFactRetriever.csproj</span><span class="sxs-lookup"><span data-stu-id="0f64c-141">myFactRetriever.csproj</span></span><br /><br /> <span data-ttu-id="0f64c-142">myFactRetriever.sln</span><span class="sxs-lookup"><span data-stu-id="0f64c-142">myFactRetriever.sln</span></span>|<span data-ttu-id="0f64c-143">用于创建程序集的 Visual C# 项目、解决方案、源和相关文件，该程序集用于从先前添加到 Northwind 示例 SQL Server 数据库的 CustInfo 表检索信息。</span><span class="sxs-lookup"><span data-stu-id="0f64c-143">Visual C# project, solution, source, and related files used to create an assembly that you use to retrieve information from the CustInfo table added earlier to the Northwind sample SQL Server database.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="0f64c-144">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="0f64c-144">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-loans-processing-using-business-rules-sample"></a><span data-ttu-id="0f64c-145">生成并初始化使用业务规则的贷款处理示例</span><span class="sxs-lookup"><span data-stu-id="0f64c-145">To build and initialize the Loans Processing Using Business Rules sample</span></span>  
  
1.  <span data-ttu-id="0f64c-146">确保您的计算机上具有 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="0f64c-146">Make sure that you have the Northwind database on your machine.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="0f64c-147">为了运行本示例，您必须拥有名为 Northwind 的数据库。</span><span class="sxs-lookup"><span data-stu-id="0f64c-147">In order to run this sample, you must have a database named Northwind.</span></span> [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]<span data-ttu-id="0f64c-148"> 和 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] 不提供 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="0f64c-148"> and [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] do not ship with the Northwind sample database.</span></span> <span data-ttu-id="0f64c-149">若要创建 Northwind 数据库，下载安装文件从[http://go.microsoft.com/fwlink/?LinkId=196020](http://go.microsoft.com/fwlink/?LinkId=196020)，并按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="0f64c-149">To create the Northwind database, download the install file from [http://go.microsoft.com/fwlink/?LinkId=196020](http://go.microsoft.com/fwlink/?LinkId=196020), and follow the instructions.</span></span>  
  
2.  <span data-ttu-id="0f64c-150">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="0f64c-150">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="0f64c-151">\<*示例路径*> \Business Rules\Loans 处理使用业务规则</span><span class="sxs-lookup"><span data-stu-id="0f64c-151">\<*Samples Path*>\Business Rules\Loans Processing using Business Rules</span></span>  
  
3.  <span data-ttu-id="0f64c-152">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0f64c-152">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="0f64c-153">清理 GAC 以消除之前运行此示例所残留的任何数据。</span><span class="sxs-lookup"><span data-stu-id="0f64c-153">Cleans up the GAC to eliminate any residual data from previous runs of this sample.</span></span>  
  
    -   <span data-ttu-id="0f64c-154">编译并部署事实检索器程序 myFactRetreiever.dll。</span><span class="sxs-lookup"><span data-stu-id="0f64c-154">Compiles and deploys the fact retriever program, myFactRetreiever.dll.</span></span>  
  
    -   <span data-ttu-id="0f64c-155">使用 SQL 脚本文件 Create_CustInfo_Table.sql，将名为 CustInfo 的表添加到 Northwind 示例 SQL 数据库中。</span><span class="sxs-lookup"><span data-stu-id="0f64c-155">Using the SQL script file Create_CustInfo_Table.sql, adds a table named CustInfo to the Northwind sample SQL database.</span></span>  
  
    -   <span data-ttu-id="0f64c-156">清理共享 SQL 规则存储以消除之前运行此示例所残留的数据。</span><span class="sxs-lookup"><span data-stu-id="0f64c-156">Cleans up the shared SQL rule store to eliminate residue of previous runs of this sample.</span></span>  
  
    -   <span data-ttu-id="0f64c-157">创建、发布并部署贷款处理规则集的最新版本 (1.0)。</span><span class="sxs-lookup"><span data-stu-id="0f64c-157">Creates, publishes, and deploys the most recent version (1.0) of the loans processing rule set.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0f64c-158">可以使用 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 随附的业务规则编辑器工具检查以编程方式设置的规则。</span><span class="sxs-lookup"><span data-stu-id="0f64c-158">You can use the Business Rule Composer tool supplied with [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to examine the rules that have been set programmatically.</span></span>  
  
    -   <span data-ttu-id="0f64c-159">为本示例创建输入 (In) 和输出 (Out) 文件夹。</span><span class="sxs-lookup"><span data-stu-id="0f64c-159">Creates the input (In) and output (Out) folders for this sample.</span></span>  
  
    -   <span data-ttu-id="0f64c-160">编译并部署本示例的其余 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目，包括 BizTalk 项目，该项目包含用于协调本示例的业务流程。</span><span class="sxs-lookup"><span data-stu-id="0f64c-160">Compiles and deploys the remaining [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, including the BizTalk project that contains the orchestration you use to coordinate this sample.</span></span>  
  
    -   <span data-ttu-id="0f64c-161">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="0f64c-161">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] receive location, and the send and receive ports.</span></span>  
  
        > [!NOTE]
        >  <span data-ttu-id="0f64c-162">本示例在创建和绑定端口时将显示以下警告：</span><span class="sxs-lookup"><span data-stu-id="0f64c-162">This sample displays the following warnings when creating and binding ports:</span></span>  
        >   
        >  `Warning: Receive handler not specified for receive location "LoansProcessor_1.0.0.0_LoansProcessor.My_Sample_Service_Incoming_ReceiveLocation"; updating with first receive handler with matching transport type.`  
        >   
        >  `Warning: Host not specified for orchestration "LoansProcessor.My_Sample_Service"; updating with first available host.`  
        >   
        >  <span data-ttu-id="0f64c-163">可以安全地忽略这些警告。</span><span class="sxs-lookup"><span data-stu-id="0f64c-163">You can safely ignore these warnings.</span></span> <span data-ttu-id="0f64c-164">（考虑可能命名在用户安装中，主机名的差异和接收处理程序省略了从绑定文件。）</span><span class="sxs-lookup"><span data-stu-id="0f64c-164">(To accommodate for possible naming differences in user installations, the host name and receive handler have been omitted from the binding file.)</span></span>  
  
    -   <span data-ttu-id="0f64c-165">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="0f64c-165">Enables the receive location, and starts the send port.</span></span>  
  
    -   <span data-ttu-id="0f64c-166">登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="0f64c-166">Enlists and starts the orchestration.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f64c-167">如果 BizTalk 主机名不是 BizTalkServerApplication，请修改 Setup.bat 文件和 LoanProcessorBinding.xml 文件以反映正确的主机名。</span><span class="sxs-lookup"><span data-stu-id="0f64c-167">If your BizTalk host name is not BizTalkServerApplication, modify the file Setup.bat and the file LoanProcessorBinding.xml to reflect the proper host name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f64c-168">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="0f64c-168">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f64c-169">如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="0f64c-169">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="0f64c-170">使用该密钥对可以对生成的程序集签名。</span><span class="sxs-lookup"><span data-stu-id="0f64c-170">Use this key pair to sign the resulting assemblies.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0f64c-171">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="0f64c-171">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="0f64c-172">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="0f64c-172">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="0f64c-173">运行本示例</span><span class="sxs-lookup"><span data-stu-id="0f64c-173">Running This Sample</span></span>  
  
#### <a name="to-run-the-loans-processing-using-business-rules-sample"></a><span data-ttu-id="0f64c-174">运行使用业务规则的贷款处理示例</span><span class="sxs-lookup"><span data-stu-id="0f64c-174">To run the Loans Processing Using Business Rules sample</span></span>  
  
1.  <span data-ttu-id="0f64c-175">粘贴到文件 sampleLoan.xml 一份**\In**文件夹。</span><span class="sxs-lookup"><span data-stu-id="0f64c-175">Paste a copy of the file sampleLoan.xml into the **\In** folder.</span></span>  
  
2.  <span data-ttu-id="0f64c-176">观察的文件夹中创建的.xml 文件**出**。输入的 XML 消息包含添加到以下四个状态元素末尾的 XML 结构的数据： **IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，和**ResidencyStatus**。</span><span class="sxs-lookup"><span data-stu-id="0f64c-176">Observe the .xml file created in the folder **Out**. It contains the input XML message with data added to the following four status elements at the end of the XML structure: **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus**.</span></span>  
  
 <span data-ttu-id="0f64c-177">可以使用业务规则编辑器工具更改规则集中的规则，然后重新部署这些规则。</span><span class="sxs-lookup"><span data-stu-id="0f64c-177">You can use the Business Rule Composer tool to change the rules in the rule set, and then redeploy those rules.</span></span>  
  
#### <a name="to-use-the-business-rule-composer-tool-to-change-one-or-more-of-the-rules-in-a-rule-set"></a><span data-ttu-id="0f64c-178">使用业务规则编辑器工具更改规则集中一个或多个规则</span><span class="sxs-lookup"><span data-stu-id="0f64c-178">To use the Business Rule Composer tool to change one or more of the rules in a rule set</span></span>  
  
1.  <span data-ttu-id="0f64c-179">单击**启动**，指向**程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="0f64c-179">Click **Start**, point to **Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rule Composer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0f64c-180">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="0f64c-180">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="0f64c-181">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="0f64c-181">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="0f64c-182">在**SQL Server**对话框中，单击**确定**以连接到规则存储。</span><span class="sxs-lookup"><span data-stu-id="0f64c-182">In the **SQL Server** dialog box, click **OK** to connect to the rule store.</span></span>  
  
3.  <span data-ttu-id="0f64c-183">在**策略资源管理器**，节点下**LoanProcessing**，右键单击**版本 1.0 – 部署**节点，，然后单击**复制**。</span><span class="sxs-lookup"><span data-stu-id="0f64c-183">In **Policy Explorer**, below the node **LoanProcessing**, right-click the **Version 1.0 – Deployed** node, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="0f64c-184">右键单击**LoanProcessing**，然后单击**粘贴**。</span><span class="sxs-lookup"><span data-stu-id="0f64c-184">Right-click **LoanProcessing**, and then click **Paste**.</span></span>  
  
5.  <span data-ttu-id="0f64c-185">更改任何规则或操作将导致不同的值的方式**IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，和**ResidencyStatus**元素。</span><span class="sxs-lookup"><span data-stu-id="0f64c-185">Change any rule or action in a way that will result in different values for the **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus** elements.</span></span> <span data-ttu-id="0f64c-186">确保你还更改求反部分的值 (实质上， **Else**子句) 选择要更改任何规则。</span><span class="sxs-lookup"><span data-stu-id="0f64c-186">Ensure that you also change the value of the negation portion (essentially, the **Else** clause) of any rule that you choose to change.</span></span>  
  
     <span data-ttu-id="0f64c-187">下表显示了本示例使用的规则集。</span><span class="sxs-lookup"><span data-stu-id="0f64c-187">The following table shows the set of rules used by this sample.</span></span> <span data-ttu-id="0f64c-188">除非明确提及，否则事实来自传入的 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="0f64c-188">Unless specifically mentioned otherwise, facts are from the incoming XML message.</span></span> <span data-ttu-id="0f64c-189">字符串 (db) 表示数据库作为事实的源。</span><span class="sxs-lookup"><span data-stu-id="0f64c-189">The string (db) indicates a database as the source of a fact.</span></span>  
  
    |<span data-ttu-id="0f64c-190">规则编号</span><span class="sxs-lookup"><span data-stu-id="0f64c-190">Rule number</span></span>|<span data-ttu-id="0f64c-191">规则名称</span><span class="sxs-lookup"><span data-stu-id="0f64c-191">Rule name</span></span>|<span data-ttu-id="0f64c-192">Description</span><span class="sxs-lookup"><span data-stu-id="0f64c-192">Description</span></span>|  
    |-----------------|---------------|-----------------|  
    |<span data-ttu-id="0f64c-193">1</span><span class="sxs-lookup"><span data-stu-id="0f64c-193">1</span></span>|<span data-ttu-id="0f64c-194">Income Status Rule</span><span class="sxs-lookup"><span data-stu-id="0f64c-194">Income Status Rule</span></span>|<span data-ttu-id="0f64c-195">如果**BasicSalary** + **OtherIncome** > 0</span><span class="sxs-lookup"><span data-stu-id="0f64c-195">IF **BasicSalary** + **OtherIncome** > 0</span></span><br /><br /> <span data-ttu-id="0f64c-196">然后**IncomeStatus** = **有效**</span><span class="sxs-lookup"><span data-stu-id="0f64c-196">THEN **IncomeStatus** = **Valid**</span></span>|  
    |<span data-ttu-id="0f64c-197">2</span><span class="sxs-lookup"><span data-stu-id="0f64c-197">2</span></span>|<span data-ttu-id="0f64c-198">Commitments Status Rule</span><span class="sxs-lookup"><span data-stu-id="0f64c-198">Commitments Status Rule</span></span>|<span data-ttu-id="0f64c-199">如果**ID** == **ID (db)**</span><span class="sxs-lookup"><span data-stu-id="0f64c-199">IF **ID** == **ID (db)**</span></span><br /><br /> <span data-ttu-id="0f64c-200">和</span><span class="sxs-lookup"><span data-stu-id="0f64c-200">AND</span></span><br /><br /> <span data-ttu-id="0f64c-201">如果**CreditCardBalance (db)** > 500</span><span class="sxs-lookup"><span data-stu-id="0f64c-201">IF **CreditCardBalance (db)** > 500</span></span><br /><br /> <span data-ttu-id="0f64c-202">然后**CommitmentsStatus** =</span><span class="sxs-lookup"><span data-stu-id="0f64c-202">THEN **CommitmentsStatus** =</span></span><br /><br /> <span data-ttu-id="0f64c-203">"Compute Commitments"</span><span class="sxs-lookup"><span data-stu-id="0f64c-203">"Compute Commitments"</span></span>|  
    |<span data-ttu-id="0f64c-204">3</span><span class="sxs-lookup"><span data-stu-id="0f64c-204">3</span></span>|<span data-ttu-id="0f64c-205">Employment Status Rule</span><span class="sxs-lookup"><span data-stu-id="0f64c-205">Employment Status Rule</span></span>|<span data-ttu-id="0f64c-206">如果**EmploymentType &#124;TimeInMonths** > 18</span><span class="sxs-lookup"><span data-stu-id="0f64c-206">IF **EmploymentType &#124; TimeInMonths** > 18</span></span><br /><br /> <span data-ttu-id="0f64c-207">然后**EmploymentStatus** = **有效**</span><span class="sxs-lookup"><span data-stu-id="0f64c-207">THEN **EmploymentStatus** = **Valid**</span></span>|  
    |<span data-ttu-id="0f64c-208">4</span><span class="sxs-lookup"><span data-stu-id="0f64c-208">4</span></span>|<span data-ttu-id="0f64c-209">Residency Status Rule</span><span class="sxs-lookup"><span data-stu-id="0f64c-209">Residency Status Rule</span></span>|<span data-ttu-id="0f64c-210">如果**PlaceOfResidence &#124;TimeInMonths** > 18</span><span class="sxs-lookup"><span data-stu-id="0f64c-210">IF **PlaceOfResidence &#124; TimeInMonths** > 18</span></span><br /><br /> <span data-ttu-id="0f64c-211">然后**ResidencyStatus** = **有效**</span><span class="sxs-lookup"><span data-stu-id="0f64c-211">THEN **ResidencyStatus** = **Valid**</span></span>|  
    |<span data-ttu-id="0f64c-212">!1, !2, !3, !4</span><span class="sxs-lookup"><span data-stu-id="0f64c-212">!1, !2, !3, !4</span></span>|<span data-ttu-id="0f64c-213">Negation Rules</span><span class="sxs-lookup"><span data-stu-id="0f64c-213">Negation Rules</span></span>|<span data-ttu-id="0f64c-214">条件逻辑**不**规则 1-4 中所述的相应条件。</span><span class="sxs-lookup"><span data-stu-id="0f64c-214">Conditions that are a logical **NOT** of the corresponding condition described in rules 1–4.</span></span> <span data-ttu-id="0f64c-215">生成操作是设置的字符串中的更改。</span><span class="sxs-lookup"><span data-stu-id="0f64c-215">Resulting actions are a change in the string that is being set.</span></span>|  
  
6.  <span data-ttu-id="0f64c-216">右键单击**（不保存） 1.1 版**节点，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="0f64c-216">Right-click the **Version 1.1(not saved)** node, and then click **Save**.</span></span>  
  
7.  <span data-ttu-id="0f64c-217">右键单击**版本 1.1**节点，，然后单击**发布**。</span><span class="sxs-lookup"><span data-stu-id="0f64c-217">Right-click the **Version 1.1** node, and then click **Publish**.</span></span>  
  
8.  <span data-ttu-id="0f64c-218">右键单击**版本 1.1**节点，，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="0f64c-218">Right-click the **Version 1.1** node, and then click **Deploy**.</span></span>  
  
9. <span data-ttu-id="0f64c-219">等待 60 秒以使更改传播到共享 SQL Server 规则存储。</span><span class="sxs-lookup"><span data-stu-id="0f64c-219">Wait for 60 seconds for the changes to propagate to the shared SQL Server rule store.</span></span>  
  
10. <span data-ttu-id="0f64c-220">将文件 sampleLoan.xml 的副本粘贴到文件夹**中**。</span><span class="sxs-lookup"><span data-stu-id="0f64c-220">Paste a copy of the file sampleLoan.xml into the folder **In**.</span></span>  
  
11. <span data-ttu-id="0f64c-221">观察的文件夹中创建的.xml 文件**出**。输入的 XML 消息包含添加到以下四个状态元素末尾的 XML 结构的数据： **IncomeStatus**， **CommitmentsStatus**， **EmploymentStatus**，和**ResidencyStatus**。</span><span class="sxs-lookup"><span data-stu-id="0f64c-221">Observe the .xml file created in the folder **Out**. It contains the input XML message with data added to the following four status elements at the end of the XML structure: **IncomeStatus**, **CommitmentsStatus**, **EmploymentStatus**, and **ResidencyStatus**.</span></span> <span data-ttu-id="0f64c-222">根据此过程步骤 5 中所做更改的性质，添加到这些元素的数据与以前的运行可能不同。</span><span class="sxs-lookup"><span data-stu-id="0f64c-222">The data added to these elements will differ, or not, from the previous run, based on the nature of the changes made in step 5in this procedure.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="0f64c-223">注释</span><span class="sxs-lookup"><span data-stu-id="0f64c-223">Comments</span></span>  
 <span data-ttu-id="0f64c-224">如果希望查看本示例的跟踪信息，您必须取消部署相关规则集（贷款处理），然后使用业务规则引擎部署向导重新部署。</span><span class="sxs-lookup"><span data-stu-id="0f64c-224">If you want to view the tracking information for this sample, you must undeploy and then redeploy the relevant rule set (Loans Processing) by using the Business Rules Engine Deployment Wizard.</span></span>  
  
 <span data-ttu-id="0f64c-225">本示例说明如何使用业务规则以业务流程内规则的形式应用业务策略。</span><span class="sxs-lookup"><span data-stu-id="0f64c-225">This sample demonstrates how you can use business rules to apply business policies in the form of rules within an orchestration.</span></span> <span data-ttu-id="0f64c-226">它还说明如何更改策略，以及如何使策略中的更改动态反映在业务流程内，而不必重新编译或重新部署业务流程解决方案。</span><span class="sxs-lookup"><span data-stu-id="0f64c-226">It also demonstrates how you can change the policies, and have the change in the policy reflected dynamically within the orchestration without having to recompile or redeploy the orchestration solution.</span></span>  
  
 <span data-ttu-id="0f64c-227">本示例的输入贷款案例为具有以下结构的 XML 消息：</span><span class="sxs-lookup"><span data-stu-id="0f64c-227">Input loan cases to this sample are XML messages that have the following structure:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0f64c-228">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f64c-228">See Also</span></span>  
 [<span data-ttu-id="0f64c-229">业务规则 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="0f64c-229">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)