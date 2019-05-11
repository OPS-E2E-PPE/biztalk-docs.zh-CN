---
title: 业务规则 Hello World1 （BizTalk Server 示例） |Microsoft Docs
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
ms.assetid: 0623ad20-96cc-430e-bb36-35431a5d17ee
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 48097f4803aba02c19abbd0a1a48c7f9103545c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357663"
---
# <a name="business-rules-hello-world1-biztalk-server-sample"></a><span data-ttu-id="20b6f-102">业务规则 Hello World1 （BizTalk Server 示例）</span><span class="sxs-lookup"><span data-stu-id="20b6f-102">Business Rules Hello World1 (BizTalk Server Sample)</span></span>
<span data-ttu-id="20b6f-103">业务规则 Hello World1 示例演示如何创建 BizTalk 规则集，将其保存到文件 (SampleRuleSet.xml)、 加载它，并运行它基于示例事实集。</span><span class="sxs-lookup"><span data-stu-id="20b6f-103">The Business Rules Hello World1 sample demonstrates how to create a BizTalk rule set, save it to a file (SampleRuleSet.xml), load it, and run it based on a sample set of facts.</span></span> <span data-ttu-id="20b6f-104">本示例规则集包含涉及 XML 元素的简单规则和。基于网络的对象 （属性和成员） 作为规则定义中的条款。</span><span class="sxs-lookup"><span data-stu-id="20b6f-104">The sample rule set contains a simple rule that involves an XML element, and .NET-based objects (properties and members) as terms in rule definition.</span></span>  
  
## <a name="what-this-sample-does"></a><span data-ttu-id="20b6f-105">本示例的用途</span><span class="sxs-lookup"><span data-stu-id="20b6f-105">What This Sample Does</span></span>  
 <span data-ttu-id="20b6f-106">此示例将创建可执行文件执行以下步骤序列：</span><span class="sxs-lookup"><span data-stu-id="20b6f-106">This sample creates an executable that performs the following sequence of steps:</span></span>  
  
1.  <span data-ttu-id="20b6f-107">调用方法**CreateRuleset**生成描述的规则集的备注部分中。</span><span class="sxs-lookup"><span data-stu-id="20b6f-107">Calls the method **CreateRuleset** to build the rule set described in the Remarks section.</span></span>  
  
2.  <span data-ttu-id="20b6f-108">调用方法**SaveToFile**演示将规则设置为一个文件保存。</span><span class="sxs-lookup"><span data-stu-id="20b6f-108">Calls the method **SaveToFile** to demonstrate saving a rule set to a file.</span></span>  
  
3.  <span data-ttu-id="20b6f-109">调用方法**LoadFromFile**演示加载规则集从一个文件。</span><span class="sxs-lookup"><span data-stu-id="20b6f-109">Calls the method **LoadFromFile** to demonstrate loading a rule set from a file.</span></span>  
  
4.  <span data-ttu-id="20b6f-110">构造基于的示例事实运行规则集。</span><span class="sxs-lookup"><span data-stu-id="20b6f-110">Constructs sample facts against which to run the rule set.</span></span>  
  
5.  <span data-ttu-id="20b6f-111">运行规则集基于示例事实，生成屏幕输出。</span><span class="sxs-lookup"><span data-stu-id="20b6f-111">Runs the rule set against the sample facts, producing screen output.</span></span>  
  
6.  <span data-ttu-id="20b6f-112">暂停，以便您可以检查规则集文件 SampleRuleStore.xml。</span><span class="sxs-lookup"><span data-stu-id="20b6f-112">Pauses, enabling you to examine the rule set file SampleRuleStore.xml.</span></span>  
  
7.  <span data-ttu-id="20b6f-113">通过删除规则集文件中以备后续的示例运行清除。</span><span class="sxs-lookup"><span data-stu-id="20b6f-113">Cleans up by deleting the rule set file in preparation for subsequent runs of the sample.</span></span>  
  
## <a name="where-to-find-this-sample"></a><span data-ttu-id="20b6f-114">本示例所在的位置</span><span class="sxs-lookup"><span data-stu-id="20b6f-114">Where to Find This Sample</span></span>  
 <span data-ttu-id="20b6f-115">\<*示例路径*\>\Business Rules\Business 规则 Hello World1\\</span><span class="sxs-lookup"><span data-stu-id="20b6f-115">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\\</span></span>  
  
 <span data-ttu-id="20b6f-116">下表显示了本示例中的文件及其用途说明：</span><span class="sxs-lookup"><span data-stu-id="20b6f-116">The following table shows the files in this sample and describes their purpose.</span></span>  
  
