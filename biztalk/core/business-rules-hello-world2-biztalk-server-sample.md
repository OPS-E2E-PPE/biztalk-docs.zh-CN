---
title: 业务规则 Hello World2 （BizTalk Server 示例） |Microsoft Docs
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
ms.assetid: 2a88a2a0-8cb6-4373-8441-0ab04345a477
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee732b2b1850b653426eab6a5ad55d52974df975
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357879"
---
# <a name="business-rules-hello-world2-biztalk-server-sample"></a>业务规则 Hello World2 （BizTalk Server 示例）
业务规则 Hello World2 示例扩展业务规则 Hello World1 示例，演示了如何为版本，发布和部署设置为共享的 SQL 规则存储，以及如何运行策略使用的 XML 规则**策略**对象由业务规则框架提供。 该示例还演示了在操作中的动态策略更新。  
  
> [!NOTE]
>  此示例假定，用户已安装的规则引擎更新服务和业务规则组件 （位于"其他软件"节点下） 在安装该产品的过程。  
  
> [!NOTE]
>  您使用**策略**要将规则引擎集成到任何独立的应用程序的对象。 **策略**对象是管理多个规则引擎实例的抽象，规则集检索消息并从共享 SQL 存储区，实例化和检索策略的更新并将其发布到托管应用程序。  
  
 有关规则集定义，且示例有关的基本信息事实构建的此示例中，请参阅[业务规则 Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md)。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例将创建可执行文件执行以下步骤序列：  
  
1.  调用方法**CreateRuleset**生成描述的规则集的备注部分中。  
  
2.  调用方法**SaveToFile**演示将规则设置为一个文件保存。  
  
3.  调用方法**LoadFromFile**演示加载规则集从一个文件。  
  
4.  将部署到共享 SQL 规则存储设置的规则。  
  
5.  运行规则集通过使用**策略**对象，并使用相同的业务规则 Hello World1 中使用示例事实集示例。  
  
6.  暂停，使您可以修改规则集文件**SampleRuleStore.xml**以特定方式。  
  
7.  运行规则集使用重新**策略**对象，现在已修改的规则集，并再次使用相同的业务规则 Hello World1 中使用示例事实集示例。  
  
8.  通过删除规则集文件和准备对后续运行的示例中的部署的规则集记录清理。  
  
> [!NOTE]
>  有关此 SDK 中的所有示例的重要信息，请参阅[示例](../core/samples-in-the-sdk.md)。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径\>* \Business Rules\Business 规则 Hello World2\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|App.ico、 AssemblyInfo.cs、 BusinessRulesHelloWorld2.csproj BusinessRulesHelloWorld2.sln|项目、 解决方案和相关的文件的一部分此示例中，创建、 保存、 加载、 部署和执行规则集。|  
|HelloWorld2.cs|Visual C# 文件： 包含方法，演示如何创建规则集、 保存到文件中，加载规则集，从文件设置的规则规则集部署到共享的 Microsoft SQL Server 规则存储，然后运行该规则使用设置的**策略**对象。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|SampleDocumentInstance.xml|与文件 SampleSchema.xsd 中定义的架构一致的示例输入的文件。|  
|SampleSchema.xsd|定义简单架构具有由 Visual C# 文件 Class1.cs 中创建的规则集引用的元素的架构文件。|  
|Setup.bat|用于生成和初始化本示例。|  
|在 \HelloWorld2Library 文件夹中：<br /><br /> AssemblyInfo.cs, HelloWorld2Library.csproj, HelloWorld2Library.sln|项目、 解决方案和相关的文件，此示例中，提供了用于定义所创建的规则集引用的对象的类的部分。|  
|在 \HelloWorld2Library 文件夹中：<br /><br /> HelloWorld2LibraryClass.cs|Visual C# 包含文件中引用的属性**IF**一部分创建的规则，并可能在调用的方法**然后**一部分创建的规则。|  
  
