---
title: OperationsSamples （BizTalk Server 示例） |Microsoft Docs
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
ms.openlocfilehash: 5101e047c41e12f322639986179b4b87504da75f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65262936"
---
# <a name="operationssamples-biztalk-server-sample"></a>OperationsSamples （BizTalk Server 示例）
OperationsSamples 示例演示如何使用操作对象模型执行操作活动。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 此示例将演示如下：  
  
- 如何使用跟踪配置文件注释与活动的业务流程。  
  
- 如何使用 BAM 跟踪数据库查找活动 ID，然后使用该 ID 来查找相关业务流程实例。  
  
- 如何查找和处理消息流通过使用**MessageFlow**类和其他操作对象模型类和 Api。  
  
- 如何访问端口、 消息和其他实例使用的类派生自**实例**类。  
  
  该示例包含很多有用的帮助器类和方法以支持更高版本的操作。 下一节中讨论这些和其他代码重点。  
  
## <a name="how-this-sample-is-designed-and-why"></a>此示例设计方式和原因  
 本示例旨在演示的几个关键类和操作对象模型中的方法并显示如何查询公用 BAM 跟踪数据库。  
  
 操作对象模型包含提供的功能来处理消息和 BizTalk Server 中的其他实例的类。  
  
### <a name="using-a-bam-activity-id"></a>使用 BAM 活动 ID  
 此示例演示如何与 BAM 交互以及如何使用跟踪数据库中的公用视图通过使用业务数据在消息框中查找实时消息。 此示例通过检索与采购订单号相对应的业务流程 ID 来执行此操作。 若要成功执行此任务，必须执行以下操作：  
  
1. 使用业务数据 （采购订单编号） 查找活动 id。 此步骤将业务数据映射到可用于查找其他信息的内部 ID。  
  
2. 检索活动 id。 与相关的 BAM 引用。  
  
3. 找到的揃"BizTalkService"类型，而是指业务流程的引用。 如果找到一个对象，返回其实例 id。  
  
   提供此功能**BAMWebService.GetOrchestrationID**静态方法和关联的帮助程序方法包括 BamManagementService.cs 源文件中的类和方法。  
  
### <a name="suspending-terminating-and-resuming-an-instance"></a>挂起、 终止和恢复实例  
 示例程序包含**Samples.OperateOnInstance**操作和实例 ID，并执行指定的操作的实例上的方法。 由定义有效的操作**InstanceOperation**枚举并包括挂起、 终止和恢复。 这些操作直接映射到 BizTalkOperations 类的方法 —**: SuspendInstance**， **TerminateInstance**，并**ResumeInstance**。  
  
 请注意，该方法处理 ArgumentException 和 SqlException 异常。 您必须谨慎预测异常 — 包括 SqlException — 时使用的类和操作对象模型中的方法。  
  
> [!NOTE]
>  很多的操作方法需要对数据库的访问。 应预测这些方法引发的异常并进行相应处理。  
  
### <a name="retrieving-all-live-messages"></a>检索所有实时消息  
 操作对象模型可以直观地循环访问所有可用实时消息，如下面的代码段中所示可以：  
  
```  
BizTalkOperations _operations = new BizTalkOperations()  
IEnumerable messages = _operations.GetMessages();  
foreach (BizTalkMessage msg in messages)  
…  
```  
  
 OperationsSamples 程序采用这一步演示了如何访问有关每个消息，包括消息 ID、 消息类型以及数量和类型的消息部分的信息。 您可以修改此代码，并使用它在方案中需要循环访问大多数或所有可用实时消息在 BizTalk Server 中。  
  
> [!NOTE]
>  可能有数百或数千个消息可用。 扫描整个列表可能会影响性能。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 本示例位于以下 SDK 位置中：  
  
 \<*Samples Path*\>\Admin\OperationsOM\OperationsSamples\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|BamManagementService.cs|BAM Web 服务的 web 代理类。|  
|Cleanup.bat|删除示例业务流程，并将 HelloWorld 示例还原到其原始状态。|  
|HelloOrchestration.btt|跟踪配置文件用于将 BizTalk 事件源映射到 BAM 目标活动。|  
|HelloOrchestration.xls|BAM 定义样式表。|  
|OperationsSamples.cs|C#包含演示操作对象模型的各个方面的代码的源文件。|  
|OperationsSamples.csproj、 operationssamples.sln 和 AssemblyInfo.cs|此示例的项目、 解决方案和程序集信息文件。|  
|Setup.bat|用于生成和初始化本示例通过修改 HelloWorld 业务流程示例。 它安装示例业务流程，将部署 BAM 活动定义和跟踪配置文件编辑器文件、 配置端口，并将示例文件放入接收位置。|  
  
