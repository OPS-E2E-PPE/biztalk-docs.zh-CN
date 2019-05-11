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
# <a name="business-rules-hello-world1-biztalk-server-sample"></a>业务规则 Hello World1 （BizTalk Server 示例）
业务规则 Hello World1 示例演示如何创建 BizTalk 规则集，将其保存到文件 (SampleRuleSet.xml)、 加载它，并运行它基于示例事实集。 本示例规则集包含涉及 XML 元素的简单规则和。基于网络的对象 （属性和成员） 作为规则定义中的条款。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例将创建可执行文件执行以下步骤序列：  
  
1.  调用方法**CreateRuleset**生成描述的规则集的备注部分中。  
  
2.  调用方法**SaveToFile**演示将规则设置为一个文件保存。  
  
3.  调用方法**LoadFromFile**演示加载规则集从一个文件。  
  
4.  构造基于的示例事实运行规则集。  
  
5.  运行规则集基于示例事实，生成屏幕输出。  
  
6.  暂停，以便您可以检查规则集文件 SampleRuleStore.xml。  
  
7.  通过删除规则集文件中以备后续的示例运行清除。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Business Rules\Business 规则 Hello World1\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|App.ico、 AssemblyInfo.cs、 BusinessRulesHelloWorld1.csproj BusinessRulesHelloWorld1.sln|项目、 解决方案和相关的文件，此示例中，创建、 保存、 部分加载和运行规则集。|  
|HelloWorld1.cs|设置 visual C# 文件，包含方法，演示如何创建规则，将规则设置为一个文件，并加载规则集从文件保存。 此外包含调用这些方法，然后运行创建的规则集的外层代码。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|SampleDocumentInstance.xml|与文件 SampleSchema.xsd 中定义的架构一致的示例输入的文件。|  
|SampleSchema.xsd|定义简单架构具有由 Visual C# 文件 HelloWorld1.cs 中创建的规则集引用的元素的架构文件。|  
|Setup.bat|用于生成和初始化本示例。|  
|在 \MySampleLibrary 文件夹中：<br /><br /> AssemblyInfo.cs、 MySampleLibrary.csproj、 MySampleLibrary.sln|项目、 解决方案和相关的文件，此示例中，提供了用于定义所创建的规则集引用的对象的类的部分。|  
|在 \MySampleLibrary 文件夹中：<br /><br /> MySampleLibraryClass.cs|Visual C# 包含文件中引用的属性**IF**一部分创建的规则，并可能在调用的方法**然后**一部分创建的规则。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 使用以下过程生成并初始化业务规则 Hello World1 示例。  
  
#### <a name="to-build-and-initialize-this-sample"></a>若要生成并初始化本示例  
  
1. 在命令窗口中，导航到以下文件夹：  
  
    \<*示例路径*\>\Business Rules\Business 规则 Hello World1\  
  
2. 运行文件 Setup.bat，以执行以下操作：  
  
   - 编译并部署 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。  
  
   > [!NOTE]
   >  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
   > 
   > [!NOTE]
   >  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。  
   > 
   > [!NOTE]
   >  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行业务规则 Hello World1 示例。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1. 在命令窗口中，导航到以下文件夹：  
  
    \<*示例路径*\>\Business Rules\Business 规则 Hello world1\bin\debug \  
  
2. 在命令窗口中，键入 (BusinessRulesHelloWorld1.exe)，此示例的可执行文件的名称，然后按 ENTER。  
  
   > [!NOTE]
   >  在运行时，此规则集文件 SampleRuleStore.xml 中的示例生成**bin\Debug**文件夹。 当可执行文件暂停时，等待您按 ENTER 以完成，你可以检查此文件的内容。 请记得按任何键以完成之前请关闭它。 否则，可执行文件可能不能删除以便为后续的示例运行做准备。  
  
   如果在使用提供的示例输入文件 SampleDocumentInstance.xml，为定义的值为一 (1) 运行此示例基于创建的规则集的性质及其**ID**元素中，你将看到以下输出：  
  
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
>  以粗体显示在前面的代码和在下面的代码，生成的输出的文件中定义的示例业务对象中所示的输出**MySampleLibrary**文件夹中，这由规则集引用。  
  
 如果更改与关联的值**ID**示例输入文件中的元素**SampleDocumentInstance.xml**从一 （1） 到两 （2），输出将发生变化，如下所示：  
  
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
  
 您不会获得输出行的任何对象**MySampleBusinessObject**类具有其**MyValue**属性设置为匹配与关联的值（在构造）的值**ID**示例输入文件 SampleDocumentInstance.xml 中的元素。  
  
## <a name="comments"></a>注释  
 内以编程方式创建的规则**createruleset （)** 方法所示：  
  
 **IF**  
  
 **MySampleBusinessObject.MyValue**与的值不相等**ID** XML 文档中的元素。  
  
 **THEN**  
  
 **MySampleBusinessObject.MySampleMethod(int)** 具有整型参数，硬编码为常量五 （5） 在这种情况下。 此方法生成开始的输出行**MySampleBusinessObject Class –-**。  
  
 此规则取决于以下因素：  
  
- 一个**MySampleBusinessObject**具有一个名为的公共属性类**MyValue**调用公共方法**MySampleMethod** （的采用一个整数参数）。  
  
- 定义 XML 文档包含的 XML 架构定义语言 (XSD) 架构**ID**元素。  
  
  定义规则，根据类和架构，但在执行期间，相关的类的对象实例和相关的架构的文档实例是必需的。 评估针对这些运行时实例 （称为事实） 的规则。 在此示例中，事实数据的多个实例**MySampleBusinessObject**构造替换为不同值的对象及其**MyValue**属性，并定义的架构的单个 XML 实例其中包含的值**ID**元素。  
  
## <a name="see-also"></a>请参阅  
 [业务规则（BizTalk Server 示例文件夹）](../core/business-rules-biztalk-server-samples-folder.md)