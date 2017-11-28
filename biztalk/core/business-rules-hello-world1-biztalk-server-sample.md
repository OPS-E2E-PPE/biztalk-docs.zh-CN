---
title: "业务规则 Hello World1 （BizTalk Server 示例） |Microsoft 文档"
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
ms.assetid: 0623ad20-96cc-430e-bb36-35431a5d17ee
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7231fd0d2aba7298127534eb43f1bf3c8c453b61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="business-rules-hello-world1-biztalk-server-sample"></a><span data-ttu-id="15aa8-102">业务规则 Hello World1 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="15aa8-102">Business Rules Hello World1 (BizTalk Server Sample)</span></span>
<span data-ttu-id="15aa8-103">“Business Rules Hello World1”示例演示如何创建一个 BizTalk 规则集，将它保存到文件 (SampleRuleSet.xml)、加载它并基于示例事实集运行它。</span><span class="sxs-lookup"><span data-stu-id="15aa8-103">The Business Rules Hello World1 sample demonstrates how to create a BizTalk rule set, save it to a file (SampleRuleSet.xml), load it, and run it based on a sample set of facts.</span></span> <span data-ttu-id="15aa8-104">本示例规则集包含一个简单规则，该规则使用 XML 元素和基于 .NET 的对象（属性和成员）作为规则定义中的条件。</span><span class="sxs-lookup"><span data-stu-id="15aa8-104">The sample rule set contains a simple rule that involves an XML element, and .NET-based objects (properties and members) as terms in rule definition.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="15aa8-105">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="15aa8-105">What This Sample Does</span></span>  
 <span data-ttu-id="15aa8-106">该示例创建一个执行以下一系列步骤的可执行文件：</span><span class="sxs-lookup"><span data-stu-id="15aa8-106">This sample creates an executable that performs the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="15aa8-107">调用的方法**CreateRuleset**生成中的规则集描述备注部分。</span><span class="sxs-lookup"><span data-stu-id="15aa8-107">Calls the method **CreateRuleset** to build the rule set described in the Remarks section.</span></span>  
  
2.  <span data-ttu-id="15aa8-108">调用的方法**SaveToFile**演示保存到文件设置的规则。</span><span class="sxs-lookup"><span data-stu-id="15aa8-108">Calls the method **SaveToFile** to demonstrate saving a rule set to a file.</span></span>  
  
3.  <span data-ttu-id="15aa8-109">调用的方法**LoadFromFile**演示加载从文件设置的规则。</span><span class="sxs-lookup"><span data-stu-id="15aa8-109">Calls the method **LoadFromFile** to demonstrate loading a rule set from a file.</span></span>  
  
4.  <span data-ttu-id="15aa8-110">构造运行规则集时所基于的示例事实。</span><span class="sxs-lookup"><span data-stu-id="15aa8-110">Constructs sample facts against which to run the rule set.</span></span>  
  
5.  <span data-ttu-id="15aa8-111">基于示例事实运行规则集，生成屏幕输出。</span><span class="sxs-lookup"><span data-stu-id="15aa8-111">Runs the rule set against the sample facts, producing screen output.</span></span>  
  
6.  <span data-ttu-id="15aa8-112">暂停，以便检查规则集文件 SampleRuleStore.xml。</span><span class="sxs-lookup"><span data-stu-id="15aa8-112">Pauses, enabling you to examine the rule set file SampleRuleStore.xml.</span></span>  
  
7.  <span data-ttu-id="15aa8-113">通过删除规则集文件进行清除，以便为后续的示例运行做好准备。</span><span class="sxs-lookup"><span data-stu-id="15aa8-113">Cleans up by deleting the rule set file in preparation for subsequent runs of the sample.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="15aa8-114">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="15aa8-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="15aa8-115">\<*示例路径*> \Business Rules\Business 规则 Hello World1\\</span><span class="sxs-lookup"><span data-stu-id="15aa8-115">\<*Samples Path*>\Business Rules\Business Rules Hello World1\\</span></span>  
  
 <span data-ttu-id="15aa8-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="15aa8-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="15aa8-117">文件</span><span class="sxs-lookup"><span data-stu-id="15aa8-117">File(s)</span></span>|<span data-ttu-id="15aa8-118">Description</span><span class="sxs-lookup"><span data-stu-id="15aa8-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="15aa8-119">App.ico、AssemblyInfo.cs、BusinessRulesHelloWorld1.csproj、BusinessRulesHelloWorld1.sln</span><span class="sxs-lookup"><span data-stu-id="15aa8-119">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld1.csproj, BusinessRulesHelloWorld1.sln</span></span>|<span data-ttu-id="15aa8-120">本示例某部分的项目、解决方案和相关文件，该部分用于创建、保存、加载和运行规则集。</span><span class="sxs-lookup"><span data-stu-id="15aa8-120">Project, solution, and related files for the portion of this sample that creates, saves, loads, and runs a rule set.</span></span>|  
