---
title: 注意事项和已知的问题的 TPE |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Tracking Profile Editor, known issues
- planning, Tracking Profile Editor
- Tracking Profile Editor, planning
ms.assetid: e96d85e0-e9ae-434a-b54e-5950f4a2b9c6
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 41f728126f14193ad8fc584a94574dab61f7140f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996870"
---
# <a name="considerations-and-known-issues-for-tpe"></a>注意事项和 TPE 的已知的问题
使用跟踪配置文件和 TPE 时，应注意以下问题。  
  
## <a name="naming-folders-in-the-tpe"></a>在 TPE 中命名文件夹  
 在跟踪配置文件编辑器中命名文件夹时，请注意以下命名要求：  
  
-   文件夹名和数据项实例值的组合的长度不得超过 128 个字符。  
  
-   对于 Continuation 和 ContinuationID 文件夹，文件夹的命名是将两个业务流程相关联的关键。 例如，业务流程 A 是业务流程 B 的父级，业务流程 A 包含一个 Continuation 文件夹，该文件夹的名称直接映射到业务流程 B 中的 ContinuationID 文件夹。  
  
## <a name="developing-orchestrations-for-the-tpe"></a>开发 TPE 的业务流程  
 如果某个业务流程的开始和结束形状无效，则您无法将该业务流程映射到业务活动。 业务流程引擎不允许跟踪某些形状。 它们分别是：  
  
- 消息赋值  
  
- 转换  
  
- 组（任务）  
  
- 挂起  
  
- 循环 (While)  
  
- Branch  
  
- Terminate  
  
- 引发  
  
- 捕获  
  
- 循环形状  
  
  当映射到业务活动时，请按照以下准则执行操作，以便跟踪配置文件编辑器和其他 BAM 工具可以使用它们：  
  
- 对于组形状，请使用非事务性作用域形状。  
  
- 对于循环形状，请将它包装到非事务性作用域形状中。  
  
- 对于终止形状，没有任何解决办法，因为在正常情况下，此形状的结束事件从不发生。  
  
- 在计划的开始或结束时，不要使用不允许执行拖放操作的任何形状。  
  
## <a name="applying-tracking-profiles-that-monitor-running-processes"></a>应用监视运行的进程的跟踪配置文件  
 如果活动中包含 BAM 继续符，则更新跟踪配置文件可能会影响正在进行的活动实例。 具体而言，如果在更新跟踪配置文件时指定在下游对已记录的某个活动项进行数据侦听，则原始值可能会被覆盖。 从本质而言，任何单个事件流将不会受跟踪配置文件更新的应用程序的影响，因为每个流对象是与活动/流开始时处于就绪状态的特定版本的配置文件相联系。 但是，使用继续符就意味着将多个事件流相关联，在更新配置文件时还尚未开始的流将提取更新中所做的更改，从而导致上述可能出现的覆盖数据的情况。 有关继续符的详细信息，请参阅[活动继续符](../core/activity-continuation.md)并[如何创建一个继续符](../core/how-to-create-a-continuation.md)。  
  
## <a name="tracking-profiles-without-a-send-or-receive-shape-from-which-to-draw-message-properties"></a>不具有从中提取消息属性的发送形状或接收形状的跟踪配置文件  
 继续符通过在多个活动中具有相同值的上下文属性或负载数据来跟踪活动。 有些属性在各个活动中的值是不同的，例如消息 ID、服务 ID 和实例 ID。  
  
 您可以使用以下方法创建跟踪配置文件来处理此情况：  
  
-   如果业务流程通过动态绑定向另一个业务流程发送消息，则继续符可以使用全局唯一负载数据。  
  
-   如果消息中没有任何唯一负载数据，则可以使用消息的交换 ID。 要使用交换 ID，您必须在同一接收形状上跟踪它。 如果您创建了新消息，则无法使用交换 ID，因为创建新消息时，交换 ID 即发生了更改。 从接收形状或发送形状之外的任何形状跟踪交换 ID 都是不可靠的。  
  
-   只要业务流程中使用的是从管道接收的消息（也就是说，业务流程端口绑定到一个管道，且从该位置跟踪接收形状和消息 ID），则您也可以使用消息 ID。 如果您从其他形状跟踪消息 ID，则将无法在继续符中使用消息 ID。  
  
-   如果业务流程调用另一个业务流程和未传递任何消息，或业务流程调用另一个业务流程，但被调用方不具有任何构造、 接收或发送形状，可以检索负载数据值，则用户可以使用实例 id。 调用的业务流程的实例 ID 不会更改。  
  
