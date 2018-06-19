---
title: OperationsSamples （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3c9e3f3e-a570-4edd-aa2e-3f8e2e37c8a0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e42b17f19791eef9bd3f1b5d7d4554f61f08356
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2017
ms.locfileid: "26010246"
---
# <a name="operationssamples-biztalk-server-sample"></a>OperationsSamples（BizTalk Server 示例）
OperationsSamples 示例演示如何使用操作对象模型执行操作活动。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例演示下面几点：  
  
-   如何使用跟踪配置文件通过活动注释业务流程。  
  
-   如何使用 BAM 跟踪数据库查找活动 ID，然后使用此 ID 查找相关业务流程实例。  
  
-   如何查找和使用工作与消息流**MessageFlow**类和其他操作对象模型类和 Api。  
  
-   如何访问端口，消息，并通过使用类的其他实例源自**实例**类。  
  
 本示例包含大量有用的助手类和方法来支持上面的操作。 下一部分讨论了这些以及其他代码重点。  
  
## <a name="how-this-sample-is-designed-and-why"></a>此示例应如何以及为何  
 本示例旨在演示操作对象模型中的多个关键类和方法，并显示如何查询公用 BAM 跟踪数据库。  
  
 操作对象模型包含的类可提供处理 BizTalk Server 中的消息和其他实例的功能。  
  
### <a name="using-a-bam-activity-id"></a>使用 BAM 活动 ID  
 本示例显示通过使用业务数据如何与 BAM 交互，以及如何使用跟踪数据库中的公用视图在消息框中查找实时消息。 本示例通过检索与采购订单编号对应的业务流程 ID 来执行此操作。 为成功执行此任务，本示例必须执行下列操作：  
  
1.  使用业务数据（采购订单编号）查找活动 ID。 该步骤将业务数据映射到可以用于查找其他信息的内部 ID。  
  
2.  检索与活动 ID 相关的 BAM 引用。  
  
3.  查找引用业务流程的揃“BizTalkService”类型的引用。 如果找到，则返回其实例 ID。  
  
 此功能由**BAMWebService.GetOrchestrationID**静态方法和关联的帮助器方法包括 BamManagementService.cs 源文件中的类和方法。  
  
### <a name="suspending-terminating-and-resuming-an-instance"></a>挂起、终止和恢复实例  
 示例程序包含**Samples.OperateOnInstance**使用操作和实例 ID，并执行指定的操作的实例上的方法。 有效的操作由定义**InstanceOperation**枚举并包含挂起、 终止和恢复。 这些操作直接映射到 BizTalkOperations 类的方法-**SuspendInstance**， **TerminateInstance**，和**ResumeInstance**。  
  
 请注意，此方法可处理 ArgumentException 和 SqlException 异常。 处理操作对象模型中的类和方法时必须谨慎预测异常（包括 SqlException）。  
  
> [!NOTE]
>  许多操作方法都需要对数据库的访问权限。 应预测这些方法引发的异常，并进行相应处理。  
  
### <a name="retrieving-all-live-messages"></a>检索所有实时消息  
 使用操作对象模型迭代所有可用实时消息非常简单，如以下代码段所示：  
  
```  
BizTalkOperations _operations = new BizTalkOperations()  
IEnumerable messages = _operations.GetMessages();  
foreach (BizTalkMessage msg in messages)  
…  
```  
  
 OperationsSamples 程序进一步演示如何访问每个消息的相关信息，包括消息 ID、消息类型以及消息部分的数目和类型。 你可以修改此代码，并将其用于必须在 BizTalk Server 中循环访问大多数或所有可用实时消息的情况。  
  
> [!NOTE]
>  可能有成百上千个可用消息。 扫描整个列表可能会对性能产生负面影响。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下 SDK 位置中：  
  
 \<*示例路径*\>\Admin\OperationsOM\OperationsSamples\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|BamManagementService.cs|BAM Web Services 的 Web 代理类。|  