|<span data-ttu-id="15aa8-121">HelloWorld1.cs</span><span class="sxs-lookup"><span data-stu-id="15aa8-121">HelloWorld1.cs</span></span>|<span data-ttu-id="15aa8-122">Visual C# 文件，包含用于演示创建规则集、将规则集保存到文件以及从文件加载规则集的方法，</span><span class="sxs-lookup"><span data-stu-id="15aa8-122">Visual C# file that contains methods to demonstrate creating a rule set, saving a rule set to a file, and loading a rule set from a file.</span></span> <span data-ttu-id="15aa8-123">此外，还包含调用这些方法然后运行所创建规则集的外层代码。</span><span class="sxs-lookup"><span data-stu-id="15aa8-123">Also contains surrounding code that calls these methods and then runs the created rule set.</span></span>|  
|<span data-ttu-id="15aa8-124">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="15aa8-124">Cleanup.bat</span></span>|<span data-ttu-id="15aa8-125">用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。</span><span class="sxs-lookup"><span data-stu-id="15aa8-125">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="15aa8-126">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="15aa8-126">Removes send and receive ports.</span></span> <span data-ttu-id="15aa8-127">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="15aa8-127">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="15aa8-128">SampleDocumentInstance.xml</span><span class="sxs-lookup"><span data-stu-id="15aa8-128">SampleDocumentInstance.xml</span></span>|<span data-ttu-id="15aa8-129">与文件 SampleSchema.xsd 中定义的架构相符的示例输入文件。</span><span class="sxs-lookup"><span data-stu-id="15aa8-129">Sample input file that conforms to the schema defined in the file SampleSchema.xsd.</span></span>|  
|<span data-ttu-id="15aa8-130">SampleSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="15aa8-130">SampleSchema.xsd</span></span>|<span data-ttu-id="15aa8-131">定义简单架构的架构文件，该简单架构具有由 Visual C# 文件 HelloWorld1.cs 中创建的规则集引用的元素。</span><span class="sxs-lookup"><span data-stu-id="15aa8-131">Schema file that defines a simple schema with an element referenced by the rule set created in the Visual C# file HelloWorld1.cs.</span></span>|  
|<span data-ttu-id="15aa8-132">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="15aa8-132">Setup.bat</span></span>|<span data-ttu-id="15aa8-133">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="15aa8-133">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="15aa8-134">在 \MySampleLibrary 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="15aa8-134">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="15aa8-135">AssemblyInfo.cs、MySampleLibrary.csproj、MySampleLibrary.sln</span><span class="sxs-lookup"><span data-stu-id="15aa8-135">AssemblyInfo.cs, MySampleLibrary.csproj, MySampleLibrary.sln</span></span>|<span data-ttu-id="15aa8-136">该示例某部分的项目、解决方案和相关文件，该部分提供定义由所创建规则集引用的对象的类。</span><span class="sxs-lookup"><span data-stu-id="15aa8-136">Project, solution, and related files for the portion of this sample that provides the class that defines the objects referenced by the created rule set.</span></span>|  
|<span data-ttu-id="15aa8-137">在 \MySampleLibrary 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="15aa8-137">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="15aa8-138">MySampleLibraryClass.cs</span><span class="sxs-lookup"><span data-stu-id="15aa8-138">MySampleLibraryClass.cs</span></span>|<span data-ttu-id="15aa8-139">Visual C# 文件包含在中引用的属性**如果**一部分创建的规则，并可能在调用的方法**然后**一部分创建的规则。</span><span class="sxs-lookup"><span data-stu-id="15aa8-139">Visual C# file that contains the property referenced in the **IF** portion of the created rule, and the method that may be called in the **THEN** portion of the created rule.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="15aa8-140">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="15aa8-140">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="15aa8-141">使用以下过程可生成并初始化“Business Rules Hello World1”示例。</span><span class="sxs-lookup"><span data-stu-id="15aa8-141">Use the following procedure to build and initialize the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="15aa8-142">构建和初始化此示例</span><span class="sxs-lookup"><span data-stu-id="15aa8-142">To build and initialize this sample</span></span>  
  
1.  <span data-ttu-id="15aa8-143">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="15aa8-143">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="15aa8-144">\<*示例路径*> \Business Rules\Business 规则 Hello World1\\</span><span class="sxs-lookup"><span data-stu-id="15aa8-144">\<*Samples Path*>\Business Rules\Business Rules Hello World1\\</span></span>  
  
