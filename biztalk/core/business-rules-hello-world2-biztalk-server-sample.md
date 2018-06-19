---
title: 业务规则 Hello World2 （BizTalk Server 示例） |Microsoft 文档
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
ms.openlocfilehash: eed1c0c83432417b53debcf523eeec91f85e5c2b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25967299"
---
# <a name="business-rules-hello-world2-biztalk-server-sample"></a>业务规则 Hello World2 （BizTalk Server 示例）
业务规则 Hello World2 示例扩展业务规则 Hello World1 示例，演示如何为版本，发布和部署 XML 规则设置为共享的 SQL 规则存储，以及如何运行策略使用**策略**对象框架提供的业务规则。 该示例还演示了操作中的动态策略更新。  
  
> [!NOTE]
>  该示例假设在安装产品过程中，用户已安装了规则引擎更新服务和业务规则组件（位于“其他软件”节点下）。  
  
> [!NOTE]
>  你使用**策略**要将规则引擎集成到任何独立的应用程序的对象。 **策略**对象是通过的多个规则管理引擎实例的抽象，规则集，将检索并从共享的 SQL 存储，实例化和将检索策略的更新并将其发布到宿主应用程序。  
  
 此示例中，通过构造的事实数据有关的规则集定义，和示例的基本信息请参阅[业务规则 Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md)。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 该示例创建一个执行以下一系列步骤的可执行文件：  
  
1.  调用的方法**CreateRuleset**生成中的规则集描述备注部分。  
  
2.  调用的方法**SaveToFile**演示保存到文件设置的规则。  
  
3.  调用的方法**LoadFromFile**演示加载从文件设置的规则。  
  
4.  将规则集部署到共享 SQL 规则存储。  
  
5.  运行的规则集使用**策略**对象，并通过使用相同的示例在业务规则 Hello World1 中使用的事实数据集示例。  
  
6.  暂停，使你能够修改规则设置文件**SampleRuleStore.xml**以特定方式。  
  
7.  运行的规则集再次使用**策略**对象，现在已修改的规则集，并再次使用相同的示例在业务规则 Hello World1 中使用的事实数据集示例。  
  
8.  通过删除规则集文件和部署的规则集记录进行清除，以便为后续的示例运行做准备。  
  
> [!NOTE]
>  有关在此 SDK 中的所有示例的重要信息，请参阅[示例](../core/samples-in-the-sdk.md)。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径\>* \Business Rules\Business 规则 Hello World2\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|App.ico、AssemblyInfo.cs、BusinessRulesHelloWorld2.csproj、BusinessRulesHelloWorld2.sln|该示例某部分的项目、解决方案和相关文件，该部分创建、保存、加载、部署和执行规则集。|  
|HelloWorld2.cs|Visual C# 文件都包含用于演示创建规则方法设置，保存到文件中，加载从文件中，设置的规则设置的规则部署规则设置为一个共享的 Microsoft SQL Server 规则存储，并且使用然后运行该规则设置**策略**对象。|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|SampleDocumentInstance.xml|与文件 SampleSchema.xsd 中定义的架构相符的示例输入文件。|  
|SampleSchema.xsd|定义简单架构的架构文件，该简单架构具有由 Visual C# 文件 Class1.cs 中创建的规则集引用的元素。|  
|Setup.bat|用于生成和初始化本示例。|  
|在 \HelloWorld2Library 文件夹中：<br /><br /> AssemblyInfo.cs、HelloWorld2Library.csproj、HelloWorld2Library.sln|该示例某部分的项目、解决方案和相关文件，该部分提供定义由所创建规则集引用的对象的类。|  
|在 \HelloWorld2Library 文件夹中：<br /><br /> HelloWorld2LibraryClass.cs|Visual C# 文件包含在中引用的属性**如果**一部分创建的规则，并可能在调用的方法**然后**一部分创建的规则。|  
  
### <a name="to-build-and-initialize-the-business-rules-hello-world2-sample"></a>生成并初始化业务规则 Hello World2 示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     *\<示例路径\>* \Business Rules\Business 规则 Hello World2\  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   编译并将部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例的项目。  
  
    > [!NOTE]
    >  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
    > [!NOTE]
    >  如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。 使用该密钥对可以对生成的程序集签名。  
  
    > [!NOTE]
    >  若要撤销 Setup.bat 所做的更改，请运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
### <a name="to-run-the-business-rules-hello-world2-sample"></a>运行业务规则 Hello World2 示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     *\<示例路径\>* \Business Rules\Business 规则 Hello World2\bin\Debug\  
  
2.  在命令窗口中，键入此示例的文件的名称 (**BusinessRulesHelloWorld2.exe**)，然后按 ENTER。  
  
## <a name="hello-world2-output"></a>Hello World2 输出  
 根据创建的规则集中的注释部分所述的特性[业务规则 Hello World1](../core/business-rules-hello-world1-biztalk-server-sample.md)，如果在使用提供的示例输入文件 SampleDocumentInstance.xml，定义的值为一 (1) 运行此示例有关其**ID**元素，你将看到以下输出：  
  
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
>  以粗体显示的输出是生成定义中的文件的示例业务对象的输出**HelloWorld2Library**规则集引用的文件夹。 此时，应用程序在此状态下等待。  
  
 运行示例的下一部分涉及使用业务规则编辑器更改业务规则。  
  
#### <a name="to-use-the-business-rules-composer-to-change-the-business-rules"></a>使用业务规则编辑器更改业务规则  
  
1.  若要打开业务规则编辑器，请单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**业务规则编辑器**。  
  
    > [!NOTE]
    >  在支持用户帐户控制 (UAC) 的系统上，可能需要具有管理权限才能运行该工具。 要执行此操作，右键单击该应用程序，，然后选择**以管理员身份运行**。  
  
2.  如果运行 SQL Server 的计算机上出现 SQL Server 对话框中，单击**确定**以连接到规则存储。  
  
3.  在**策略资源管理器**下面**SampleRuleSet**节点，右键单击该节点**版本 1.0 – 部署**，然后单击**复制**。  
  
4.  右键单击**SampleRuleSet**，然后单击**粘贴 （策略版本）**。  
  
5.  可以更改规则条件和操作以满足需求。 有关此过程中，单击**规则 1**中 **（不保存） 1.1 版**。 在右窗格中，右键单击**条件**，然后单击**添加不逻辑**。 添加**不逻辑**操作**不等于**以谓词相当于使用**相等**谓词。  
  
6.  右键单击该节点 **（不保存） 1.1 版**，然后单击**保存**。 再次右键单击，并依次**发布**。 右键单击第三次，然后单击**部署**。  
  
7.  更新策略之后，在暂停的命令窗口中将让您按任意键继续，请按任意键。  
  
 来自可执行文件 BusinessRulesHelloWorld2.exe 的输出（假设您通过添加逻辑非更改了规则）继续显示如下：  
  
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
  
-   在方法中的输出行**MySampleMethod**仅的实例的一次现在，打印**MySampleBusinessObject**为其类**MyValue**属性等于 1而不是打印时的上一个规则**MyValue**属性是否不等于 1。  
  
-   策略的次要版本号现在为 1。  
  
## <a name="see-also"></a>另请参阅  
 [业务规则（BizTalk Server 示例文件夹）](../core/business-rules-biztalk-server-samples-folder.md)