### <a name="to-build-and-initialize-the-business-rules-hello-world2-sample"></a>若要生成并初始化业务规则 Hello World2 示例  
  
1. 在命令窗口中，导航到以下文件夹：  
  
    *\<示例路径\>* \Business Rules\Business 规则 Hello World2\  
  
2. 运行文件 Setup.bat，以执行以下操作：  
  
   - 编译并部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。  
  
   > [!NOTE]
   >  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
   > 
   > [!NOTE]
   >  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对生成程序集进行签名。  
   > 
   > [!NOTE]
   >  若要撤消 Setup.bat 所做的更改，请运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  
  
### <a name="to-run-the-business-rules-hello-world2-sample"></a>若要运行业务规则 Hello World2 示例  
  
1.  在命令窗口中，导航到以下文件夹：  
  
     *\<Samples Path\>* \Business Rules\Business Rules Hello World2\bin\Debug\  
  
2.  在命令窗口中，键入此示例的文件的名称 (**BusinessRulesHelloWorld2.exe**)，然后按 ENTER。  
  
## <a name="hello-world2-output"></a>Hello World2 输出  
 根据创建的规则集的注释部分中描述的性质[业务规则 Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md)，如果在使用提供的示例输入文件 SampleDocumentInstance.xml，该定义的值为一 (1) 运行此示例为其**ID**元素中，你将看到以下输出：  
  
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
>  以粗体显示的输出是由文件中定义的示例业务对象生成的输出**HelloWorld2Library**文件夹的规则集的引用。 此时，应用程序将保持此状态中等待。  
  
 运行示例的下一部分涉及使用业务规则编辑器更改业务规则。  
  
#### <a name="to-use-the-business-rules-composer-to-change-the-business-rules"></a>若要使用业务规则编辑器更改业务规则  
  
1. 若要打开业务规则编辑器，请单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则编辑器**。  
  
   > [!NOTE]
   >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，并选择**以管理员身份运行**。  
  
2. 如果运行 SQL Server 的计算机上出现 SQL Server 对话框，单击**确定**连接到规则存储。  
  
3. 在**策略浏览器**下文**SampleRuleSet**节点，右键单击该节点**版本 1.0 – 已部署**，然后单击**复制**。  
  
4. 右键单击**SampleRuleSet**，然后单击**粘贴 （策略版本）**。  
  
5. 您可以更改规则条件和操作以满足你的需求。 有关此过程中，单击**rule1**中**版本 1.1 （未保存）**。 在右窗格中，右键单击**条件**，然后单击**添加逻辑非**。 添加**逻辑非**操作**不等于**谓词等效于使用**相等**谓词。  
  
6. 右键单击该节点**版本 1.1 （未保存）**，然后单击**保存**。 再次右键单击，然后依次**发布**。 右键单击第三次，然后单击**部署**。  
  
7. 在暂停的命令窗口中让您按任意键继续更新策略之后，按任意键。  
  
   从可执行文件 BusinessRulesHelloWorld2.exe 继续，如下所示的输出 （假设您可以通过添加逻辑非更改规则）：  
  
```  
Sleeping for 60 seconds (so that the deployed ruleset becomes effective) ...         
Grabbing the policy ...         
Executing the policy...         
MySampleBusinessObject Class -- MySampleMethod executed for object 1 with parameter 5         
The major version of the policy was: 1         
The minor version of the policy was: 1         
Press ENTER to continue after updating the policy...         
```  
  
 请注意输出如何变化：  
  
-   在方法中的输出行**MySampleMethod**仅打印的实例的一次现在**MySampleBusinessObject**为其类**MyValue**属性值等于 1而不是打印时的上一个规则**MyValue**属性不等于 1。  
  
-   该策略的次版本号现在为 1。  
  
## <a name="see-also"></a>请参阅  
 [业务规则（BizTalk Server 示例文件夹）](../core/business-rules-biztalk-server-samples-folder.md)