2.  <span data-ttu-id="15aa8-145">运行 Setup.bat 文件，该文件将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="15aa8-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
    -   <span data-ttu-id="15aa8-146">编译和部署 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例的项目。</span><span class="sxs-lookup"><span data-stu-id="15aa8-146">Compiles and deploys the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15aa8-147">在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。</span><span class="sxs-lookup"><span data-stu-id="15aa8-147">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15aa8-148">如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="15aa8-148">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="15aa8-149">使用该密钥对可以对生成的程序集签名。</span><span class="sxs-lookup"><span data-stu-id="15aa8-149">Use this key pair to sign the resulting assemblies.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15aa8-150">若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="15aa8-150">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="15aa8-151">在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。</span><span class="sxs-lookup"><span data-stu-id="15aa8-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="15aa8-152">运行本示例</span><span class="sxs-lookup"><span data-stu-id="15aa8-152">Running This Sample</span></span>  
 <span data-ttu-id="15aa8-153">使用以下过程可运行“Business Rules Hello World1”示例。</span><span class="sxs-lookup"><span data-stu-id="15aa8-153">Use the following procedure to run the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="15aa8-154">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="15aa8-154">To run this sample</span></span>  
  
1.  <span data-ttu-id="15aa8-155">在命令窗口中，导航到下面的文件夹：</span><span class="sxs-lookup"><span data-stu-id="15aa8-155">In a command window, navigate to the following folder:</span></span>  
  
     <span data-ttu-id="15aa8-156">\<*示例路径*> \Business Rules\Business 规则 Hello World1\bin\Debug\\</span><span class="sxs-lookup"><span data-stu-id="15aa8-156">\<*Samples Path*>\Business Rules\Business Rules Hello World1\bin\Debug\\</span></span>  
  
2.  <span data-ttu-id="15aa8-157">在命令窗口中，键入本示例的可执行文件名 (BusinessRulesHelloWorld2.exe)，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="15aa8-157">In the command window, type the name of the executable file for this sample (BusinessRulesHelloWorld1.exe), and then press ENTER.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="15aa8-158">运行时，此规则集文件中的 SampleRuleStore.xml 的示例生成**bin\Debug**文件夹。</span><span class="sxs-lookup"><span data-stu-id="15aa8-158">While running, this sample produces the rule set file SampleRuleStore.xml in the **bin\Debug** folder.</span></span> <span data-ttu-id="15aa8-159">当可执行文件暂停以等待您按 Enter 以完成运行时，您可检查此文件的内容。</span><span class="sxs-lookup"><span data-stu-id="15aa8-159">When the executable pauses, waiting for you to press ENTER to finish, you can examine the contents of this file.</span></span> <span data-ttu-id="15aa8-160">按任何键以完成操作之前，请务必关闭该文件。</span><span class="sxs-lookup"><span data-stu-id="15aa8-160">Remember to close it before pressing any key to finish.</span></span> <span data-ttu-id="15aa8-161">否则，可执行文件可能无法删除该规则集文件以为后续的示例运行做好准备。</span><span class="sxs-lookup"><span data-stu-id="15aa8-161">Otherwise, the executable may not be able to delete it in preparation for subsequent runs of the sample.</span></span>  
  
 <span data-ttu-id="15aa8-162">如果在使用提供的示例输入文件 SampleDocumentInstance.xml，为定义的值为一 (1) 运行此示例基于对创建的规则集的性质其**ID**元素，你将看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="15aa8-162">Based on the nature of the created rule set, if you run this sample with the provided sample input file SampleDocumentInstance.xml, which has a value of one (1) defined for its **ID** element, you will see the following output:</span></span>  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Asserting objects ...  