|<span data-ttu-id="20b6f-117">文件</span><span class="sxs-lookup"><span data-stu-id="20b6f-117">File(s)</span></span>|<span data-ttu-id="20b6f-118">Description</span><span class="sxs-lookup"><span data-stu-id="20b6f-118">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="20b6f-119">App.ico、 AssemblyInfo.cs、 BusinessRulesHelloWorld1.csproj BusinessRulesHelloWorld1.sln</span><span class="sxs-lookup"><span data-stu-id="20b6f-119">App.ico, AssemblyInfo.cs, BusinessRulesHelloWorld1.csproj, BusinessRulesHelloWorld1.sln</span></span>|<span data-ttu-id="20b6f-120">项目、 解决方案和相关的文件，此示例中，创建、 保存、 部分加载和运行规则集。</span><span class="sxs-lookup"><span data-stu-id="20b6f-120">Project, solution, and related files for the portion of this sample that creates, saves, loads, and runs a rule set.</span></span>|  
|<span data-ttu-id="20b6f-121">HelloWorld1.cs</span><span class="sxs-lookup"><span data-stu-id="20b6f-121">HelloWorld1.cs</span></span>|<span data-ttu-id="20b6f-122">设置 visual C# 文件，包含方法，演示如何创建规则，将规则设置为一个文件，并加载规则集从文件保存。</span><span class="sxs-lookup"><span data-stu-id="20b6f-122">Visual C# file that contains methods to demonstrate creating a rule set, saving a rule set to a file, and loading a rule set from a file.</span></span> <span data-ttu-id="20b6f-123">此外包含调用这些方法，然后运行创建的规则集的外层代码。</span><span class="sxs-lookup"><span data-stu-id="20b6f-123">Also contains surrounding code that calls these methods and then runs the created rule set.</span></span>|  
|<span data-ttu-id="20b6f-124">Cleanup.bat</span><span class="sxs-lookup"><span data-stu-id="20b6f-124">Cleanup.bat</span></span>|<span data-ttu-id="20b6f-125">用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。</span><span class="sxs-lookup"><span data-stu-id="20b6f-125">Used to undeploy assemblies and remove them from the global assembly cache (GAC).</span></span> <span data-ttu-id="20b6f-126">删除发送和接收端口。</span><span class="sxs-lookup"><span data-stu-id="20b6f-126">Removes send and receive ports.</span></span> <span data-ttu-id="20b6f-127">根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。</span><span class="sxs-lookup"><span data-stu-id="20b6f-127">Removes Microsoft Internet Information Services (IIS) virtual directories as needed.</span></span>|  
|<span data-ttu-id="20b6f-128">SampleDocumentInstance.xml</span><span class="sxs-lookup"><span data-stu-id="20b6f-128">SampleDocumentInstance.xml</span></span>|<span data-ttu-id="20b6f-129">与文件 SampleSchema.xsd 中定义的架构一致的示例输入的文件。</span><span class="sxs-lookup"><span data-stu-id="20b6f-129">Sample input file that conforms to the schema defined in the file SampleSchema.xsd.</span></span>|  
|<span data-ttu-id="20b6f-130">SampleSchema.xsd</span><span class="sxs-lookup"><span data-stu-id="20b6f-130">SampleSchema.xsd</span></span>|<span data-ttu-id="20b6f-131">定义简单架构具有由 Visual C# 文件 HelloWorld1.cs 中创建的规则集引用的元素的架构文件。</span><span class="sxs-lookup"><span data-stu-id="20b6f-131">Schema file that defines a simple schema with an element referenced by the rule set created in the Visual C# file HelloWorld1.cs.</span></span>|  
|<span data-ttu-id="20b6f-132">Setup.bat</span><span class="sxs-lookup"><span data-stu-id="20b6f-132">Setup.bat</span></span>|<span data-ttu-id="20b6f-133">用于生成和初始化本示例。</span><span class="sxs-lookup"><span data-stu-id="20b6f-133">Used to build and initialize this sample.</span></span>|  
|<span data-ttu-id="20b6f-134">在 \MySampleLibrary 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="20b6f-134">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="20b6f-135">AssemblyInfo.cs、 MySampleLibrary.csproj、 MySampleLibrary.sln</span><span class="sxs-lookup"><span data-stu-id="20b6f-135">AssemblyInfo.cs, MySampleLibrary.csproj, MySampleLibrary.sln</span></span>|<span data-ttu-id="20b6f-136">项目、 解决方案和相关的文件，此示例中，提供了用于定义所创建的规则集引用的对象的类的部分。</span><span class="sxs-lookup"><span data-stu-id="20b6f-136">Project, solution, and related files for the portion of this sample that provides the class that defines the objects referenced by the created rule set.</span></span>|  
|<span data-ttu-id="20b6f-137">在 \MySampleLibrary 文件夹中：</span><span class="sxs-lookup"><span data-stu-id="20b6f-137">In the \MySampleLibrary folder:</span></span><br /><br /> <span data-ttu-id="20b6f-138">MySampleLibraryClass.cs</span><span class="sxs-lookup"><span data-stu-id="20b6f-138">MySampleLibraryClass.cs</span></span>|<span data-ttu-id="20b6f-139">Visual C# 包含文件中引用的属性**IF**一部分创建的规则，并可能在调用的方法**然后**一部分创建的规则。</span><span class="sxs-lookup"><span data-stu-id="20b6f-139">Visual C# file that contains the property referenced in the **IF** portion of the created rule, and the method that may be called in the **THEN** portion of the created rule.</span></span>|  
  
