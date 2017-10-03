---
title: "医疗声明处理和测试策略 （BizTalk Server 示例） |Microsoft 文档"
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
ms.assetid: c0bdf7b7-3e55-4560-a5a8-00c5b661d14d
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 33c8921e037b9f9628c0e0ee97a915f62ab634ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="medical-claims-processing-and-testing-policies-biztalk-server-sample"></a><span data-ttu-id="52316-102">医疗声明处理和测试策略 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="52316-102">Medical Claims Processing and Testing Policies (BizTalk Server Sample)</span></span>
<span data-ttu-id="52316-103">“医疗索赔处理和测试保单”示例演示如何创建包含多个规则的规则集，这些规则检查从数据库表和入站文档推断得出的事实，并使用基于 .NET 的对象记录索赔处理结果。</span><span class="sxs-lookup"><span data-stu-id="52316-103">The Medical Claims Processing and Testing Policies sample demonstrates how to create a rule set containing multiple rules that examine facts derived from a database table and the inbound document, and which use .NET-based objects to record the results of the claims processing.</span></span>  
  
 <span data-ttu-id="52316-104">此示例演示如何使用一个简单的声明处理方案端执行。基于网络的应用程序使用业务规则引擎运行医疗声明规则集对传入声明，以确定声明的状态和状态的原因。</span><span class="sxs-lookup"><span data-stu-id="52316-104">This sample demonstrates end-end execution of the claim processing scenario using a simple .NET-based application that uses the Business Rule Engine to run a medical claims rule set against incoming claims to determine the STATUS of the claim and the REASON for the status.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="52316-105">此示例还演示如何使用调试跟踪文件的业务规则引擎执行跟踪。</span><span class="sxs-lookup"><span data-stu-id="52316-105">This sample also demonstrates how to trace Business Rule Engine execution using a debug trace file.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="52316-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="52316-106">What This Sample Does</span></span>  
 <span data-ttu-id="52316-107">此示例适用于已提交的声明规则的以下序列：</span><span class="sxs-lookup"><span data-stu-id="52316-107">This sample applies the following sequence of rules to submitted claims:</span></span>  
  
1.  <span data-ttu-id="52316-108">如果声明的总金额超过策略允许的最大，拒绝声明。</span><span class="sxs-lookup"><span data-stu-id="52316-108">Rejects the claim if the total amount claimed exceeds the maximum permitted by the policy.</span></span>  
  
2.  <span data-ttu-id="52316-109">如果客户端段中已在医院比策略允许的最大的多个晚上将拒绝声明。</span><span class="sxs-lookup"><span data-stu-id="52316-109">Rejects the claim if the client has stayed in hospitals more nights than the maximum permitted by the policy.</span></span>  
  
3.  <span data-ttu-id="52316-110">如果声明的日期是在将来将拒绝声明。</span><span class="sxs-lookup"><span data-stu-id="52316-110">Rejects the claim if the date on the claim is in the future.</span></span>  
  
4.  <span data-ttu-id="52316-111">拒绝声明，如果该策略无效。</span><span class="sxs-lookup"><span data-stu-id="52316-111">Rejects the claim if the policy is not valid.</span></span>  
  
5.  <span data-ttu-id="52316-112">如果策略已过期，请将一个主管发送到策略 ID 和客户名称的销售部门。</span><span class="sxs-lookup"><span data-stu-id="52316-112">Sends a lead to the sales department with the policy ID and customer name if the policy has expired.</span></span>  
  
