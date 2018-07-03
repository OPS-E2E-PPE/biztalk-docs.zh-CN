---
title: 医疗索赔处理和测试保单 （BizTalk Server 示例） |Microsoft Docs
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
ms.assetid: c0bdf7b7-3e55-4560-a5a8-00c5b661d14d
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e67b9a631764ed83659b05aa11f4c1570484f74
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994862"
---
# <a name="medical-claims-processing-and-testing-policies-biztalk-server-sample"></a><span data-ttu-id="81450-102">医疗索赔处理和测试保单 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="81450-102">Medical Claims Processing and Testing Policies (BizTalk Server Sample)</span></span>
<span data-ttu-id="81450-103">“医疗索赔处理和测试保单”示例演示如何创建包含多个规则的规则集，这些规则检查从数据库表和入站文档推断得出的事实，并使用基于 .NET 的对象记录索赔处理结果。</span><span class="sxs-lookup"><span data-stu-id="81450-103">The Medical Claims Processing and Testing Policies sample demonstrates how to create a rule set containing multiple rules that examine facts derived from a database table and the inbound document, and which use .NET-based objects to record the results of the claims processing.</span></span>  
  
 <span data-ttu-id="81450-104">此示例演示使用一个简单的声明处理方案的完整执行。基于 NET 的应用程序使用业务规则引擎来运行医疗声明规则集对传入声明来确定报销申请的状态和状态的原因。</span><span class="sxs-lookup"><span data-stu-id="81450-104">This sample demonstrates end-end execution of the claim processing scenario using a simple .NET-based application that uses the Business Rule Engine to run a medical claims rule set against incoming claims to determine the STATUS of the claim and the REASON for the status.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="81450-105">此示例还演示如何跟踪业务规则引擎执行使用调试跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="81450-105">This sample also demonstrates how to trace Business Rule Engine execution using a debug trace file.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="81450-106">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="81450-106">What This Sample Does</span></span>  
 <span data-ttu-id="81450-107">此示例适用于已提交的声明规则按以下顺序：</span><span class="sxs-lookup"><span data-stu-id="81450-107">This sample applies the following sequence of rules to submitted claims:</span></span>  
  
1.  <span data-ttu-id="81450-108">如果声明的总金额超过策略允许的最大，拒绝声明。</span><span class="sxs-lookup"><span data-stu-id="81450-108">Rejects the claim if the total amount claimed exceeds the maximum permitted by the policy.</span></span>  
  
2.  <span data-ttu-id="81450-109">如果客户端具有仍保留在医院比策略允许的最大的多个夜晚将拒绝该声明。</span><span class="sxs-lookup"><span data-stu-id="81450-109">Rejects the claim if the client has stayed in hospitals more nights than the maximum permitted by the policy.</span></span>  
  
3.  <span data-ttu-id="81450-110">如果在声明上的日期在将来，会拒绝声明。</span><span class="sxs-lookup"><span data-stu-id="81450-110">Rejects the claim if the date on the claim is in the future.</span></span>  
  
4.  <span data-ttu-id="81450-111">如果策略不是有效，则会拒绝该声明。</span><span class="sxs-lookup"><span data-stu-id="81450-111">Rejects the claim if the policy is not valid.</span></span>  
  
5.  <span data-ttu-id="81450-112">如果策略已过期，请将潜在顾客发送到销售部门的策略 ID 和客户名称。</span><span class="sxs-lookup"><span data-stu-id="81450-112">Sends a lead to the sales department with the policy ID and customer name if the policy has expired.</span></span>  
  