## <a name="how-to-use-this-sample"></a>如何使用此示例  
 此示例用于浏览操作对象模型中可用的功能。 修改现有例程以查找并以不同方式处理消息，或添加复制 BizTalk Server 管理控制台中的组中心的某些部分的新代码。  
  
 您也可以考虑的一些以下任务：  
  
-   编写的应用程序复制到自定义应用程序的组中心最常用的子集。  
  
-   编写自定义的预配应用程序创建端口并为新贸易合作伙伴发送测试消息。  
  
-   将示例程序修改为提供有关单个采购订单或一系列屏幕、 XML 文件或文本报告到的采购订单信息的命令行实用工具。  
  
## <a name="installing-sample-support-files"></a>安装示例支持文件  
 本部分将指导完成安装和运行示例所需的过程。  
  
> [!NOTE]
>  在安装和运行此示例之前, 必须验证 BAM 已安装并且正常工作。 如果尚未安装 BAM，本示例不起作用。  
  
#### <a name="to-compile-and-install-the-support-files-for-this-sample"></a>若要编译并安装此示例的支持文件  
  
1.  在命令窗口中，导航到以下文件夹：  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
2.  运行 Setup.bat，将执行以下操作：  
  
    -   创建发送端口和接收目录  
  
    -   创建并启动发送端口和接收端口  
  
    -   编译并部署中的 HelloWorld 业务流程`<Samples Path>`\Orchestrations\HelloWorld 文件夹。  
  
    -   修改 HelloWorld 业务流程的公钥标记  
  
    -   部署 BAM 活动定义和跟踪配置文件编辑器文件  
  
    -   重命名输出目录  
  
    > [!NOTE]
    >  若要中止安装，请在第一个"按任意键继续"提示符处按 CTRL + C。 这会停止该脚本并将 HelloWorld 示例保留在其原始状态。 在第二个和最后一个提示符处按 CTRL + C 不会停止安装。 在这种情况下，运行 Cleanup.bat 卸载 OperationsOM 示例并还原 HelloWorld 示例。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行 OperationsOM 示例。  
  
#### <a name="to-compile-and-run-the-sample"></a>若要编译并运行示例  
  
1.  单击**启动**，选择**所有程序**，选择**Microsoft BizTalk Server**，然后选择**BizTalk Server 管理**。  
  
2.  在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**平台设置**，然后展开**主机实例**。  
  
3.  右键单击**BizTalkServerApplication**，然后单击**重新启动**。  
  
    > [!NOTE]
    >  重新启动 BizTalkServerApplication 主机实例可能有必要; 如果不重新启动主机实例配置产品以来，则为 BAM 设置正确的工作数据库。  
  
4.  从 Windows 资源管理器，导航到以下文件夹：  
  
     `<Samples Path>\Admin\OperationsOM\OperationSamples`  
  
5.  双击**OperationsOM.sln**要加载到 Visual Studio 项目文件。  
  
6.  按 F5 以运行示例。  
  
     -- OR --  
  
     上**构建**菜单上，单击**重新生成解决方案**。 生成完成后，使用 Windows 资源管理器导航到`<Samples Path>\Admin\OperationsOM\OperationSamples\bin\Debug,`，然后双击**OperationsSamples.exe**。  
  
## <a name="classes-or-methods-used-in-this-sample"></a>类或方法在此示例中使用  
 [Microsoft.BizTalk.Operations.BizTalkOperations](http://msdn.microsoft.com/library/microsoft.biztalk.operations.biztalkoperations.aspx) &#124; [Microsoft.BizTalk.Operations.MessageFlow](http://msdn.microsoft.com/library/microsoft.biztalk.operations.messageflow.aspx) &#124; [Microsoft.BizTalk.Operations.SendPortInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.sendportinstance.aspx)&#124; [Microsoft.BizTalk.Operations.RoutingFailureInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.routingfailureinstance.aspx) &#124; [Microsoft.BizTalk.Operations.OrchestrationInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.orchestrationinstance.aspx) &#124; [Microsoft.BizTalk.Operations.MSMQtInstance](http://msdn.microsoft.com/library/microsoft.biztalk.operations.msmqtinstance.aspx) &#124; [Microsoft.BizTalk.Operations.TrackedServiceInstance](http://msdn.microsoft.com/library/Microsoft.BizTalk.Operations.TrackedServiceInstance.aspx)  
  
## <a name="see-also"></a>请参阅  
 [Admin-OperationsOM（BizTalk Server 示例文件夹）](../core/admin-operationsom-biztalk-server-samples-folder.md)