## <a name="building-and-initializing-this-sample"></a><span data-ttu-id="20b6f-140">生成并初始化此示例</span><span class="sxs-lookup"><span data-stu-id="20b6f-140">Building and Initializing This Sample</span></span>  
 <span data-ttu-id="20b6f-141">使用以下过程生成并初始化业务规则 Hello World1 示例。</span><span class="sxs-lookup"><span data-stu-id="20b6f-141">Use the following procedure to build and initialize the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-build-and-initialize-this-sample"></a><span data-ttu-id="20b6f-142">若要生成并初始化本示例</span><span class="sxs-lookup"><span data-stu-id="20b6f-142">To build and initialize this sample</span></span>  
  
1. <span data-ttu-id="20b6f-143">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="20b6f-143">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="20b6f-144">\<*示例路径*\>\Business Rules\Business 规则 Hello World1\\</span><span class="sxs-lookup"><span data-stu-id="20b6f-144">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\\</span></span>  
  
2. <span data-ttu-id="20b6f-145">运行文件 Setup.bat，以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="20b6f-145">Run the file Setup.bat, which performs the following actions:</span></span>  
  
   - <span data-ttu-id="20b6f-146">编译并部署 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。</span><span class="sxs-lookup"><span data-stu-id="20b6f-146">Compiles and deploys the Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] projects for this sample.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="20b6f-147">您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。</span><span class="sxs-lookup"><span data-stu-id="20b6f-147">You should confirm that [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] did not report any errors during the build and initialization process before attempting to run this sample.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="20b6f-148">如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。</span><span class="sxs-lookup"><span data-stu-id="20b6f-148">If you choose to open and build the projects in this sample without running the file Setup.bat, you must first create a strong name key pair using the .NET Framework Strong Name utility (sn.exe).</span></span> <span data-ttu-id="20b6f-149">使用此密钥对生成程序集进行签名。</span><span class="sxs-lookup"><span data-stu-id="20b6f-149">Use this key pair to sign the resulting assemblies.</span></span>  
   > 
   > [!NOTE]
   >  <span data-ttu-id="20b6f-150">若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="20b6f-150">To undo changes made by Setup.bat, run Cleanup.bat.</span></span> <span data-ttu-id="20b6f-151">必须运行 Setup.bat 前运行 Cleanup.bat 时间。</span><span class="sxs-lookup"><span data-stu-id="20b6f-151">You must run Cleanup.bat before running Setup.bat a second time.</span></span>  
  
## <a name="running-this-sample"></a><span data-ttu-id="20b6f-152">运行本示例</span><span class="sxs-lookup"><span data-stu-id="20b6f-152">Running This Sample</span></span>  
 <span data-ttu-id="20b6f-153">使用以下过程运行业务规则 Hello World1 示例。</span><span class="sxs-lookup"><span data-stu-id="20b6f-153">Use the following procedure to run the Business Rules Hello World1 sample.</span></span>  
  
