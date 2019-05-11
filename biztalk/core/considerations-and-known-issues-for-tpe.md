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
ms.openlocfilehash: ca8761237aa255322d9aa1a15fb04abcd2ac9df6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65354907"
---
# <a name="considerations-and-known-issues-for-tpe"></a>注意事项和 TPE 的已知的问题
当您使用跟踪配置文件和 TPE 时，应考虑以下问题。  
  
## <a name="naming-folders-in-the-tpe"></a>在 TPE 中命名文件夹  
 命名的文件夹在跟踪配置文件编辑器时，请注意以下命名要求：  
  
-   文件夹名称和数据项实例值的组合长度不得超过 128 个字符。  
  
-   对于 Continuation 和 ContinuationID 文件夹，文件夹的命名是将两个业务流程相关联的关键。 例如，如果业务流程 A 是业务流程 B 的父级，业务流程 A 包含其名称直接映射到业务流程 B 中的 ContinuationID 文件夹的继续符文件夹  
  
## <a name="developing-orchestrations-for-the-tpe"></a>开发 TPE 的业务流程  
 如果开始和结束形状无效，不能将业务流程映射到业务活动。 业务流程引擎不允许跟踪某些形状。 它们分别是：  
  
- 消息赋值  
  
- 转换  
  
- 组 （任务）  
  
- 挂起  
  
- 循环 (While)  
  
- 分支  
  
- 终止  
  
- 引发  
  
- 捕获  
  
- 循环形状  
  
  映射到业务活动，以便其使用跟踪配置文件编辑器和其他 BAM 工具时，请使用以下准则：  
  
- 对于组形状中，请使用非事务性作用域形状。  
  
- 对于循环形状，将其封装在非事务性作用域形状。  
  
- 对于终止形状，没有解决方法，因为在正常情况下永远不会发生此形状的结束事件。  
  
- 无法启动或结束与的任何形状将不允许拖放操作的计划。  
  
## <a name="applying-tracking-profiles-that-monitor-running-processes"></a>应用监视正在运行的进程的跟踪配置文件  
 如果该活动将包含 BAM 继续符，更新跟踪配置文件可能会影响正在进行中的活动实例。 具体而言，如果跟踪配置文件更新指定的已记录某个活动项的数据的下游拦截，就可以将覆盖原始值。 从本质上讲，任何单个事件流不会受跟踪配置文件更新，因为每个流对象绑定到活动/流开始时就已存在的配置文件的特定版本的应用程序。 但是，由于延续关联多个事件流的方式，流尚未开始更新配置文件的时间会选取更新，从而导致可能覆盖数据的情况中的更改。 有关继续符的详细信息，请参阅[活动继续符](../core/activity-continuation.md)并[如何创建一个继续符](../core/how-to-create-a-continuation.md)。  
  
## <a name="tracking-profiles-without-a-send-or-receive-shape-from-which-to-draw-message-properties"></a>跟踪配置文件而无需发送或接收形状从其提取消息属性  
 继续符跟踪通过上下文属性或相同的活动之间的有效负载数据的活动。 消息 ID、 服务 ID 和实例 ID 等属性更改活动之间的值。  
  
 你可以创建跟踪配置文件可使用以下方法处理这种情况：  
  
-   如果业务流程通过动态绑定到另一个业务流程发送一条消息，全局唯一负载数据值可以用于将延续任务。  
  
-   如果消息中没有任何唯一负载数据，则可以使用消息的交换 ID。 若要使用的交换 ID，必须在同一接收形状上对它进行跟踪。 如果时创建的新消息的交换 ID 更改为创建新消息，则无法使用交换 ID。 从任何非接收形状或发送形状跟踪交换 ID 是不可靠的。  
  
-   只要业务流程中使用，从管道接收的消息、，即业务流程端口绑定到管道和接收形状和消息 ID 会跟踪从该位置，还可以使用消息 ID。 如果您从其他形状跟踪消息 ID，将消息 ID 将在继续符中使用无效。  
  
-   如果业务流程调用另一个业务流程和未传递任何消息，或业务流程调用另一个业务流程，但被调用方不具有任何构造、 接收或发送形状，可以检索负载数据值，则用户可以使用实例 id。 调用的业务流程的实例 ID 不会更改。  
  