6.  <span data-ttu-id="52316-113">否则，批准声明。</span><span class="sxs-lookup"><span data-stu-id="52316-113">Otherwise, approves the claim.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="52316-114">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="52316-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="52316-115">\<*示例路径*> \Business Rules\Medical 声明处理和测试 Policies\\</span><span class="sxs-lookup"><span data-stu-id="52316-115">\<*Samples Path*>\Business Rules\Medical Claims Processing and Testing Policies\\</span></span>  
  
 <span data-ttu-id="52316-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="52316-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="52316-117">文件</span><span class="sxs-lookup"><span data-stu-id="52316-117">File(s)</span></span>|<span data-ttu-id="52316-118">Description</span><span class="sxs-lookup"><span data-stu-id="52316-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="52316-119">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="52316-119">Cleanup.bat</span></span>|<span data-ttu-id="52316-120">用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="52316-120">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="52316-121">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="52316-121">Removes send and receive ports.</span></span> <span data-ttu-id="52316-122">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="52316-122">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="52316-123">Create_PolicyValidity_Table.sql</span><span class="sxs-lookup"><span data-stu-id="52316-123">Create_PolicyValidity_Table.sql</span></span>|<span data-ttu-id="52316-124">添加一个新表的 SQL 脚本名 PolicyValidity 为包含到 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="52316-124">SQL script that adds a new table named PolicyValidity to the Northwind sample database.</span></span>|  
|<span data-ttu-id="52316-125">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="52316-125">Setup.bat</span></span>|<span data-ttu-id="52316-126">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="52316-126">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="52316-127">在 \Claims 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="52316-127">In the \Claims folder:</span></span><br /><br /> <span data-ttu-id="52316-128">AssemblyInfo.cs、 Claims.csproj，Claims.sln Claims.cs</span><span class="sxs-lookup"><span data-stu-id="52316-128">AssemblyInfo.cs, Claims.csproj, Claims.sln, Claims.cs</span></span>|<span data-ttu-id="52316-129">项目、 解决方案、 源和相关的文件记录结果的处理，声明此示例的部分调用**然后**规则部分。</span><span class="sxs-lookup"><span data-stu-id="52316-129">Project, solution, source, and related files for the portion of this sample that records the result of the claims processing, called the **THEN** portion of a rule.</span></span>|  
|<span data-ttu-id="52316-130">在 \FactRetrieverForClaimsProcessing 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="52316-130">In the \FactRetrieverForClaimsProcessing folder:</span></span><br /><br /> <span data-ttu-id="52316-131">AssemblyInfo.cs、 FactRetrieverForClaimsProcessing.cs，FactRetrieverForClaimsProcessing.csproj FactRetrieverForClaimsProcessing.sln</span><span class="sxs-lookup"><span data-stu-id="52316-131">AssemblyInfo.cs, FactRetrieverForClaimsProcessing.cs, FactRetrieverForClaimsProcessing.csproj, FactRetrieverForClaimsProcessing.sln</span></span>|<span data-ttu-id="52316-132">项目、 解决方案、 源和相关的文件提供了从创建此示例的 PolicyValidity 表中检索信息的长期事实检索此示例的部分。</span><span class="sxs-lookup"><span data-stu-id="52316-132">Project, solution, source, and related files for the portion of this sample that provides the long-term fact retriever that retrieves information from the PolicyValidity table created by this sample.</span></span>|  
|<span data-ttu-id="52316-133">\RulesForMedicalClaims 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="52316-133">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="52316-134">App.ico、 AssemblyInfo.cs、 RulesForMedicalClaims.cs、 RulesForMedicalClaims.csproj、 RulesForMedicalClaims.sln</span><span class="sxs-lookup"><span data-stu-id="52316-134">App.ico, AssemblyInfo.cs, RulesForMedicalClaims.cs, RulesForMedicalClaims.csproj, RulesForMedicalClaims.sln</span></span>|<span data-ttu-id="52316-135">项目、 解决方案、 源和相关的文件，此示例以编程方式可以是此示例 (RulesForMedicalClaims.exe)，和的主可执行文件的部分定义也将规则集，构造示例事实，然后运行规则集使用**PolicyTester**对象。</span><span class="sxs-lookup"><span data-stu-id="52316-135">Project, solution, source, and related files for the portion of this sample that constitutes the main executable for this sample (RulesForMedicalClaims.exe), and which programmatically defines and stores the rule set, constructs sample facts, and then runs the rule set using a **PolicyTester** object.</span></span>|  
|<span data-ttu-id="52316-136">\RulesForMedicalClaims 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="52316-136">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="52316-137">MedicalClaims.xsd</span><span class="sxs-lookup"><span data-stu-id="52316-137">MedicalClaims.xsd</span></span>|<span data-ttu-id="52316-138">于此示例中定义的提交示例医疗声明的结构的架构文件。</span><span class="sxs-lookup"><span data-stu-id="52316-138">Schema file that defines the structure of the sample medical claims submitted to this sample.</span></span>|  
|<span data-ttu-id="52316-139">\RulesForMedicalClaims 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="52316-139">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="52316-140">sampleClaim.xml</span><span class="sxs-lookup"><span data-stu-id="52316-140">sampleClaim.xml</span></span>|<span data-ttu-id="52316-141">示例符合架构文件 MedicalClaims.xsd 中定义的输入的文件。</span><span class="sxs-lookup"><span data-stu-id="52316-141">Sample input file that conforms to the schema defined in the file MedicalClaims.xsd.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="52316-142">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="52316-142">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-medical-claims-processing-and-testing-policies-sample"></a><span data-ttu-id="52316-143">生成并初始化“医疗索赔处理和测试保单”示例</span><span class="sxs-lookup"><span data-stu-id="52316-143">To build and initialize the Medical Claims Processing and Testing Policies sample</span></span>  
  
