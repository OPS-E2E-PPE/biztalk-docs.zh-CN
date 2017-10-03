---
title: "业务规则 Hello World2 （BizTalk Server 示例） |Microsoft 文档"
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
ms.assetid: 2a88a2a0-8cb6-4373-8441-0ab04345a477
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48d92d3de6b4ef6b4d541d7f64e0d483feb9c30f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="business-rules-hello-world2-biztalk-server-sample"></a><span data-ttu-id="d502a-102">业务规则 Hello World2 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="d502a-102">Business Rules Hello World2 (BizTalk Server Sample)</span></span>
<span data-ttu-id="d502a-103">业务规则 Hello World2 示例扩展业务规则 Hello World1 示例，演示如何为版本，发布和部署 XML 规则设置为共享的 SQL 规则存储，以及如何运行策略使用**策略**对象框架提供的业务规则。</span><span class="sxs-lookup"><span data-stu-id="d502a-103">The Business Rules Hello World2 sample extends the Business Rules Hello World1 sample by demonstrating how to version, publish, and deploy the XML rule set to the shared SQL rule store, and how to run the policy using the **Policy** object provided by the Business Rules Framework.</span></span> <span data-ttu-id="d502a-104">该示例还演示了操作中的动态策略更新。</span><span class="sxs-lookup"><span data-stu-id="d502a-104">The sample also demonstrates dynamic policy updates in action.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d502a-105">该示例假设在安装产品过程中，用户已安装了规则引擎更新服务和业务规则组件（位于“其他软件”节点下）。</span><span class="sxs-lookup"><span data-stu-id="d502a-105">This sample assumes that the user has installed the Rule Engine Update Service and Business Rules Components (located under the "Additional Software" node) during installation of the product.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d502a-106">你使用**策略**要将规则引擎集成到任何独立的应用程序的对象。</span><span class="sxs-lookup"><span data-stu-id="d502a-106">You use **Policy** objects to integrate the rule engine into any stand-alone application.</span></span> <span data-ttu-id="d502a-107">**策略**对象是通过的多个规则管理引擎实例的抽象，规则集，将检索并从共享的 SQL 存储，实例化和将检索策略的更新并将其发布到宿主应用程序。</span><span class="sxs-lookup"><span data-stu-id="d502a-107">The **Policy** object is the abstraction through which multiple rule engine instances are managed, rule sets are retrieved and instantiated from the shared SQL store, and updates to the policies are retrieved and published to the hosting application.</span></span>  
  
 <span data-ttu-id="d502a-108">此示例中，通过构造的事实数据有关的规则集定义，和示例的基本信息请参阅[业务规则 Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="d502a-108">For basic information about the rule set defined, and sample facts constructed by this sample, see [Business Rules Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md).</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="d502a-109">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="d502a-109">What This Sample Does</span></span>  
 <span data-ttu-id="d502a-110">该示例创建一个执行以下一系列步骤的可执行文件：</span><span class="sxs-lookup"><span data-stu-id="d502a-110">This sample creates an executable that performs the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="d502a-111">调用的方法**CreateRuleset**生成中的规则集描述备注部分。</span><span class="sxs-lookup"><span data-stu-id="d502a-111">Calls the method **CreateRuleset** to build the rule set described in the Remarks section.</span></span>  
  
2.  <span data-ttu-id="d502a-112">调用的方法**SaveToFile**演示保存到文件设置的规则。</span><span class="sxs-lookup"><span data-stu-id="d502a-112">Calls the method **SaveToFile** to demonstrate saving a rule set to a file.</span></span>  
  
3.  <span data-ttu-id="d502a-113">调用的方法**LoadFromFile**演示加载从文件设置的规则。</span><span class="sxs-lookup"><span data-stu-id="d502a-113">Calls the method **LoadFromFile** to demonstrate loading a rule set from a file.</span></span>  
  
4.  <span data-ttu-id="d502a-114">将规则集部署到共享 SQL 规则存储。</span><span class="sxs-lookup"><span data-stu-id="d502a-114">Deploys the rule set to a shared SQL rule store.</span></span>  
  
5.  <span data-ttu-id="d502a-115">运行的规则集使用**策略**对象，并通过使用相同的示例在业务规则 Hello World1 中使用的事实数据集示例。</span><span class="sxs-lookup"><span data-stu-id="d502a-115">Runs the rule set by using a **Policy** object, and by using the same set of sample facts used in the Business Rules Hello World1 sample.</span></span>  
  
6.  <span data-ttu-id="d502a-116">暂停，使你能够修改规则设置文件**SampleRuleStore.xml**以特定方式。</span><span class="sxs-lookup"><span data-stu-id="d502a-116">Pauses, enabling you to modify the rule set file **SampleRuleStore.xml** in a specific way.</span></span>  
  
7.  <span data-ttu-id="d502a-117">运行的规则集再次使用**策略**对象，现在已修改的规则集，并再次使用相同的示例在业务规则 Hello World1 中使用的事实数据集示例。</span><span class="sxs-lookup"><span data-stu-id="d502a-117">Runs the rule set again using a **Policy** object, the now modified rule set, and again with the same set of sample facts used in the Business Rules Hello World1 sample.</span></span>  
  
8.  <span data-ttu-id="d502a-118">通过删除规则集文件和部署的规则集记录进行清除，以便为后续的示例运行做准备。</span><span class="sxs-lookup"><span data-stu-id="d502a-118">Cleans up by deleting the rule set file and the deployed rule set records in preparation for subsequent running of the sample.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d502a-119">有关在此 SDK 中的所有示例的重要信息，请参阅[示例](../core/samples-in-the-sdk.md)。</span><span class="sxs-lookup"><span data-stu-id="d502a-119">For important information about all samples in this SDK, see [Samples](../core/samples-in-the-sdk.md).</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="d502a-120">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="d502a-120">Where to Find This Sample</span></span>  
 <span data-ttu-id="d502a-121">*\<示例路径 >*\Business Rules\Business 规则 Hello World2\\</span><span class="sxs-lookup"><span data-stu-id="d502a-121">*\<Samples Path>*\Business Rules\Business Rules Hello World2\\</span></span>  
  
 <span data-ttu-id="d502a-122">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="d502a-122">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="d502a-123">文件</span><span class="sxs-lookup"><span data-stu-id="d502a-123">File(s)</span></span>|<span data-ttu-id="d502a-124">Description</span><span class="sxs-lookup"><span data-stu-id="d502a-124">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d502a-125">App.ico、AssemblyInfo.cs、BusinessRulesHelloWorld2.csproj、BusinessRulesHelloWorld2.sln</span><span class="sxs-lookup"><span data-stu-id="d502a-125">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld2.csproj, BusinessRulesHelloWorld2.sln</span></span>|<span data-ttu-id="d502a-126">该示例某部分的项目、解决方案和相关文件，该部分创建、保存、加载、部署和执行规则集。</span><span class="sxs-lookup"><span data-stu-id="d502a-126">Project, solution, and related files for the portion of this sample that creates, saves, loads, deploys, and executes a rule set.</span></span>|  
|<span data-ttu-id="d502a-127">HelloWorld2.cs</span><span class="sxs-lookup"><span data-stu-id="d502a-127">HelloWorld2.cs</span></span>|<span data-ttu-id="d502a-128">Visual C# 文件都包含用于演示创建规则方法设置，保存到文件中，加载从文件中，设置的规则设置的规则部署规则设置为一个共享的 Microsoft SQL Server 规则存储，并且使用然后运行该规则设置**策略**对象。</span><span class="sxs-lookup"><span data-stu-id="d502a-128">Visual C# file that contains methods to demonstrate creating a rule set, saving a rule set to a file, loading a rule set from a file, deploying the rule set to a shared Microsoft SQL Server rule store, and then running the rule set by using a **Policy** object.</span></span>|  
|<span data-ttu-id="d502a-129">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="d502a-129">Cleanup.bat</span></span>|<span data-ttu-id="d502a-130">用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="d502a-130">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="d502a-131">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="d502a-131">Removes send and receive ports.</span></span> <span data-ttu-id="d502a-132">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="d502a-132">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="d502a-133">SampleDocumentInstance.xml</span><span class="sxs-lookup"><span data-stu-id="d502a-133">SampleDocumentInstance.xml</span></span>|<span data-ttu-id="d502a-134">与文件 SampleSchema.xsd 中定义的架构相符的示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="d502a-134">Sample input file that conforms to the schema defined in the file SampleSchema.xsd.</span></span>|  
|<span data-ttu-id="d502a-135">SampleSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="d502a-135">SampleSchema.xsd</span></span>|<span data-ttu-id="d502a-136">定义简单架构的架构文件，该简单架构具有由 Visual C# 文件 Class1.cs 中创建的规则集引用的元素。</span><span class="sxs-lookup"><span data-stu-id="d502a-136">Schema file that defines a simple schema with an element referenced by the rule set created in the Visual C# file Class1.cs.</span></span>|  
|<span data-ttu-id="d502a-137">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="d502a-137">Setup.bat</span></span>|<span data-ttu-id="d502a-138">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="d502a-138">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="d502a-139">在 \HelloWorld2Library 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d502a-139">In the \HelloWorld2Library folder:</span></span><br /><br /> <span data-ttu-id="d502a-140">AssemblyInfo.cs、HelloWorld2Library.csproj、HelloWorld2Library.sln</span><span class="sxs-lookup"><span data-stu-id="d502a-140">AssemblyInfo.cs, HelloWorld2Library.csproj, HelloWorld2Library.sln</span></span>|<span data-ttu-id="d502a-141">该示例某部分的项目、解决方案和相关文件，该部分提供定义由所创建规则集引用的对象的类。</span><span class="sxs-lookup"><span data-stu-id="d502a-141">Project, solution, and related files for the portion of this sample that provides the class that defines the objects referenced by the created rule set.</span></span>|  
|<span data-ttu-id="d502a-142">在 \HelloWorld2Library 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d502a-142">In the \HelloWorld2Library folder:</span></span><br /><br /> <span data-ttu-id="d502a-143">HelloWorld2LibraryClass.cs</span><span class="sxs-lookup"><span data-stu-id="d502a-143">HelloWorld2LibraryClass.cs</span></span>|<span data-ttu-id="d502a-144">Visual C# 文件包含在中引用的属性**如果**一部分创建的规则，并可能在调用的方法**然后**一部分创建的规则。</span><span class="sxs-lookup"><span data-stu-id="d502a-144">Visual C# file that contains the property referenced in the **IF** portion of the created rule, and the method that may be called in the **THEN** portion of the created rule.</span></span>|  
  
### <a name="to-build-and-initialize-the-business-rules-hello-world2-sample"></a><span data-ttu-id="d502a-145">生成并初始化业务规则 Hello World2 示例</span><span class="sxs-lookup"><span data-stu-id="d502a-145">To build and initialize the Business Rules Hello World2 sample</span></span>  
  
1.  <span data-ttu-id="d502a-146">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="d502a-146">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="d502a-147">*\<示例路径 >*\Business Rules\Business 规则 Hello World2\\</span><span class="sxs-lookup"><span data-stu-id="d502a-147">*\<Samples Path>*\Business Rules\Business Rules Hello World2\\</span></span>  
  
2.  <span data-ttu-id="d502a-148">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d502a-148">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="d502a-149">编译并将部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例的项目。</span><span class="sxs-lookup"><span data-stu-id="d502a-149">Compiles and deploys the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d502a-150">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="d502a-150">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d502a-151">如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="d502a-151">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="d502a-152">使用该密钥对可以对生成的程序集签名。</span><span class="sxs-lookup"><span data-stu-id="d502a-152">Use this key pair to sign the resulting assemblies.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d502a-153">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="d502a-153">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="d502a-154">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="d502a-154">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
### <a name="to-run-the-business-rules-hello-world2-sample"></a><span data-ttu-id="d502a-155">运行业务规则 Hello World2 示例</span><span class="sxs-lookup"><span data-stu-id="d502a-155">To run the Business Rules Hello World2 sample</span></span>  
  
1.  <span data-ttu-id="d502a-156">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="d502a-156">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="d502a-157">*\<示例路径 >*\Business Rules\Business 规则 Hello World2\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="d502a-157">*\<Samples Path>*\Business Rules\Business Rules Hello World2\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="d502a-158">在命令窗口中，键入此示例的文件的名称 (**BusinessRulesHelloWorld2.exe**)，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="d502a-158">In the command window, type the name of the file for this sample (**BusinessRulesHelloWorld2.exe**), and then press ENTER.</span></span>  
  
## <a name="hello-world2-output"></a><span data-ttu-id="d502a-159">Hello World2 输出</span><span class="sxs-lookup"><span data-stu-id="d502a-159">Hello World2 Output</span></span>  
 <span data-ttu-id="d502a-160">根据创建的规则集中的注释部分所述的特性[业务规则 Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md)，如果在使用提供的示例输入文件 SampleDocumentInstance.xml，定义的值为一 (1) 运行此示例有关其**ID**元素，你将看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="d502a-160">Based on the nature of the created rule set, described in the Comments section of [Business Rules Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md), if you run this sample with the provided sample input file SampleDocumentInstance.xml, which has a value of one (1) defined for its **ID** element, you will see the following output:</span></span>  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Deploying the ruleset ...  
Sleeping for 60 seconds (so that the deployed ruleset becomes effective) ...  
Grabbing the policy ...  
Executing the policy...  
MySampleBusinessObject Class -- MySampleMethod executed for object 2 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
The major version of the policy was: 1  
The minor version of the policy was: 0  
Press the ENTER to continue after updating the policy...  
```  
  
> [!NOTE]
>  <span data-ttu-id="d502a-161">以粗体显示的输出是生成定义中的文件的示例业务对象的输出**HelloWorld2Library**规则集引用的文件夹。</span><span class="sxs-lookup"><span data-stu-id="d502a-161">The output shown in bold is the output produced by the sample business object, defined by the files in the **HelloWorld2Library** folder that the rule set references.</span></span> <span data-ttu-id="d502a-162">此时，应用程序在此状态下等待。</span><span class="sxs-lookup"><span data-stu-id="d502a-162">At this point, the application is left waiting in this state.</span></span>  
  
 <span data-ttu-id="d502a-163">运行示例的下一部分涉及使用业务规则编辑器更改业务规则。</span><span class="sxs-lookup"><span data-stu-id="d502a-163">The next part of running the sample involves using the Business Rules Composer to change the business rules.</span></span>  
  
#### <a name="to-use-the-business-rules-composer-to-change-the-business-rules"></a><span data-ttu-id="d502a-164">使用业务规则编辑器更改业务规则</span><span class="sxs-lookup"><span data-stu-id="d502a-164">To use the Business Rules Composer to change the business rules</span></span>  
  
1.  <span data-ttu-id="d502a-165">若要打开业务规则编辑器，请单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则编辑器**。</span><span class="sxs-lookup"><span data-stu-id="d502a-165">To open the Business Rules Composer, click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **Business Rules Composer**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d502a-166">在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。</span><span class="sxs-lookup"><span data-stu-id="d502a-166">On a system that supports User Account Control (UAC), you may need to run the tool with Administrative privileges.</span></span> <span data-ttu-id="d502a-167">要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。</span><span class="sxs-lookup"><span data-stu-id="d502a-167">To do this, right-click the application, and then select **Run as administrator**.</span></span>  
  
2.  <span data-ttu-id="d502a-168">如果运行 SQL Server 的计算机上出现 SQL Server 对话框中，单击**确定**以连接到规则存储。</span><span class="sxs-lookup"><span data-stu-id="d502a-168">If a SQL Server dialog box appears on the computer running SQL Server, click **OK** to connect to the rule store.</span></span>  
  
3.  <span data-ttu-id="d502a-169">在**策略资源管理器**下面**SampleRuleSet**节点，右键单击该节点**版本 1.0 – 部署**，然后单击**复制**。</span><span class="sxs-lookup"><span data-stu-id="d502a-169">In **Policy Explorer**, below the **SampleRuleSet** node, right-click the node **Version 1.0 – Deployed**, and then click **Copy**.</span></span>  
  
4.  <span data-ttu-id="d502a-170">右键单击**SampleRuleSet**，然后单击**粘贴 （策略版本）**。</span><span class="sxs-lookup"><span data-stu-id="d502a-170">Right-click **SampleRuleSet**, and then click **Paste (Policy Version)**.</span></span>  
  
5.  <span data-ttu-id="d502a-171">可以更改规则条件和操作以满足需求。</span><span class="sxs-lookup"><span data-stu-id="d502a-171">You can change the rule condition and action to meet your needs.</span></span> <span data-ttu-id="d502a-172">有关此过程中，单击**规则 1**中**（不保存） 1.1 版**。</span><span class="sxs-lookup"><span data-stu-id="d502a-172">For this procedure, click **rule1** in **Version 1.1 (not saved)**.</span></span> <span data-ttu-id="d502a-173">在右窗格中，右键单击**条件**，然后单击**添加不逻辑**。</span><span class="sxs-lookup"><span data-stu-id="d502a-173">In the right pane, right-click **Conditions**, and then click **Add Logical NOT**.</span></span> <span data-ttu-id="d502a-174">添加**不逻辑**操作**不等于**以谓词相当于使用**相等**谓词。</span><span class="sxs-lookup"><span data-stu-id="d502a-174">Adding a **Logical NOT** operation to **Not Equal** to predicate is equivalent to using an **Equal** predicate.</span></span>  
  
6.  <span data-ttu-id="d502a-175">右键单击该节点**（不保存） 1.1 版**，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="d502a-175">Right-click the node **Version 1.1(not saved)**, and then click **Save**.</span></span> <span data-ttu-id="d502a-176">再次右键单击，并依次**发布**。</span><span class="sxs-lookup"><span data-stu-id="d502a-176">Right-click again, and then click **Publish**.</span></span> <span data-ttu-id="d502a-177">右键单击第三次，然后单击**部署**。</span><span class="sxs-lookup"><span data-stu-id="d502a-177">Right-click a third time and click **Deploy**.</span></span>  
  
7.  <span data-ttu-id="d502a-178">更新策略之后，在暂停的命令窗口中将让您按任意键继续，请按任意键。</span><span class="sxs-lookup"><span data-stu-id="d502a-178">In the paused command window asking you to press any key to continue after updating the policy, press any key.</span></span>  
  
 <span data-ttu-id="d502a-179">来自可执行文件 BusinessRulesHelloWorld2.exe 的输出（假设您通过添加逻辑非更改了规则）继续显示如下：</span><span class="sxs-lookup"><span data-stu-id="d502a-179">Output (assuming you changed the rule by adding a logical Not) from the executable file BusinessRulesHelloWorld2.exe continues as follows:</span></span>  
  
```  
Sleeping for 60 seconds (so that the deployed ruleset becomes effective) ...         
Grabbing the policy ...         
Executing the policy...         
MySampleBusinessObject Class -- MySampleMethod executed for object 1 with parameter 5         
The major version of the policy was: 1         
The minor version of the policy was: 1         
Press ENTER to continue after updating the policy...         
```  
  
 <span data-ttu-id="d502a-180">请注意输出如何变化：</span><span class="sxs-lookup"><span data-stu-id="d502a-180">Notice how the output has changed:</span></span>  
  
-   <span data-ttu-id="d502a-181">在方法中的输出行**MySampleMethod**仅的实例的一次现在，打印**MySampleBusinessObject**为其类**MyValue**属性等于 1而不是打印时的上一个规则**MyValue**属性是否不等于 1。</span><span class="sxs-lookup"><span data-stu-id="d502a-181">The output line in the method **MySampleMethod** only prints once now, for the instance of the **MySampleBusinessObject** class for which the **MyValue** property is equal to 1, rather than the previous rule of printing when the **MyValue** property is not equal to 1.</span></span>  
  
-   <span data-ttu-id="d502a-182">策略的次要版本号现在为 1。</span><span class="sxs-lookup"><span data-stu-id="d502a-182">The minor version number of the policy is now 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d502a-183">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d502a-183">See Also</span></span>  
 [<span data-ttu-id="d502a-184">业务规则 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="d502a-184">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)