-   如果业务流程将加载另一个业务流程通过执行调用而不是调用它直接，则将无法使用任何静态消息属性来跟踪活动。 用户无法启用继续符。 在此实例中执行跟踪的唯一方法是一条消息将通过管道，其中包含要对其执行跟踪的唯一负载数据。  
  
## <a name="you-cannot-use-a-session-id-as-a-continuation-token-for-pass-through-pipelines"></a>无法将会话 ID 用作直通管道的继续标记  
 在跟踪配置文件，当从某个消息负载中，选择项时的跟踪配置文件绑定到该消息的架构。 在直通管道中，架构名称值为 null 值。 当 BAM 尝试加载由端口名称和架构名称的配置时它不能对会话 ID 架构进行匹配，并由引擎跟踪任何数据。  
  
 对于直通管道，可以删除所有负载跟踪从跟踪配置文件，或如果需要跟踪负载数据，请使用 XML 管道。  
  
## <a name="using-unique-port-names"></a>使用唯一端口名  
 当枚举双向端口，TPE 显示它们视为两个逻辑端口、 发送和接收端口。 每个这些逻辑端口将显示相同的名称。 BizTalk Server，可创建具有相同名称的单向和双向端口。 例如，您可以创建一个名为"Port1"的双向端口，然后创建具有相同名称的接收端口。 在这些情况下 TPE 显示接收端口一次和双向端口两次，一次一次为接收端口和发送端口。  
  
 TPE 将应用跟踪配置文件，同时在这种情况下接收端口。 我们建议端口指定唯一名称，以帮助正确标识它们。  
  
## <a name="using-tpe-orchestrations-with-a-parallel-shape-as-the-first-shape"></a>使用并行形状的 TPE 业务流程使用作为第一个形状  
 如果开始业务流程以分叉、 并行或侦听形状，则不能映射上的一个分支的活动 ID。 在并行处理的情况下可以映射到分叉形状上面 ActivityID。 您还可以让 BAM 生成活动 ID，以避免并行形状在业务流程的顶部的问题。  
  
> [!IMPORTANT]
>  一个活动映射到多个路径，且将 ActivityID 映射到分叉形状将导致错误时处理如下所示在其未映射 ActivityID 的路径的一个路径。  
  
## <a name="availability-of-message-properties-at-design-time"></a>在设计时的消息属性的可用性  
 创建跟踪配置文件，并不是所有消息属性都时可用。 这是最有可能会遇到其中从映射消息属性的形状位于业务流程顶部时。 在这些情况下，消息属性的值为 null。  
  
 此示例中是侦听形状在业务流程中的第一个形状。 当从此形状映射消息属性时，只有以下属性具有值：InstanceID、 ServiceID 和 ServiceClassID。 （MessageID 作用域中此时并不具有 null 值。）  
  
## <a name="you-cannot-map-shapes-inside-a-loop-shape-to-report-a-milestone"></a>无法映射循环形状来报告里程碑内部的形状  
 TPE 将阻止从循环形状中包含的活动映射到循环外的项的源。  
  
 循环活动是指用于循环，或在业务流程内重复的操作。 就可以捕获来自业务流程内循环的操作的事件。 若要执行此操作，创建另一个活动并将映射的所有新活动里程碑和在循环内的数据。 这是必需的因为在循环中的数据处理将会发生多个计划的执行每一次。  
  
 例如，如果您有包含在循环中处理的多个行项的采购订单，问题，如"哪些采购订单的货物价格为 $100？" 是不明确。 问题则含义明确：  
  
 哪些采购订单的价格为 $100 的货物行？  
  
 哪些采购订单的总计/最小/最大货物价格为 $100？  
  
 内容使用独立的从采购订单创建明确问题需要考虑的行项。 在跟踪配置文件编辑器中，根活动 （例如，采购订单） 映射到在循环外的所有操作。 子活动 （例如，行项） 映射到此循环操作。  
  
 使用这些类型的构造的典型方法是分解重复的循环并使相关的活动基于与外部活动相关的内部活动。  
  
 您需要一个负载项用作根活动的 ActivityID 和使此负载项目可在某些内部循环的消息。 该活动映射到关系节点下的子活动，并将其命名为根活动。  
  