#### <a name="to-run-this-sample"></a><span data-ttu-id="20b6f-154">运行本示例的步骤</span><span class="sxs-lookup"><span data-stu-id="20b6f-154">To run this sample</span></span>  
  
1. <span data-ttu-id="20b6f-155">在命令窗口中，导航到以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="20b6f-155">In a command window, navigate to the following folder:</span></span>  
  
    <span data-ttu-id="20b6f-156">\<*示例路径*\>\Business Rules\Business 规则 Hello world1\bin\debug \\</span><span class="sxs-lookup"><span data-stu-id="20b6f-156">\<*Samples Path*\>\Business Rules\Business Rules Hello World1\bin\Debug\\</span></span>  
  
2. <span data-ttu-id="20b6f-157">在命令窗口中，键入 (BusinessRulesHelloWorld1.exe)，此示例的可执行文件的名称，然后按 ENTER。</span><span class="sxs-lookup"><span data-stu-id="20b6f-157">In the command window, type the name of the executable file for this sample (BusinessRulesHelloWorld1.exe), and then press ENTER.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="20b6f-158">在运行时，此规则集文件 SampleRuleStore.xml 中的示例生成**bin\Debug**文件夹。</span><span class="sxs-lookup"><span data-stu-id="20b6f-158">While running, this sample produces the rule set file SampleRuleStore.xml in the **bin\Debug** folder.</span></span> <span data-ttu-id="20b6f-159">当可执行文件暂停时，等待您按 ENTER 以完成，你可以检查此文件的内容。</span><span class="sxs-lookup"><span data-stu-id="20b6f-159">When the executable pauses, waiting for you to press ENTER to finish, you can examine the contents of this file.</span></span> <span data-ttu-id="20b6f-160">请记得按任何键以完成之前请关闭它。</span><span class="sxs-lookup"><span data-stu-id="20b6f-160">Remember to close it before pressing any key to finish.</span></span> <span data-ttu-id="20b6f-161">否则，可执行文件可能不能删除以便为后续的示例运行做准备。</span><span class="sxs-lookup"><span data-stu-id="20b6f-161">Otherwise, the executable may not be able to delete it in preparation for subsequent runs of the sample.</span></span>  
  
   <span data-ttu-id="20b6f-162">如果在使用提供的示例输入文件 SampleDocumentInstance.xml，为定义的值为一 (1) 运行此示例基于创建的规则集的性质及其**ID**元素中，你将看到以下输出：</span><span class="sxs-lookup"><span data-stu-id="20b6f-162">Based on the nature of the created rule set, if you run this sample with the provided sample input file SampleDocumentInstance.xml, which has a value of one (1) defined for its **ID** element, you will see the following output:</span></span>  
  
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
>  <span data-ttu-id="20b6f-163">以粗体显示在前面的代码和在下面的代码，生成的输出的文件中定义的示例业务对象中所示的输出**MySampleLibrary**文件夹中，这由规则集引用。</span><span class="sxs-lookup"><span data-stu-id="20b6f-163">The output shown in bold, both in the preceding code and in the code that follows, is the output produced by the sample business object, defined by the files in the **MySampleLibrary** folder, which is referenced by the rule set.</span></span>  
  
 <span data-ttu-id="20b6f-164">如果更改与关联的值**ID**示例输入文件中的元素**SampleDocumentInstance.xml**从一 （1） 到两 （2），输出将发生变化，如下所示：</span><span class="sxs-lookup"><span data-stu-id="20b6f-164">If you change the value associated with the **ID** element in the sample input file **SampleDocumentInstance.xml** from one (1) to two (2), the output would change as follows:</span></span>  
  
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
  
 <span data-ttu-id="20b6f-165">您不会获得输出行的任何对象**MySampleBusinessObject**类具有其**MyValue**属性设置为匹配与关联的值（在构造）的值**ID**示例输入文件 SampleDocumentInstance.xml 中的元素。</span><span class="sxs-lookup"><span data-stu-id="20b6f-165">You will not get an output line for any objects of the **MySampleBusinessObject** class that have their **MyValue** property set to a value (during construction) that matches the value associated with the **ID** element in the sample input file SampleDocumentInstance.xml.</span></span>  
  