1.  <span data-ttu-id="52316-144">确保您的计算机上具有 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="52316-144">Make sure that you have the Northwind database on your machine.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="52316-145">为了运行本示例，您必须拥有名为 Northwind 的数据库。</span><span class="sxs-lookup"><span data-stu-id="52316-145">In order to run this sample, you must have a database named Northwind.</span></span> [!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]<span data-ttu-id="52316-146"> 和 [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] 不提供 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="52316-146"> and [!INCLUDE[btsSQLServer2008R2](../includes/btssqlserver2008r2-md.md)] do not ship with the Northwind sample database.</span></span> <span data-ttu-id="52316-147">若要创建 Northwind 数据库，下载安装文件从[http://go.microsoft.com/fwlink/?LinkId=196020](http://go.microsoft.com/fwlink/?LinkId=196020)，并按照说明操作。</span><span class="sxs-lookup"><span data-stu-id="52316-147">To create the Northwind database, download the install file from [http://go.microsoft.com/fwlink/?LinkId=196020](http://go.microsoft.com/fwlink/?LinkId=196020), and follow the instructions.</span></span>  
  
2.  <span data-ttu-id="52316-148">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="52316-148">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="52316-149">\<*示例路径*> \Business Rules\Medical 声明处理和测试 Policies\\</span><span class="sxs-lookup"><span data-stu-id="52316-149">\<*Samples Path*>\Business Rules\Medical Claims Processing and Testing Policies\\</span></span>  
  
3.  <span data-ttu-id="52316-150">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="52316-150">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="52316-151">为本示例编译并部署 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目，包括 Claims.dll、FactRetrieverForClaimsProcessing.dll 和 RulesForMedicalClaims.dll。</span><span class="sxs-lookup"><span data-stu-id="52316-151">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, including Claims.dll, FactRetrieverForClaimsProcessing.dll, and RulesForMedicalClaims.dll.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52316-152">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="52316-152">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52316-153">如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="52316-153">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="52316-154">使用该密钥对可以对生成的程序集签名。</span><span class="sxs-lookup"><span data-stu-id="52316-154">Use this key pair to sign the resulting assemblies.</span></span>  
  
    -   <span data-ttu-id="52316-155">运行提供的 SQL 脚本 Create_PolicyValidity_Table.sql 使用 SQL 查询分析器中。</span><span class="sxs-lookup"><span data-stu-id="52316-155">Runs the provided SQL script Create_PolicyValidity_Table.sql using SQL Query Analyzer.</span></span> <span data-ttu-id="52316-156">由脚本创建的表，PolicyValidity，Northwind 示例数据库中的两个示例行。</span><span class="sxs-lookup"><span data-stu-id="52316-156">The script creates the table, PolicyValidity, with two sample rows in the Northwind sample database.</span></span> <span data-ttu-id="52316-157">此表包含两列： ID 和 PolicyStatus。</span><span class="sxs-lookup"><span data-stu-id="52316-157">This table has two columns: ID and PolicyStatus.</span></span>  
  
    -   <span data-ttu-id="52316-158">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="52316-158">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports.</span></span>  
  
    -   <span data-ttu-id="52316-159">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="52316-159">Enables the receive location, and starts the send port.</span></span>  
  
    -   <span data-ttu-id="52316-160">登记，并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="52316-160">Enlists and starts orchestration.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52316-161">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="52316-161">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="52316-162">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="52316-162">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="52316-163">运行本示例</span><span class="sxs-lookup"><span data-stu-id="52316-163">Running This Sample</span></span>  
  
#### <a name="to-run-the-medical-claims-processing-and-testing-policies-sample"></a><span data-ttu-id="52316-164">运行“医疗索赔处理和测试保单”示例</span><span class="sxs-lookup"><span data-stu-id="52316-164">To run the Medical Claims Processing and Testing Policies sample</span></span>  
  
1.  <span data-ttu-id="52316-165">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="52316-165">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="52316-166">\<*示例路径*> \Business Rules\Medical 声明处理和测试 Policies\RulesForMedicalClaims\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="52316-166">\<*Samples Path*>\Business Rules\Medical Claims Processing and Testing Policies\RulesForMedicalClaims\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="52316-167">在命令行上运行文件 RulesForMedicalClaims.exe。</span><span class="sxs-lookup"><span data-stu-id="52316-167">Run the file RulesForMedicalClaims.exe on the command line.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="52316-168">你可以更改的示例声明文件 sampleClaim.xml 中各个元素的值和重复运行示例。</span><span class="sxs-lookup"><span data-stu-id="52316-168">You can change the values of individual elements in the sample claim file sampleClaim.xml and run the sample repeatedly.</span></span> <span data-ttu-id="52316-169">这些元素中的不同值的预期的输出所示后面的列表。</span><span class="sxs-lookup"><span data-stu-id="52316-169">The expected outputs for different values in these elements are shown in the list that follows.</span></span>  
  
 <span data-ttu-id="52316-170">基于已提交的示例声明文件中的值的各种组合的输出方案是：</span><span class="sxs-lookup"><span data-stu-id="52316-170">Output scenarios based on various combinations of values in the submitted sample claims file are:</span></span>  
  
-   <span data-ttu-id="52316-171">声明其量超过 1000 美元，可获得以下输出：</span><span class="sxs-lookup"><span data-stu-id="52316-171">For a claim whose amount exceeds $1000, the following output is obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of claim has exceeded Policy limit  
    ```  
  
-   <span data-ttu-id="52316-172">夜晚其数目超过 10 声明，可获得以下输出：</span><span class="sxs-lookup"><span data-stu-id="52316-172">For a claim whose number of nights exceeds 10, the following output is obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of Nights has exceeded Policy limit  
    ```  
  
-   <span data-ttu-id="52316-173">声明其日期无效 (日期 > 当前日期)，则以下输出中获得：</span><span class="sxs-lookup"><span data-stu-id="52316-173">For a claim whose date is not valid (date > current date), the following output in obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Cannot submit claims for future dates!  
    ```  
  
-   <span data-ttu-id="52316-174">不是有效的策略 ID 与声明 (例如，通过更改**ID**元素具有值为 2) 由于策略过期获得以下输出：</span><span class="sxs-lookup"><span data-stu-id="52316-174">For a claim with a policy ID that is not valid (for example, by changing the **ID** element to have a value of 2) because of policy expiration, the following output is obtained:</span></span>  
  
    ```  
    Sending to Renewal Department for Customer Smir with Policy # 2  
    Status:  REJECTED!  
    Reason:  Policy ID is invalid  
    ```  
  
-   <span data-ttu-id="52316-175">声明的有效，可获得以下输出：</span><span class="sxs-lookup"><span data-stu-id="52316-175">For a claim that is valid, the following output is obtained:</span></span>  
  
    ```  
    Status:  Claim Accepted!  
    Reason:  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="52316-176">文本文件、 outputtrace.txt，每次运行此示例文件夹...\RulesForMedicalClaims\bin\Debug 文件夹中创建。</span><span class="sxs-lookup"><span data-stu-id="52316-176">A text file, outputtrace.txt, is created in the folder ...\RulesForMedicalClaims\bin\Debug folder every time you run this sample.</span></span> <span data-ttu-id="52316-177">它包含的规则执行调试跟踪，并创建它时每次执行周期下文件夹 \RulesForMedicalClaims\bin\Debug 后。</span><span class="sxs-lookup"><span data-stu-id="52316-177">It contains a debug trace of rule execution, and it is created after every execution cycle under the folder \RulesForMedicalClaims\bin\Debug.</span></span> <span data-ttu-id="52316-178">你可以检查该文件，请参阅规则执行的输出跟踪。</span><span class="sxs-lookup"><span data-stu-id="52316-178">You can examine this file to see the output trace of rule execution.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="52316-179">注释</span><span class="sxs-lookup"><span data-stu-id="52316-179">Comments</span></span>  
 <span data-ttu-id="52316-180">在规则集计算中使用的事实来源是：</span><span class="sxs-lookup"><span data-stu-id="52316-180">The fact sources used in the rule set evaluation are:</span></span>  
  
-   <span data-ttu-id="52316-181">长期的事实检索器。基于网络的应用程序实现**IFactReriever**接口，文件夹 FactRetrieverForClaimsProcessing 中生成。</span><span class="sxs-lookup"><span data-stu-id="52316-181">A long-term fact retriever, a .NET-based application that implements the **IFactReriever** interface, is built in the folder FactRetrieverForClaimsProcessing.</span></span> <span data-ttu-id="52316-182">它通过处理策略的医疗声明用于从 PolicyValidity 数据库中检索数据 （在数据集的形式） 并要在规则条件计算中使用。</span><span class="sxs-lookup"><span data-stu-id="52316-182">It is used by the medical claims processing policy to retrieve data (in the form of a dataset) from the PolicyValidity database and to use in rule condition evaluation.</span></span>  
  
-   <span data-ttu-id="52316-183">声明是包含以下信息，存储在同级元素的 XML 文档的形式： 名称、 ID、 金额、 晚上和日期。</span><span class="sxs-lookup"><span data-stu-id="52316-183">The claim is in the form of an XML document that contains the following information, stored in sibling elements: Name, ID, Amount, Nights, and Date.</span></span>  
  
-   <span data-ttu-id="52316-184">答:。基于网络的类库 （声明） 与**ClaimResults**类用于记录的状态和使用属性，声明的原因以及 （如果该策略不是有效的） 发送一个主管通过调用**SendLeads**具有 ID 和名称作为参数的方法。</span><span class="sxs-lookup"><span data-stu-id="52316-184">A .NET-based class library (Claims), with a **ClaimResults** class is used to record the STATUS and REASON of the claim using properties, and to send a lead (if the policy is not valid) by invoking the **SendLeads** method with ID and name as parameters.</span></span>  
  
 <span data-ttu-id="52316-185">基于这些事实源，你可以被不正式地描述为这种情况下，如下所示定义的规则：</span><span class="sxs-lookup"><span data-stu-id="52316-185">Based on these fact sources, you can informally describe the rules defined for this scenario as follows:</span></span>  
  
1.  <span data-ttu-id="52316-186">检查传入声明有效。</span><span class="sxs-lookup"><span data-stu-id="52316-186">Check to see if the incoming claim is valid.</span></span> <span data-ttu-id="52316-187">如果量超过了允许的限制声明，如果策略已过期 （通过检查数据库表已验证），如果晚上数目超过了允许的最大限制，并且将来的日期进行声明，声明无效。</span><span class="sxs-lookup"><span data-stu-id="52316-187">The claim is not valid if the amount is over the allowable limit for a claim, if the policy has expired (verified by checking the database table), if the number of nights has exceeded the maximum allowable limit, and if the claim is made for a future date.</span></span> <span data-ttu-id="52316-188">如果已确定声明不是有效，正确设置的状态和声明的原因。</span><span class="sxs-lookup"><span data-stu-id="52316-188">If the claim has been determined to be not valid, set the STATUS and REASON of the claim appropriately.</span></span>  
  
2.  <span data-ttu-id="52316-189">如果传入声明的策略 ID 已过期，请向策略续订部门发送一个主管 （具有策略 ID 和客户名称）。</span><span class="sxs-lookup"><span data-stu-id="52316-189">If the policy ID of the incoming claim has expired, send a lead (with policy ID and customer name) to the policy renewal department.</span></span>  
  
3.  <span data-ttu-id="52316-190">如果声明是有效的正确设置的状态和声明的原因。</span><span class="sxs-lookup"><span data-stu-id="52316-190">If the claim is valid, set the STATUS and REASON of the claim appropriately.</span></span>  
  
 <span data-ttu-id="52316-191">更正式的表示形式和术语绑定规则如下所示：</span><span class="sxs-lookup"><span data-stu-id="52316-191">A more formal representation of the rules and their term bindings is as follows:</span></span>  
  
-   <span data-ttu-id="52316-192">**规则 1。量检查**</span><span class="sxs-lookup"><span data-stu-id="52316-192">**Rule 1. Amount check**</span></span>  
  
    ```  
    IF Amount in the XML document is > 1000  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"\  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="52316-193">**规则 2。晚上花在医院**</span><span class="sxs-lookup"><span data-stu-id="52316-193">**Rule 2. Nights spent in the hospital**</span></span>  
  
    ```  
    IF number of nights in the XML document is > 10  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Amount of claim has exceeded limit"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="52316-194">**规则 3。日期有效性**</span><span class="sxs-lookup"><span data-stu-id="52316-194">**Rule 3. Date validity**</span></span>  
  
    ```  
    IF date on the incoming XML claim is > Today  
      AND   
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Cannot submit claims in the future!"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="52316-195">**规则 4。策略有效性**</span><span class="sxs-lookup"><span data-stu-id="52316-195">**Rule 4. Policy validity**</span></span>  
  
    ```  
    IF Policy is invalid for the ID in the XML claim (check database)  
      AND  
    IF Claims.ClaimResults object has not been modified (if ClaimResults.RESULT = null)  
  
    THEN Claims.ClaimResults.Status = "REJECTED"  
         &&  
         Claims.ClaimResults.Reason = "Policy Invalid"  
         &&  
         Assert this object back into working memory  
  
    ```  
  
-   <span data-ttu-id="52316-196">**规则 5。潜在销售顾客**</span><span class="sxs-lookup"><span data-stu-id="52316-196">**Rule 5. Sales lead**</span></span>  
  
    ```  
    IF Claim.ClaimResults.Reason = "Policy invalid"  
  
    THEN send a lead to the policy department by invoking the function Claim.ClaimResults.SendLead with customer ID and Name from the incoming XML document.  
  
    ```  
  
-   <span data-ttu-id="52316-197">**规则 6。接受的声明**</span><span class="sxs-lookup"><span data-stu-id="52316-197">**Rule 6. Claim accepted**</span></span>  
  
    ```  
    IF Claim.ClaimResults.Status = null  
  
    THEN Set the claim status to be valid  
         &&  
         Send the lead to the sales department  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="52316-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52316-198">See Also</span></span>  
 [<span data-ttu-id="52316-199">业务规则 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="52316-199">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)