6.  <span data-ttu-id="81450-113">否则，将批准该声明。</span><span class="sxs-lookup"><span data-stu-id="81450-113">Otherwise, approves the claim.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="81450-114">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="81450-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="81450-115">\<*示例路径*\>\Business Rules\Medical 声明 Processing and Testing Policies\\</span><span class="sxs-lookup"><span data-stu-id="81450-115">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\\</span></span>  
  
 <span data-ttu-id="81450-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="81450-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="81450-117">文件</span><span class="sxs-lookup"><span data-stu-id="81450-117">File(s)</span></span>|<span data-ttu-id="81450-118">Description</span><span class="sxs-lookup"><span data-stu-id="81450-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="81450-119">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="81450-119">Cleanup.bat</span></span>|<span data-ttu-id="81450-120">用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="81450-120">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="81450-121">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="81450-121">Removes send and receive ports.</span></span> <span data-ttu-id="81450-122">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="81450-122">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="81450-123">Create_PolicyValidity_Table.sql</span><span class="sxs-lookup"><span data-stu-id="81450-123">Create_PolicyValidity_Table.sql</span></span>|<span data-ttu-id="81450-124">添加一个新表的 SQL 脚本名 PolicyValidity 为到 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="81450-124">SQL script that adds a new table named PolicyValidity to the Northwind sample database.</span></span>|  
|<span data-ttu-id="81450-125">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="81450-125">Setup.bat</span></span>|<span data-ttu-id="81450-126">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="81450-126">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="81450-127">在 \Claims 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="81450-127">In the \Claims folder:</span></span><br /><br /> <span data-ttu-id="81450-128">AssemblyInfo.cs、 Claims.csproj，Claims.sln Claims.cs</span><span class="sxs-lookup"><span data-stu-id="81450-128">AssemblyInfo.cs, Claims.csproj, Claims.sln, Claims.cs</span></span>|<span data-ttu-id="81450-129">项目、 解决方案、 源和相关的文件，此示例中，记录索赔处理结果的部分称为**然后**规则的部分。</span><span class="sxs-lookup"><span data-stu-id="81450-129">Project, solution, source, and related files for the portion of this sample that records the result of the claims processing, called the **THEN** portion of a rule.</span></span>|  
|<span data-ttu-id="81450-130">在 \FactRetrieverForClaimsProcessing 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="81450-130">In the \FactRetrieverForClaimsProcessing folder:</span></span><br /><br /> <span data-ttu-id="81450-131">AssemblyInfo.cs、 FactRetrieverForClaimsProcessing.cs，FactRetrieverForClaimsProcessing.csproj FactRetrieverForClaimsProcessing.sln</span><span class="sxs-lookup"><span data-stu-id="81450-131">AssemblyInfo.cs, FactRetrieverForClaimsProcessing.cs, FactRetrieverForClaimsProcessing.csproj, FactRetrieverForClaimsProcessing.sln</span></span>|<span data-ttu-id="81450-132">项目、 解决方案、 源和相关的文件，此示例中，提供从创建此示例的 PolicyValidity 表中检索信息的长期事实检索器的部分。</span><span class="sxs-lookup"><span data-stu-id="81450-132">Project, solution, source, and related files for the portion of this sample that provides the long-term fact retriever that retrieves information from the PolicyValidity table created by this sample.</span></span>|  
|<span data-ttu-id="81450-133">\RulesForMedicalClaims 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="81450-133">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="81450-134">App.ico、 AssemblyInfo.cs、 RulesForMedicalClaims.cs、 RulesForMedicalClaims.csproj、 RulesForMedicalClaims.sln</span><span class="sxs-lookup"><span data-stu-id="81450-134">App.ico, AssemblyInfo.cs, RulesForMedicalClaims.cs, RulesForMedicalClaims.csproj, RulesForMedicalClaims.sln</span></span>|<span data-ttu-id="81450-135">项目、 解决方案、 源和相关的文件，此示例中，以编程方式构成本示例 (RulesForMedicalClaims.exe) 和其中的主要可执行文件的部分定义和存储的规则集、 构造示例事实，然后运行使用设置的规则**PolicyTester**对象。</span><span class="sxs-lookup"><span data-stu-id="81450-135">Project, solution, source, and related files for the portion of this sample that constitutes the main executable for this sample (RulesForMedicalClaims.exe), and which programmatically defines and stores the rule set, constructs sample facts, and then runs the rule set using a **PolicyTester** object.</span></span>|  
|<span data-ttu-id="81450-136">\RulesForMedicalClaims 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="81450-136">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="81450-137">MedicalClaims.xsd</span><span class="sxs-lookup"><span data-stu-id="81450-137">MedicalClaims.xsd</span></span>|<span data-ttu-id="81450-138">此示例中定义的提交示例医疗索赔的结构的架构文件。</span><span class="sxs-lookup"><span data-stu-id="81450-138">Schema file that defines the structure of the sample medical claims submitted to this sample.</span></span>|  
|<span data-ttu-id="81450-139">\RulesForMedicalClaims 文件夹的内容：</span><span class="sxs-lookup"><span data-stu-id="81450-139">In the \RulesForMedicalClaims folder:</span></span><br /><br /> <span data-ttu-id="81450-140">sampleClaim.xml</span><span class="sxs-lookup"><span data-stu-id="81450-140">sampleClaim.xml</span></span>|<span data-ttu-id="81450-141">符合 MedicalClaims.xsd 在文件中定义的架构的示例输入的文件。</span><span class="sxs-lookup"><span data-stu-id="81450-141">Sample input file that conforms to the schema defined in the file MedicalClaims.xsd.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="81450-142">生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="81450-142">Building and Initializing This Sample</span></span>  
  