-   如果业务流程通过执行调用来加载另一个业务流程，而没有直接调用它，则无法使用任何静态消息属性来跟踪活动。 用户无法启用继续符。 在这种情况下，只有当消息通过包含对其执行跟踪的唯一负载数据的管道来传递时，才能执行跟踪。  
  
## <a name="you-cannot-use-a-session-id-as-a-continuation-token-for-pass-through-pipelines"></a>您无法将会话 ID 用作直通管道的继续符  
 在跟踪配置文件中，当您从某个消息负载中选择项时，跟踪配置文件将绑定到该消息的架构。 在直通管道中，架构名称值是空值。 当 BAM 尝试按端口名和架构名来加载配置时，它将找不到与会话 ID 架构相匹配的项，而且引擎将不跟踪任何数据。  
  
 对于直通管道，您可以从跟踪配置文件中删除所有负载跟踪；或者，如果您确实需要跟踪负载数据，则可以使用 XML 管道。  
  
## <a name="using-unique-port-names"></a>使用唯一端口名  
 当枚举双向端口时，TPE 将它们显示为两个逻辑端口，即一个发送端口和一个接收端口。 两个逻辑端口的显示名称相同。 您可以使用 BizTalk Server 创建具有相同名称的单向端口和双向端口。 例如，您可以创建一个名为“Port1”的双向端口，然后创建一个具有相同名称的接收端口。 在这些情况下，TPE 显示接收端口一次，显示双向端口两次，一次显示为接收端口，一次显示为发送端口。  
  
 在这种情况下，TPE 将对两个接收端口都应用跟踪配置文件。 我们建议为端口指定唯一名称，以帮助正确标识它们。  
  
## <a name="using-tpe-orchestrations-with-a-parallel-shape-as-the-first-shape"></a>使用第一个形状为并行形状的 TPE 业务流程  
 如果业务流程以分叉、并行或侦听形状开始，则您将无法在其中一个分支上映射活动 ID。 在并行处理的情况下，您可以在分叉形状上映射 ActivityID。 您也可以让 BAM 生成活动 ID，以避免并行形状出现在业务流程的顶部。  
  
> [!IMPORTANT]
>  如果将一个活动映射到多个路径，且将 ActivityID 映射到分叉形状的一个路径，则当沿着未映射 ActivityID 的路径进行处理时，将导致错误。  
  
## <a name="availability-of-message-properties-at-design-time"></a>消息属性在设计时的可用性  
 创建跟踪配置文件时，并非所有消息属性都是可用的。 当从其映射消息属性的形状位于业务流程顶部时，最有可能遇到这个问题。 在这些情况下，消息属性的值为空。  
  
 例如，当侦听形状是业务流程中的第一个形状。 当消息属性被映射中的此形状，仅以下属性具有值： InstanceID、 ServiceID 和 ServiceClassID。 （此时，消息 ID 不在作用域中，它具有空值。）  
  
## <a name="you-cannot-map-shapes-inside-a-loop-shape-to-report-a-milestone"></a>您无法映射循环形状内部的形状来报告里程碑  
 TPE 将阻止从循环形状中包含的源映射到循环外的项的活动。  
  
 循环活动是指在业务流程内循环（即重复）的操作。 可以从在业务流程内循环的操作中捕获事件。 为此，需要创建另一个活动，并映射该循环内的所有新活动里程碑和数据。 这样做是有必要的，因为在循环中数据处理在每次计划的执行中将发生多次。  
  
 例如，如果您有包含在循环中处理的多个行项的采购订单，问题，如"哪些采购订单的货物价格为 $100？" 是不明确。 下面的问题则含义明确：  
  
 哪些采购订单包含价格为 $100 的货物行？  
  
 哪些采购订单的货物的总计/最小/最大价格为 $100？  
  
 要提出含义明确的问题，则需要将货物行同采购订单分开考虑。 在跟踪配置文件编辑器中，根活动（例如，采购订单）映射到循环外的所有操作。 子活动（例如，货物行）映射到循环内的操作。  
  
 使用这些类型的构造的通常方法是分解重复的循环，然后使相关活动基于与外部活动相关的内部活动。  
  
 您需要将一个负载项用作根活动的活动 ID，并使此负载项在循环内的某些消息中可用。 还需要将该活动映射到子活动下的关系节点，并将它命名为根活动。  
  