|Cleanup.bat|删除示例业务流程，并将 HelloWorld 示例还原为其原始状态。|  
|HelloOrchestration.btt|用于将 BizTalk 事件源映射到 BAM 目标活动的跟踪配置文件。|  
|HelloOrchestration.xls|BAM 定义样式表。|  
|OperationsSamples.cs|包含演示操作对象模型的各个方面的代码的 C# 源文件。|  
|OperationsSamples.csproj、OperationsSamples.sln 和 AssemblyInfo.cs|本示例的项目、解决方案和程序集信息文件。|  
|Setup.bat|用于通过修改 HelloWorld 业务流程示例来生成和初始化本示例。 该文件将安装示例业务流程、部署 BAM 活动定义和跟踪配置文件编辑器文件、配置端口并将示例文件放置到接收位置中。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 使用本示例可以浏览可在操作对象模型中使用的功能。 修改现有例程以查找消息，并以不同方式处理消息，或者添加复制 BizTalk Server 管理控制台中的部分组中心的新代码。  
  
 你也可以考虑下面一些任务：  
  
-   编写用于将组中心页的最常用子集复制到自定义应用程序的应用程序。  
  
-   编写用于创建端口并为新贸易合作伙伴发送测试消息的自定义快速部署应用程序。  
  
-   将示例程序修改为向屏幕、XML 文件或文本报告提供单个或一系列采购订单的相关信息的命令行实用工具。  
  
## <a name="installing-sample-support-files"></a>安装示例支持文件  
 本部分可引导你完成安装和运行本示例所需的过程。  
  
> [!NOTE]
>  在安装和运行本示例之前，必须验证是否已安装并且正在运行 BAM。 如果尚未安装 BAM，本示例将不会运行。  
  
#### <a name="to-compile-and-install-the-support-files-for-this-sample"></a>编译和安装本示例的支持文件  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
2.  运行 Setup.bat，该文件将执行以下操作：  
  
    -   创建发送目录和接收目录。  
  
    -   创建并启动发送端口和接收端口  
  
    -   编译和部署 `<Samples Path>` \Orchestrations\HelloWorld 文件夹中的 HelloWorld 业务流程。  
  
    -   修改 HelloWorld 业务流程的公钥标记  
  
    -   部署 BAM 活动定义和跟踪配置文件编辑器文件  
  
    -   重命名输出目录  
  
    > [!NOTE]
    >  若要中止安装，请在第一个“按任意键继续”提示下按 Ctrl+C。 此操作将停止脚本，并将 HelloWorld 示例保留在其原始状态。 在第二个和最终提示下按 Ctrl+C 不会停止安装。 在这种情况下，请运行 Cleanup.bat 卸载 OperationsOM 示例并还原 HelloWorld 示例。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 OperationsOM 示例。  
  
#### <a name="to-compile-and-run-the-sample"></a>编译并运行本示例  
  
1.  单击**启动**，选择**所有程序**，选择**Microsoft BizTalk Server**，然后选择**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**托管实例**。  
  
3.  右键单击**BizTalkServerApplication**，然后单击**重新启动**。  
  
    > [!NOTE]
    >  如果自从配置产品以来尚未重新启动 BizTalkServerApplication 主机实例，可能需要重新启动此主机实例以便为 BAM 设置正确的工作数据库。  
  
4.  从 Windows 资源管理器，导航到以下文件夹：  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
5.  双击**OperationsOM.sln**要加载到 Visual Studio 中的项目文件。  
  
6.  按 F5 键运行本示例。  
  
     -或者-  
  
     上**生成**菜单上，单击**重新生成解决方案**。 生成完成后，使用 Windows 资源管理器导航到`<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,`然后双击**OperationsSamples.exe**。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>本示例中使用的类或方法  
 [Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx)&#124;[Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx)&#124;[Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124;[Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx)&#124;[Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx)&#124;[Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx)&#124;[Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)  
  
## <a name="see-also"></a>另请参阅  
 [Admin-OperationsOM（BizTalk Server 示例文件夹）](../core/admin-operationsom-biztalk-server-samples-folder.md)