#### <a name="to-build-and-initialize-the-medical-claims-processing-and-testing-policies-sample"></a><span data-ttu-id="81450-143">生成并初始化“医疗索赔处理和测试保单”示例</span><span class="sxs-lookup"><span data-stu-id="81450-143">To build and initialize the Medical Claims Processing and Testing Policies sample</span></span>  
  
1. <span data-ttu-id="81450-144">确保您的计算机上具有 Northwind 数据库。</span><span class="sxs-lookup"><span data-stu-id="81450-144">Make sure that you have the Northwind database on your machine.</span></span>  
  
   > [!IMPORTANT]
   >  <span data-ttu-id="81450-145">若要运行此示例，必须具有 Northwind SQL Server 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="81450-145">To run this sample, you must have the Northwind SQL Server sample database.</span></span> <span data-ttu-id="81450-146">[下载](https://www.microsoft.com/download/details.aspx?id=23654)，并安装。</span><span class="sxs-lookup"><span data-stu-id="81450-146">[Download](https://www.microsoft.com/download/details.aspx?id=23654), and install.</span></span> 
  
2. <span data-ttu-id="81450-147">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="81450-147">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="81450-148">\<*示例路径*\>\Business Rules\Medical 声明 Processing and Testing Policies\\</span><span class="sxs-lookup"><span data-stu-id="81450-148">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\\</span></span>  
  
3. <span data-ttu-id="81450-149">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="81450-149">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="81450-150">为本示例编译并部署 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 项目，包括 Claims.dll、FactRetrieverForClaimsProcessing.dll 和 RulesForMedicalClaims.dll。</span><span class="sxs-lookup"><span data-stu-id="81450-150">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample, including Claims.dll, FactRetrieverForClaimsProcessing.dll, and RulesForMedicalClaims.dll.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="81450-151">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="81450-151">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="81450-152">如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="81450-152">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="81450-153">使用该密钥对可以对生成的程序集签名。</span><span class="sxs-lookup"><span data-stu-id="81450-153">Use this key pair to sign the resulting assemblies.</span></span>  
  
   - <span data-ttu-id="81450-154">运行提供的 SQL 脚本 Create_PolicyValidity_Table.sql 使用 SQL 查询分析器。</span><span class="sxs-lookup"><span data-stu-id="81450-154">Runs the provided SQL script Create_PolicyValidity_Table.sql using SQL Query Analyzer.</span></span> <span data-ttu-id="81450-155">该脚本创建表，PolicyValidity，与 Northwind 示例数据库中的两个示例行。</span><span class="sxs-lookup"><span data-stu-id="81450-155">The script creates the table, PolicyValidity, with two sample rows in the Northwind sample database.</span></span> <span data-ttu-id="81450-156">此表包含两列： ID 和 PolicyStatus。</span><span class="sxs-lookup"><span data-stu-id="81450-156">This table has two columns: ID and PolicyStatus.</span></span>  
  
   - <span data-ttu-id="81450-157">创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 发送端口和接收端口。</span><span class="sxs-lookup"><span data-stu-id="81450-157">Creates and binds the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] send and receive ports.</span></span>  
  
   - <span data-ttu-id="81450-158">启用接收位置并启动发送端口。</span><span class="sxs-lookup"><span data-stu-id="81450-158">Enables the receive location, and starts the send port.</span></span>  
  
   - <span data-ttu-id="81450-159">登记并启动业务流程。</span><span class="sxs-lookup"><span data-stu-id="81450-159">Enlists and starts orchestration.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="81450-160">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="81450-160">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="81450-161">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="81450-161">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="81450-162">运行本示例</span><span class="sxs-lookup"><span data-stu-id="81450-162">Running This Sample</span></span>  
  