## <a name="comments"></a><span data-ttu-id="20b6f-166">注释</span><span class="sxs-lookup"><span data-stu-id="20b6f-166">Comments</span></span>  
 <span data-ttu-id="20b6f-167">内以编程方式创建的规则**createruleset （)** 方法所示：</span><span class="sxs-lookup"><span data-stu-id="20b6f-167">The rule created programmatically within the **CreateRuleset()** method shows:</span></span>  
  
 <span data-ttu-id="20b6f-168">**IF**</span><span class="sxs-lookup"><span data-stu-id="20b6f-168">**IF**</span></span>  
  
 <span data-ttu-id="20b6f-169">**MySampleBusinessObject.MyValue**与的值不相等**ID** XML 文档中的元素。</span><span class="sxs-lookup"><span data-stu-id="20b6f-169">**MySampleBusinessObject.MyValue** is not equal to the value of the **ID** element in the XML document.</span></span>  
  
 <span data-ttu-id="20b6f-170">**THEN**</span><span class="sxs-lookup"><span data-stu-id="20b6f-170">**THEN**</span></span>  
  
 <span data-ttu-id="20b6f-171">**MySampleBusinessObject.MySampleMethod(int)** 具有整型参数，硬编码为常量五 （5） 在这种情况下。</span><span class="sxs-lookup"><span data-stu-id="20b6f-171">**MySampleBusinessObject.MySampleMethod(int)** with an integer parameter, hard coded to the constant five (5) in this case.</span></span> <span data-ttu-id="20b6f-172">此方法生成开始的输出行**MySampleBusinessObject Class –-**。</span><span class="sxs-lookup"><span data-stu-id="20b6f-172">This method produces the output lines that begin **MySampleBusinessObject Class –-**.</span></span>  
  
 <span data-ttu-id="20b6f-173">此规则取决于以下因素：</span><span class="sxs-lookup"><span data-stu-id="20b6f-173">This rule depends on the following:</span></span>  
  
- <span data-ttu-id="20b6f-174">一个**MySampleBusinessObject**具有一个名为的公共属性类**MyValue**调用公共方法**MySampleMethod** （的采用一个整数参数）。</span><span class="sxs-lookup"><span data-stu-id="20b6f-174">A **MySampleBusinessObject** class with a public property called **MyValue** and a public method called **MySampleMethod** (that takes in an integer parameter).</span></span>  
  
- <span data-ttu-id="20b6f-175">定义 XML 文档包含的 XML 架构定义语言 (XSD) 架构**ID**元素。</span><span class="sxs-lookup"><span data-stu-id="20b6f-175">An XML schema definition language (XSD) schema that defines an XML document that contains an **ID** element.</span></span>  
  
  <span data-ttu-id="20b6f-176">定义规则，根据类和架构，但在执行期间，相关的类的对象实例和相关的架构的文档实例是必需的。</span><span class="sxs-lookup"><span data-stu-id="20b6f-176">You define rules in terms of classes and schemas, but during execution, object instances of the relevant classes and document instances of the relevant schemas are required.</span></span> <span data-ttu-id="20b6f-177">评估针对这些运行时实例 （称为事实） 的规则。</span><span class="sxs-lookup"><span data-stu-id="20b6f-177">You evaluate the rules against these run-time instances (known as facts).</span></span> <span data-ttu-id="20b6f-178">在此示例中，事实数据的多个实例**MySampleBusinessObject**构造替换为不同值的对象及其**MyValue**属性，并定义的架构的单个 XML 实例其中包含的值**ID**元素。</span><span class="sxs-lookup"><span data-stu-id="20b6f-178">In this sample, the facts are multiple instances of the **MySampleBusinessObject** object, constructed with different values for their **MyValue** property, and a single XML instance of the defined schema that contains a value for the **ID** element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20b6f-179">请参阅</span><span class="sxs-lookup"><span data-stu-id="20b6f-179">See Also</span></span>  
 [<span data-ttu-id="20b6f-180">业务规则（BizTalk Server 示例文件夹）</span><span class="sxs-lookup"><span data-stu-id="20b6f-180">Business Rules (BizTalk Server Samples Folder)</span></span>](../core/business-rules-biztalk-server-samples-folder.md)