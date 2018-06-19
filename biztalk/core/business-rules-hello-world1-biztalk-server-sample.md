---
title: 业务规则 Hello World1 （BizTalk Server 示例） |Microsoft 文档
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
ms.openlocfilehash: ebe9f04fc8dac06676d7f29bf5dd2ecd01e7a06c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967667"
---
# <a name="business-rules-hello-world1-biztalk-server-sample"></a>业务规则 Hello World1 （BizTalk Server 示例）
“Business Rules Hello World1”示例演示如何创建一个 BizTalk 规则集，将它保存到文件 (SampleRuleSet.xml)、加载它并基于示例事实集运行它。 本示例规则集包含一个简单规则，该规则使用 XML 元素和基于 .NET 的对象（属性和成员）作为规则定义中的条件。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 该示例创建一个执行以下一系列步骤的可执行文件：  
  
1.  调用的方法**CreateRuleset**生成中的规则集描述备注部分。  
  
2.  调用的方法**SaveToFile**演示保存到文件设置的规则。  
  
3.  调用的方法**LoadFromFile**演示加载从文件设置的规则。  
  
4.  构造运行规则集时所基于的示例事实。  
  
5.  基于示例事实运行规则集，生成屏幕输出。  
  
6.  暂停，以便检查规则集文件 SampleRuleStore.xml。  
  
7.  通过删除规则集文件进行清除，以便为后续的示例运行做好准备。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Business Rules\Business 规则 Hello World1\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|App.ico、AssemblyInfo.cs、BusinessRulesHelloWorld1.csproj、BusinessRulesHelloWorld1.sln|本示例某部分的项目、解决方案和相关文件，该部分用于创建、保存、加载和运行规则集。|  
|HelloWorld1.cs|Visual C# 文件，包含用于演示创建规则集、将规则集保存到文件以及从文件加载规则集的方法， 此外，还包含调用这些方法然后运行所创建规则集的外层代码。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|SampleDocumentInstance.xml|与文件 SampleSchema.xsd 中定义的架构相符的示例输入文件。|  
|SampleSchema.xsd|定义简单架构的架构文件，该简单架构具有由 Visual C# 文件 HelloWorld1.cs 中创建的规则集引用的元素。|  
|Setup.bat|用于生成和初始化本示例。|  
|在 \MySampleLibrary 文件夹中：<br /><br /> AssemblyInfo.cs、MySampleLibrary.csproj、MySampleLibrary.sln|该示例某部分的项目、解决方案和相关文件，该部分提供定义由所创建规则集引用的对象的类。|  
|在 \MySampleLibrary 文件夹中：<br /><br /> MySampleLibraryClass.cs|Visual C# 文件包含在中引用的属性**如果**一部分创建的规则，并可能在调用的方法**然后**一部分创建的规则。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 使用以下过程可生成并初始化“Business Rules Hello World1”示例。  
  
#### <a name="to-build-and-initialize-this-sample"></a>构建和初始化此示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*\>\Business Rules\Business 规则 Hello World1\  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   编译和部署 Microsoft[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例的项目。  
  
    > [!NOTE]
    >  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
    > [!NOTE]
    >  如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。 使用该密钥对可以对生成的程序集签名。  
  
    > [!NOTE]
    >  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程可运行“Business Rules Hello World1”示例。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*\>\Business Rules\Business 规则 Hello World1\bin\Debug\  
  
2.  在命令窗口中，键入本示例的可执行文件名 (BusinessRulesHelloWorld2.exe)，然后按 Enter。  
  
    > [!NOTE]
    >  运行时，此规则集文件中的 SampleRuleStore.xml 的示例生成**bin\Debug**文件夹。 当可执行文件暂停以等待您按 Enter 以完成运行时，您可检查此文件的内容。 按任何键以完成操作之前，请务必关闭该文件。 否则，可执行文件可能无法删除该规则集文件以为后续的示例运行做好准备。  
  
 如果在使用提供的示例输入文件 SampleDocumentInstance.xml，为定义的值为一 (1) 运行此示例基于对创建的规则集的性质其**ID**元素，你将看到以下输出：  
  
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
>  加粗，同时在上面的代码并将在后面的代码，输出由生成定义中的文件的示例业务对象中所示的输出**MySampleLibrary**文件夹中，这由规则集引用。  
  
 如果更改与关联的值**ID**示例输入文件中的元素**SampleDocumentInstance.xml**从一个 （1） 到两 （2），输出将更改，如下所示：  
  
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
  
 将不会获取输出行的任何对象**MySampleBusinessObject**类具有其**MyValue**属性设置为与匹配与关联的值（在期间构造）的值**ID**示例输入文件 SampleDocumentInstance.xml 中的元素。  
  
## <a name="comments"></a>注释  
 以编程方式内创建的规则**CreateRuleset()** 方法所示：  
  
 **如果**  
  
 **MySampleBusinessObject.MyValue**是否不等于的值**ID** XML 文档中的元素。  
  
 **然后**  
  
 **MySampleBusinessObject.MySampleMethod(int)** 用整数参数，硬编码到常量五 （5） 在这种情况下。 此方法产生开头的输出行**MySampleBusinessObject 类 –-**。  
  
 此规则依赖于以下项：  
  
-   A **MySampleBusinessObject**具有公共属性调用类**MyValue**并调用一个公共方法**MySampleMethod** （采用一个整数参数）。  
  
-   定义 XML 文档包含 XML 架构定义语言 (XSD) 架构**ID**元素。  
  
 您可根据类和架构定义规则，但在执行过程中，必须使用相关类的对象实例和相关架构的文档实例。 您将针对这些运行时实例（称为事实）来评估规则。 在此示例中，事实数据的多个实例**MySampleBusinessObject**构造使用不同值的对象，其**MyValue**属性，并定义的架构的单个 XML 实例包含的值， **ID**元素。  
  
## <a name="see-also"></a>另请参阅  
 [业务规则（BizTalk Server 示例文件夹）](../core/business-rules-biztalk-server-samples-folder.md)