#### <a name="to-run-the-medical-claims-processing-and-testing-policies-sample"></a><span data-ttu-id="81450-163">运行“医疗索赔处理和测试保单”示例</span><span class="sxs-lookup"><span data-stu-id="81450-163">To run the Medical Claims Processing and Testing Policies sample</span></span>  
  
1. <span data-ttu-id="81450-164">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="81450-164">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="81450-165">\<*示例路径*\>\Business Rules\Medical 索赔处理和测试 Policies\RulesForMedicalClaims\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="81450-165">\<*Samples Path*\>\Business Rules\Medical Claims Processing and Testing Policies\RulesForMedicalClaims\bin\Debug\\</span></span>  
  
2. <span data-ttu-id="81450-166">在命令行上运行文件 RulesForMedicalClaims.exe。</span><span class="sxs-lookup"><span data-stu-id="81450-166">Run the file RulesForMedicalClaims.exe on the command line.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="81450-167">可以更改的示例声明文件 sampleClaim.xml 中各个元素的值，并重复运行该示例。</span><span class="sxs-lookup"><span data-stu-id="81450-167">You can change the values of individual elements in the sample claim file sampleClaim.xml and run the sample repeatedly.</span></span> <span data-ttu-id="81450-168">在这些元素中的不同值的预期的输出所示后面的列表。</span><span class="sxs-lookup"><span data-stu-id="81450-168">The expected outputs for different values in these elements are shown in the list that follows.</span></span>  
  
   <span data-ttu-id="81450-169">基于已提交的示例声明文件中的值的各种组合的输出方案是：</span><span class="sxs-lookup"><span data-stu-id="81450-169">Output scenarios based on various combinations of values in the submitted sample claims file are:</span></span>  
  
-   <span data-ttu-id="81450-170">声明其量超过 1000 美元，可获得以下输出：</span><span class="sxs-lookup"><span data-stu-id="81450-170">For a claim whose amount exceeds $1000, the following output is obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of claim has exceeded Policy limit  
    ```  
  
-   <span data-ttu-id="81450-171">夜晚其数目超过 10 声明，可获得以下输出：</span><span class="sxs-lookup"><span data-stu-id="81450-171">For a claim whose number of nights exceeds 10, the following output is obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Amount of Nights has exceeded Policy limit  
    ```  
  
-   <span data-ttu-id="81450-172">声明其日期不是有效 (日期 > 当前日期)，则以下输出中获取：</span><span class="sxs-lookup"><span data-stu-id="81450-172">For a claim whose date is not valid (date > current date), the following output in obtained:</span></span>  
  
    ```  
    Status:  REJECTED!  
    Reason:  Cannot submit claims for future dates!  
    ```  
  