Executing ...  
MySampleBusinessObject Class -- MySampleMethod executed for object 2 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
Press any key to finish ...  
```  
  
> [!NOTE]
>  <span data-ttu-id="15aa8-163">加粗，同时在上面的代码并将在后面的代码，输出由生成定义中的文件的示例业务对象中所示的输出**MySampleLibrary**文件夹中，这由规则集引用。</span><span class="sxs-lookup"><span data-stu-id="15aa8-163">The output shown in bold, both in the preceding code and in the code that follows, is the output produced by the sample business object, defined by the files in the **MySampleLibrary** folder, which is referenced by the rule set.</span></span>  
  
 <span data-ttu-id="15aa8-164">如果更改与关联的值**ID**示例输入文件中的元素**SampleDocumentInstance.xml**从一个 （1） 到两 （2），输出将更改，如下所示：</span><span class="sxs-lookup"><span data-stu-id="15aa8-164">If you change the value associated with the **ID** element in the sample input file **SampleDocumentInstance.xml** from one (1) to two (2), the output would change as follows:</span></span>  
  
```  
Creating a new ruleset ...  
Saving ruleset to SampleRuleStore.xml ...  
Loading ruleset ...  
Asserting objects ...  
Executing ...  
MySampleBusinessObject Class -- MySampleMethod executed for object 1 with parameter 5  
MySampleBusinessObject Class -- MySampleMethod executed for object 3 with parameter 5  
Press any key to finish ...  
```  
  
 <span data-ttu-id="15aa8-165">将不会获取输出行的任何对象**MySampleBusinessObject**类具有其**MyValue**属性设置为与匹配与关联的值（在期间构造）的值**ID**示例输入文件 SampleDocumentInstance.xml 中的元素。</span><span class="sxs-lookup"><span data-stu-id="15aa8-165">You will not get an output line for any objects of the **MySampleBusinessObject** class that have their **MyValue** property set to a value (during construction) that matches the value associated with the **ID** element in the sample input file SampleDocumentInstance.xml.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="15aa8-166">注释</span><span class="sxs-lookup"><span data-stu-id="15aa8-166">Comments</span></span>  
 <span data-ttu-id="15aa8-167">以编程方式内创建的规则**CreateRuleset()**方法所示：</span><span class="sxs-lookup"><span data-stu-id="15aa8-167">The rule created programmatically within the **CreateRuleset()** method shows:</span></span>  
  
 <span data-ttu-id="15aa8-168">**如果**</span><span class="sxs-lookup"><span data-stu-id="15aa8-168">**IF**</span></span>  
  
 <span data-ttu-id="15aa8-169">**MySampleBusinessObject.MyValue**是否不等于的值**ID** XML 文档中的元素。</span><span class="sxs-lookup"><span data-stu-id="15aa8-169">**MySampleBusinessObject.MyValue** is not equal to the value of the **ID** element in the XML document.</span></span>  
  
 <span data-ttu-id="15aa8-170">**然后**</span><span class="sxs-lookup"><span data-stu-id="15aa8-170">**THEN**</span></span>  
  
 <span data-ttu-id="15aa8-171">**MySampleBusinessObject.MySampleMethod(int)**用整数参数，硬编码到常量五 （5） 在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="15aa8-171">**MySampleBusinessObject.MySampleMethod(int)** with an integer parameter, hard coded to the constant five (5) in this case.</span></span> <span data-ttu-id="15aa8-172">此方法产生开头的输出行**MySampleBusinessObject 类 –-**。</span><span class="sxs-lookup"><span data-stu-id="15aa8-172">This method produces the output lines that begin **MySampleBusinessObject Class –-**.</span></span>  
  
 <span data-ttu-id="15aa8-173">此规则依赖于以下项：</span><span class="sxs-lookup"><span data-stu-id="15aa8-173">This rule depends on the following:</span></span>  
  
-   <span data-ttu-id="15aa8-174">A **MySampleBusinessObject**具有公共属性调用类**MyValue**并调用一个公共方法**MySampleMethod** （采用一个整数参数）。</span><span class="sxs-lookup"><span data-stu-id="15aa8-174">A **MySampleBusinessObject** class with a public property called **MyValue** and a public method called **MySampleMethod** (that takes in an integer parameter).</span></span>  
  
-   <span data-ttu-id="15aa8-175">定义 XML 文档包含 XML 架构定义语言 (XSD) 架构**ID**元素。</span><span class="sxs-lookup"><span data-stu-id="15aa8-175">An XML schema definition language (XSD) schema that defines an XML document that contains an **ID** element.</span></span>  
  
 <span data-ttu-id="15aa8-176">您可根据类和架构定义规则，但在执行过程中，必须使用相关类的对象实例和相关架构的文档实例。</span><span class="sxs-lookup"><span data-stu-id="15aa8-176">You define rules in terms of classes and schemas, but during execution, object instances of the relevant classes and document instances of the relevant schemas are required.</span></span> <span data-ttu-id="15aa8-177">您将针对这些运行时实例（称为事实）来评估规则。</span><span class="sxs-lookup"><span data-stu-id="15aa8-177">You evaluate the rules against these run-time instances (known as facts).</span></span> <span data-ttu-id="15aa8-178">在此示例中，事实数据的多个实例**MySampleBusinessObject**构造使用不同值的对象，其**MyValue**属性，并定义的架构的单个 XML 实例包含的值， **ID**元素。</span><span class="sxs-lookup"><span data-stu-id="15aa8-178">In this sample, the facts are multiple instances of the **MySampleBusinessObject** object, constructed with different values for their **MyValue** property, and a single XML instance of the defined schema that contains a value for the **ID** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15aa8-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="15aa8-179">See Also</span></span>  
 [<span data-ttu-id="15aa8-180">业务规则 （BizTalk Server 示例文件夹中）</span><span class="sxs-lookup"><span data-stu-id="15aa8-180">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)