## <a name="tracking-profiles-spanning-multiple-applications"></a>跟踪跨多个应用程序的配置文件  
 如果跟踪配置文件跨越多个应用程序，在部署解决方案中的所有应用程序后，必须部署跟踪配置文件。 如果跟踪配置文件不是部署的最后一项，将收到以下消息"**找不到映射源。**"，在部署向导调用 BTTDeploy.exe 时。  
  
## <a name="mapping-multiple-biztalk-server-artifacts-to-a-document-reference-url-or-messageid-nodes"></a>多个 BizTalk Server 项目映射到一个文档引用 URL 或消息 Id 节点  
 TPE，可从到相同的文档引用 URL 或消息 Id 节点上的多个 BizTalk Server 项目拖放。  
  
 在其中多个源映射到 BAM 活动中的相同项的情况下上, 一项目的是 BAM 过程中遇到处理是一种跟踪数据中仍然存在，可以在 BAM 门户中查看。  
  
## <a name="updating-btt-versions-to-match-biztalk-solution-versions"></a>更新 BTT 版本以与 BizTalk 解决方案版本相匹配  
 BAM 开发人员和管理员可以通过自动化 BTT 文件的更新保持跟踪配置文件和 BizTalk 解决方案之间的版本同步。 若要执行此操作，修改**版本**属性中**DataLevel** BTT 文件的元素。 在下面的元素示例中，将修改 TargetAssemblyName 和 SchemaName 属性中的版本信息。  
  
```  
<DataLevel Name="City" SourceTypeSelected="Messaging Payload" TargetAssemblyName="TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SchemaName="TheImplementationOfOrderMgmt.PurchaseOrder,TheImplementationOfOrderMgmt, Version=1.0.0.0, Culture=neutral, PublicKeyToken=c5b33e44ffa4658b" SomXPath="/*[local-name()='<Schema>' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" XPath="/*[local-name()='PurchaseOrder' and namespace-uri()='http://TheImplementationOfOrderMgmt.PurchaseOrder']/*[local-name()='Header' and namespace-uri()='']/*[local-name()='ShipTo' and namespace-uri()='']/@*[local-name()='City' and namespace-uri()='']" IsBeginActivity="true" IsEndActivity="false">  
```  
  
## <a name="some-orchestration-shapes-cannot-be-tracked-in-the-tpe"></a>某些业务流程形状不能在 TPE 中跟踪  
 业务流程引擎不会生成以下形状的事件并因此无法跟踪或在 TPE 中映射这些形状：  
  
-   任务  
  
-   所有分支  
  
-   挂起  
  
-   终止  
  
-   引发  
  
-   捕获  
  
-   MessageAssignment （因为它是构造形状的一部分）  
  
-   转换 （因为它是构造形状的一部分）  
  
-   循环  
  
## <a name="tpe-not-retrieving-deployed-tracking-profiles"></a>TPE 不检索已部署的跟踪配置文件  
 升级或重新部署可能会遇到在检索已部署的问题后跟踪配置文件。 这可能引起的方式上的 BizTalkMgmtDb 数据库的服务器名称存储在注册表中的不匹配。  
  
 BizTalkMgmtDb 在组配置期间写入到注册表。 TPE 使用项查找主导入数据库和筛选跟踪配置文件。  
  
 在配置过程中就可以用多种格式输入服务器名称。 例如：  
  
- mgmtsvr1316267,15001\inst  
  
- MGMTSVR1316267\inst 15001  
  
  使用注册表项时，TPE 将执行基本字符串比较。 若要检索已部署的跟踪配置文件是检查存储的服务器和数据库名称和输入在 TPE 中所需**设置管理数据库**对话框。  
  
#### <a name="to-determine-the-syntax-for-server-and-database-names-and-enter-it-in-the-biztalk-management-database"></a>若要确定服务器和数据库名称的语法并将其输入 BizTalk 管理数据库中。  
  
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