## <a name="tracking-profiles-spanning-multiple-applications"></a>跨多个应用程序的跟踪配置文件  
 如果跟踪配置文件横跨多个应用程序，则必须在解决方案中的所有应用程序均部署完毕后再部署该跟踪配置文件。 如果跟踪配置文件不是部署的最后一项，将收到以下消息"**找不到映射源。**"，在部署向导调用 BTTDeploy.exe 时。  
  
## <a name="mapping-multiple-biztalk-server-artifacts-to-a-document-reference-url-or-messageid-nodes"></a>将多个 BizTalk Server 项目映射到一个文档引用 URL 或消息 ID 节点  
 您可以使用 TPE 将多个 BizTalk Server 项目拖放到同一文档引用 URL 或消息 ID 节点。  
  
 在多个源映射到 BAM 活动中的同一个项时，在 BAM 处理过程中遇到的最后一个项目为跟踪数据中保留的项目，并可以在 BAM 门户中进行查看。  
  
## <a name="updating-btt-versions-to-match-biztalk-solution-versions"></a>更新 BTT 版本以与 BizTalk 解决方案版本相匹配  
 通过将 BTT 文件的更新自动化，BAM 开发人员和管理员可以保持跟踪配置文件与 BizTalk 解决方案之间的版本同步。 若要执行此操作，修改**版本**属性中**DataLevel** BTT 文件的元素。 在下面的元素示例中，您将修改 TargetAssemblyName 和 SchemaName 属性中的版本信息。  
  
```  
<DataLevel Name="City" SourceTypeSelected="Messaging Payload" TargetAssemblyName="TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SchemaName="TheImplementationOfOrderMgmt.PurchaseOrder,TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SomXPath="/*[local-name()='<Schema>' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" XPath="/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" IsBeginActivity="true" IsEndActivity="false">  
```  
  
## <a name="some-orchestration-shapes-cannot-be-tracked-in-the-tpe"></a>在 TPE 中无法跟踪某些业务流程形状  
 业务流程引擎不生成以下形状的事件，因此无法在 TPE 中跟踪或映射这些形状：  
  
-   任务  
  
-   全部分支  
  
-   挂起  
  
-   Terminate  
  
-   引发  
  
-   捕获  
  
-   消息赋值（因为它是构造形状的一部分）  
  
-   转换（因为它是构造形状的一部分）  
  
-   循环  
  
## <a name="tpe-not-retrieving-deployed-tracking-profiles"></a>TPE 不检索已部署的跟踪配置文件  
 在升级或重新部署之后，您可能会在检索已部署的跟踪配置文件时遇到困难。 这可能是因为 BizTalkMgmtDb 数据库所在服务器的名称在注册表中的存储方式不匹配。  
  
 BizTalkMgmtDb 在组配置期间写入注册表。 TPE 使用此注册表项查找主导入数据库和筛选跟踪配置文件。  
  
 在配置期间，可以用多种格式输入服务器名称。 例如：  
  
- mgmtsvr1316267,15001\inst  
  
- MGMTSVR1316267\inst,15001  
  
  TPE 在使用注册表项时会执行简单的字符串比较。 若要检索已部署的跟踪配置文件是检查存储的服务器和数据库名称和输入在 TPE 中所需**设置管理数据库**对话框。  
  
#### <a name="to-determine-the-syntax-for-server-and-database-names-and-enter-it-in-the-biztalk-management-database"></a>确定服务器和数据库名称的语法，并将其输入到 BizTalk 管理数据库中。  
  
1. 打开[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]**自定义配置管理器**。 有关使用信息**自定义配置管理器**，请参阅[配置 BizTalk Server](../install-and-config-guides/configure-biztalk-server.md)。  
  
2. 在导航窗格中，选择**组**打开组配置页。  
  
3. 在中**数据存储**网格中，观察到的格式**服务器名称**并**数据库名称**。  
  
4. 打开 TPE，然后选择**工具**菜单项。  
  
5. 选择**设置管理数据库**菜单项以打开**设置管理数据库**对话框。  
  
6. 中**SQL Server**文字框中，输入中使用的服务器名称**服务器名称**字段**数据存储**gridon**自定义配置管理器**组页。  
  
7. 中**数据库名称**文字框中，输入数据库名称中使用过**数据库名称**字段**数据存储**gridon**自定义配置管理器**组页。  
  
8. 单击**确定**按钮以保存这些条目。  
  
## <a name="see-also"></a>请参阅  
 [使用 TPE](../core/using-the-tpe.md)   
 [跟踪配置文件编辑器](../core/tracking-profile-editor.md)