-   <span data-ttu-id="81450-173">对于不是有效的策略 ID 的声明 (例如，通过更改**ID**元素具有值为 2) 由于策略过期，获得以下输出：</span><span class="sxs-lookup"><span data-stu-id="81450-173">For a claim with a policy ID that is not valid (for example, by changing the **ID** element to have a value of 2) because of policy expiration, the following output is obtained:</span></span>  
  
    ```  
    Sending to Renewal Department for Customer Smir with Policy # 2  
    Status:  REJECTED!  
    Reason:  Policy ID is invalid  
    ```  
  
-   <span data-ttu-id="81450-174">声明的有效，可获得以下输出：</span><span class="sxs-lookup"><span data-stu-id="81450-174">For a claim that is valid, the following output is obtained:</span></span>  
  
    ```  
    Status:  Claim Accepted!  
    Reason:  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="81450-175">文本文件、 outputtrace.txt，每次运行此示例文件夹...\RulesForMedicalClaims\bin\Debug 文件夹中创建。</span><span class="sxs-lookup"><span data-stu-id="81450-175">A text file, outputtrace.txt, is created in the folder ...\RulesForMedicalClaims\bin\Debug folder every time you run this sample.</span></span> <span data-ttu-id="81450-176">它包含的规则执行调试跟踪和创建后下文件夹 \RulesForMedicalClaims\bin\Debug 每次执行循环。</span><span class="sxs-lookup"><span data-stu-id="81450-176">It contains a debug trace of rule execution, and it is created after every execution cycle under the folder \RulesForMedicalClaims\bin\Debug.</span></span> <span data-ttu-id="81450-177">可以检查该文件，请参阅输出跟踪规则执行。</span><span class="sxs-lookup"><span data-stu-id="81450-177">You can examine this file to see the output trace of rule execution.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="81450-178">注释</span><span class="sxs-lookup"><span data-stu-id="81450-178">Comments</span></span>  
 <span data-ttu-id="81450-179">将规则集计算中使用的事实源是：</span><span class="sxs-lookup"><span data-stu-id="81450-179">The fact sources used in the rule set evaluation are:</span></span>  
  
- <span data-ttu-id="81450-180">长期事实检索器。实现的基于网络的应用程序**IFactReriever**接口中，生成 FactRetrieverForClaimsProcessing 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="81450-180">A long-term fact retriever, a .NET-based application that implements the **IFactReriever** interface, is built in the folder FactRetrieverForClaimsProcessing.</span></span> <span data-ttu-id="81450-181">它使用医疗索赔处理策略从 PolicyValidity 数据库检索数据 （在数据集的形式） 并在规则条件计算中使用。</span><span class="sxs-lookup"><span data-stu-id="81450-181">It is used by the medical claims processing policy to retrieve data (in the form of a dataset) from the PolicyValidity database and to use in rule condition evaluation.</span></span>  
  
- <span data-ttu-id="81450-182">声明是包含以下信息，存储在同级元素的 XML 文档的形式： 名称、 ID、 数量、 夜晚和日期。</span><span class="sxs-lookup"><span data-stu-id="81450-182">The claim is in the form of an XML document that contains the following information, stored in sibling elements: Name, ID, Amount, Nights, and Date.</span></span>  
  
- <span data-ttu-id="81450-183">答:。基于 NET 的类库 （声明），与**ClaimResults**类用于记录状态以及使用属性、 声明的原因并发送一个潜在顾客 （如果该策略不是有效的） 通过调用**SendLeads**使用 ID 和名称作为参数的方法。</span><span class="sxs-lookup"><span data-stu-id="81450-183">A .NET-based class library (Claims), with a **ClaimResults** class is used to record the STATUS and REASON of the claim using properties, and to send a lead (if the policy is not valid) by invoking the **SendLeads** method with ID and name as parameters.</span></span>  
  
  <span data-ttu-id="81450-184">基于这些事实源，可以非正式地描述为这种情况下，如下所示定义的规则：</span><span class="sxs-lookup"><span data-stu-id="81450-184">Based on these fact sources, you can informally describe the rules defined for this scenario as follows:</span></span>  
  
1. <span data-ttu-id="81450-185">检查传入声明是否有效。</span><span class="sxs-lookup"><span data-stu-id="81450-185">Check to see if the incoming claim is valid.</span></span> <span data-ttu-id="81450-186">如果量高于允许限制声明，如果策略已过期 （已通过检查数据库表验证） 的夜晚数是否超过了最大允许的限制，并为将来日期作出声明，声明无效。</span><span class="sxs-lookup"><span data-stu-id="81450-186">The claim is not valid if the amount is over the allowable limit for a claim, if the policy has expired (verified by checking the database table), if the number of nights has exceeded the maximum allowable limit, and if the claim is made for a future date.</span></span> <span data-ttu-id="81450-187">如果已确定该声明不是有效，适当地设置的状态和原因的声明。</span><span class="sxs-lookup"><span data-stu-id="81450-187">If the claim has been determined to be not valid, set the STATUS and REASON of the claim appropriately.</span></span>  
  
2. <span data-ttu-id="81450-188">如果传入声明的策略 ID 已过期，请向策略续订部门发送 （与策略 ID 和客户名称）。</span><span class="sxs-lookup"><span data-stu-id="81450-188">If the policy ID of the incoming claim has expired, send a lead (with policy ID and customer name) to the policy renewal department.</span></span>  
  
3. <span data-ttu-id="81450-189">如果声明是有效的相应地设置的状态和原因的声明。</span><span class="sxs-lookup"><span data-stu-id="81450-189">If the claim is valid, set the STATUS and REASON of the claim appropriately.</span></span>  
  
   <span data-ttu-id="81450-190">规则和及其术语绑定的更正式表示形式如下所示：</span><span class="sxs-lookup"><span data-stu-id="81450-190">A more formal representation of the rules and their term bindings is as follows:</span></span>  
  
-   <span data-ttu-id="81450-191">**规则 1。量检查**</span><span class="sxs-lookup"><span data-stu-id="81450-191">**Rule 1. Amount check**</span></span>  
  
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
  
-   <span data-ttu-id="81450-192">**规则 2。在医院中所用的夜晚，**</span><span class="sxs-lookup"><span data-stu-id="81450-192">**Rule 2. Nights spent in the hospital**</span></span>  
  
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
  
-   <span data-ttu-id="81450-193">**规则 3。日期有效性**</span><span class="sxs-lookup"><span data-stu-id="81450-193">**Rule 3. Date validity**</span></span>  
  
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
  
-   <span data-ttu-id="81450-194">**规则 4。策略有效期**</span><span class="sxs-lookup"><span data-stu-id="81450-194">**Rule 4. Policy validity**</span></span>  
  
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
  
-   <span data-ttu-id="81450-195">**规则 5。潜在销售顾客**</span><span class="sxs-lookup"><span data-stu-id="81450-195">**Rule 5. Sales lead**</span></span>  
  
    ```  
    IF Claim.ClaimResults.Reason = "Policy invalid"  
  
    THEN send a lead to the policy department by invoking the function Claim.ClaimResults.SendLead with customer ID and Name from the incoming XML document.  
  
    ```  
  
-   <span data-ttu-id="81450-196">**规则 6。接受的声明**</span><span class="sxs-lookup"><span data-stu-id="81450-196">**Rule 6. Claim accepted**</span></span>  
  
    ```  
    IF Claim.ClaimResults.Status = null  
  
    THEN Set the claim status to be valid  
         &&  
         Send the lead to the sales department  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="81450-197">请参阅</span><span class="sxs-lookup"><span data-stu-id="81450-197">See Also</span></span>  
 [<span data-ttu-id="81450-198">业务规则（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="81450-198">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)