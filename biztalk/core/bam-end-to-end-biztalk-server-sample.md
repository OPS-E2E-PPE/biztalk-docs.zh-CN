---
title: "BAM BizTalk Server 中的端到端示例 |Microsoft 文档"
description: "有关如何将来自多个组件在 BizTalk Server 中使用业务活动监视的事件相关联的方案"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81406038-7f3f-499f-a003-12423d92c44b
caps.latest.revision: "35"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 21cf3bcfae53d3204a1b4de23c1476591be2b453
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="bam-end-to-end-biztalk-server-sample"></a>BAM 端对端（BizTalk Server 示例）
端到端示例演示如何通过使用 BAM 关联中 （在这种情况下，三个业务流程和管道） 的多个组件的事件。  
  
 BAM 重新构造了跨管道组件和业务流程的业务活动。 在最低级别，之所以能够通过调用**EventStream.EnableContinuation**从每个需要更多事件活动的实现组件。 调用**EnableContinuation**是显式的调用由在 Orchestration1 和 Orchestration2 将延续文件夹添加到一个计划，并遵循的计划的 ContinuationID 文件夹中的跟踪配置文件时它。  
  
 下图说明了本示例中使用的工作流。  
  
 ![](../core/media/ebiz-sdk-samples-bam-endtoendwkflw.gif "ebiz_sdk_samples_bam_endtoendwkflw")  

  
## <a name="what-this-sample-does"></a>本示例的用途  
 BAM 端对端示例显示如何使用 BAM 从管道和多个业务流程收集信息并更新单个活动。  
  
## <a name="how-this-sample-was-designed-and-why"></a>本示例的设计方式和原因  
 BAM 端对端示例旨在阐释下列活动：  
  
-   在管道中使用 BAM。  
  
-   使用跟踪配置文件编辑器 (TPE) 将活动项映射到业务流程中的形状和消息的元素。  
  
-   当一个解决方案的多个部分都作用于活动时，使用继续符使活动保持活动状态。  
  

本示例的工作原理如下所示：  
  
1.  从检索到输入的消息*\<示例路径 >*\BamEndToEnd\Input 文件夹。  
  
2.  管道组件向消息分配唯一的 DocumentID，然后使用 BAM API 开始一个新 BAM 活动。 将此 DocumentID 作为此输入消息的一个单独部分附加，以使其可用于业务流程。  
  
3.  在收到此输入消息时激活服务 Orchestration1。  
  
4.  Orchestration1 修改此输入消息，然后将其作为参数传递给 Orchestration2。  
  
5.  Orchestration2 修改此输入消息，然后将其发送给 MessageBox 数据库，这便激活了 Orchestration3。  
  
6.  Orchestration3 修改消息并将其写入文件夹*\<示例路径 >*\BamEndToEnd\Output。  
  
7.  每个业务流程都会更新 BAM 活动中的活动项。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 你可以找到在此示例*\<示例路径 >*\BAM\BamEndToEnd。  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|----|---|  
|BamEndToEnd.sln|BAM 端对端示例解决方案。|  
|BamEndToEnd.xls|BAM 定义样式表。|  
|BamEndToEnd.xml|BAM 定义 XML。|  
|BAMEndToEndBinding.xml|BAM 绑定。|  
|Cleanup.bat|用于取消部署本示例的批处理文件。|  
|InputMessage.xml|输入消息。|  
|Setup.bat|用于编译和部署本示例的批处理文件。|  
|\Components\AssemblyInfo.cs|管道组件代码。|  
|\Components\BAMMessagePartPLComponent.cs|管道组件代码。|  
|\Components\Components.csproj|管道组件项目。|  
|\Messages\InputMessage01.xml<br /><br /> ...<br /><br /> \Messages\InputMessage10.xml|示例输入的消息。|  
|\Services\BAMInbound.btp|入站管道文件。|  
|\Services\BAMPartSchema.xsd|BAM 部分消息架构。|  
|\Services\Orchestration1.odx|业务流程。|  
|\Services\Orchestration2.odx|业务流程。|  
|\Services\Orchestration3.odx|业务流程。|  
|\Services\PropertySchema.xsd|属性架构。|  
|\Services\Schema1.xsd|消息架构。|  
|\Services\Schema2.xsd|消息架构。|  
Services\Schema3.xsd|消息架构。|  
|\Services\Services.btproj|[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk 文件项目。|  
|\Services\Transform_1.btm|映射文件。|  
|\Services\Transform_2.btm|映射文件。|  
|\Services\Transform_3.btm|映射文件。|  
  
## <a name="how-to-use-this-sample"></a>如何使用本示例  
 请按下面的过程生成并运行 BAM 端对端示例：  
  
-   [若要生成并初始化此示例](#To_Build_Sample)  
  
-   [若要运行此示例](#To_Run_Sample)  
  
-   [若要查看 BAM 数据](#To_View_Data)  
  
##  <a name="To_Build_Sample"></a>生成并初始化此示例  
  
1.  打开命令提示符以管理员身份，并运行*\<示例路径 >*\BAM\BAMEndToEnd\Setup.bat。 Setup.bat 为此示例生成并初始化 BAM 基础结构。 保持命令提示符处于打开状态。  
  
2.  创建一个跟踪配置文件，以将 Orchestration1、Orchestration2 和 Orchestration3 映射到 BAM 活动。 (由于创建跟踪配置文件是一个复杂的过程，在单独的过程调用了的详细的说明**创建跟踪配置文件**。 此过程位于本文档后面的部分中。）  
  
3.  部署上一步中创建的跟踪配置文件 BamEndToEnd.btt。  在命令提示符将更改为*\<示例路径 >*\BAM\BamEndToEnd 目录。 若要部署的跟踪配置文件，请键入以下行，，然后按**Enter**:  
  
    `“<BizTalkInstallationPath>\Tracking\bttdeploy” BamEndToEnd.btt`
  
     [如何部署跟踪配置文件使用跟踪配置文件管理实用程序](../core/how-to-deploy-tracking-profiles-with-the-tracking-profiles-management-utility.md)提供了详细信息。
  
    > [!IMPORTANT]
    >  你可以忽略 ContinuationID Orch1_ 没有匹配继续符的消息。 预期会出现此消息，因为名为 Orch1_ 的继续符是在管道组件中定义的，而不是在踪配置文件中。  
  
##  <a name="To_Run_Sample"></a>运行此示例  
  
将文件复制*\<示例路径 >*到文件夹 \BamEndToEnd\InputMessage.xml *\<示例路径 >*\BamEndToEnd\Input。 在几秒钟后，消息消失从输入文件夹中，并输出消息出现在*\<示例路径 >*\BamEndToEnd\Output 文件夹。  
  
##  <a name="To_View_Data"></a>查看 BAM 数据  
  
1.  打开 SQL Server Management Studio。  
  
2.  在 SQL Server Management Studio，展开服务器，展开**数据库**，展开**BAMPrimaryImport**，然后展开**表**。  
  
3.  右键单击**dbo.bam_EndToEndActivity_Completed**，然后单击**打开表**。 如果你使用[!INCLUDE[btsSQLServer2008](../includes/btssqlserver2008-md.md)]，单击**选择前 1000年行**。  
  
     右窗格中会显示 bam_EndToEndActivity_Completed 表的内容。 表中的每一行均代表一个已完成的 EndToEndActivity 活动。  
  
#### <a name="rerun-this-sample"></a>重新运行此示例  
  
1.  打开命令提示符以管理员身份，并将更改为*\<示例路径 >*\BAM\BamEndToEnd 目录。 键入以下行：  
  
    `“C:\Program Files\Microsoft BizTalk Server <version>\Tracking\bttdeploy” BamEndToEnd.btt /remove`  
  
    > [!NOTE]
    >  如果你未安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]到 C 驱动器中，将"C"替换为你的安装位置的驱动器号[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
2.  运行*\<示例路径 >*\BAM\BAMEndToEnd\Cleanup.bat。 Cleanup.bat 移除此示例的 BAM 基础结构。  
  
3.  执行中的步骤**生成并初始化此示例**本主题中的部分。  
  
##  <a name="TPE_procedure"></a>创建跟踪配置文件  
  
1.  单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]。 右键单击**跟踪配置文件编辑器**，和**以管理员身份运行**。  
  
2.  在左窗格中**跟踪配置文件编辑器**窗口中，单击**单击此处以导入 BAM 活动定义**。  
  
3.  在**BAM 活动定义名称**部分**导入 BAM 活动定义**对话框中，选择**EndToEndActivity**，然后单击**确定**.  
  
4.  在右窗格中**跟踪配置文件编辑器**窗口中，单击**单击此处选择的事件源**。  
  
5.  在**程序集名称**部分**选择事件源父程序集**对话框中，选择**Microsoft.Samples.BizTalk.BamEndToEnd.Services**，然后单击**下一步**。  
  
6.  在**Orchestration 名称**部分**选择业务流程**对话框中，选择**BamEndToEnd.Services.Orchestration1**，然后单击**确定**.  
  
7.  在左窗格中**跟踪配置文件编辑器**窗口中，右键单击**EndToEndActivity**，然后单击**新 ContinuationID**。 命名新的延续 ID **Orch1_**。 重复此步骤以创建两个多个延续 Id 名为**Orch2_**和**Orch3_**。  
  
8.  右键单击**EndToEndActivity**，然后单击**新的延续**。 命名新的延续**Orch2_**。 重复此步骤以创建名为的另一个延续**Orch3_**。  
  
9. 右键单击**Receive1**形状，并依次**上下文属性架构**。  
  
10. 滚动到末尾**上下文属性名称**列表，，然后双击**BAMEndToEnd.Services.PropertySchema.DocumentID**。  
  
11. 展开**\<架构 >**，然后拖动**DocumentID**到右窗格中**Orch1_**的左窗格中。  
  
12. 单击文件夹图标带有箭头 (![使用文件夹和向上箭头的按钮](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 两次以显示业务流程。  
  
13. 拖动**Receive1**到右窗格中的形状**SBegin1**的左窗格中。  
  
14. 拖动**StartOrchestration_1**到右窗格中的形状**SEnd1**的左窗格中。  
  
15. 右键单击**StartOrchestration_1**形状，并依次**消息负载架构**。  
  
16. 在双击包含"Message_2"的值的行**消息**列和值"MessageBody"中**一部分**列。  
  
     ![键入消息负载架构显示消息和 #95; 2](../core/media/77fbc444-46cf-4d45-8e9c-c330da7ba7d1.gif "77fbc444-46cf-4d45-8e9c-c330da7ba7d1")  
  
17. 展开**Schema2**，然后拖动**Data2**到右窗格中**Data1**的左窗格中。  
  
18. 单击**选择事件源**，然后单击**选择上下文属性**。  
  
19. 滚动到末尾**上下文属性名称**列表，，然后双击**BAMEndToEnd.Services.PropertySchema.DocumentID**。  
  
20. 展开**\<架构 >**，然后拖动**DocumentID**到**Orch2_**延续的左窗格中。  
  
    > [!NOTE]
    >  不要混淆 Orch2_ 延续替换 Orch2_ 延续 id。 表示延续 ID 的图标包含键 (![图标延续 ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示延续的图标不包含键 （![延续图标](../core/media/test.gif "测试"))。  
  
21. 单击**选择事件源**，然后单击**选择业务流程计划**。  
  
22. 在**程序集名称**部分**选择事件源父程序集**对话框中，选择**Microsoft.Samples.BizTalk.BamEndToEnd.Services**，然后单击**下一步**。  
  
23. 在**Orchestration 名称**部分**选择业务流程**对话框中，选择**BamEndToEnd.Services.Orchestration2**，然后单击**确定**.  
  
24. 右键单击**ConstructMessage_1**形状，并依次**消息负载架构**。  
  
25. 在双击包含"Message_3"的值的行**消息**列和值"BAMPart"中**一部分**列。  
  
26. 展开**BAMPart**，然后拖动**DocumentID**到右窗格中**Orch2_**延续的左窗格中的 ID。  
  
    > [!NOTE]
    >  不要混淆 Orch2_ 延续替换 Orch2_ 延续 id。 表示延续 ID 的图标包含键 (![图标延续 ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示延续的图标不包含键 （![延续图标](../core/media/test.gif "测试"))。  
  
27. 单击文件夹图标带有箭头 (![使用文件夹和向上按钮 &#45; 箭头](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 两次以显示业务流程。  
  
28. 拖动**ConstructMessage_1**到右窗格中的形状**SBegin2**的左窗格中。  
  
29. 拖动**Send_1**到右窗格中的形状**SEnd2**的左窗格中。  
  
30. 右键单击**Send_1**形状，并依次**消息负载架构**。  
  
31. 在双击包含"Message_3"的值的行**消息**列和值"MessageBody"中**一部分**列。  
  
32. 展开**Schema3**，然后拖动**Data3**到右窗格中**Data2**的左窗格中。  
  
33. 从右侧窗格上的下拉列表列表中选择**消息负载架构**。  
  
34. 在双击包含"Message_3"的值的行**消息**列和值"BAMPart"中**一部分**列。  
  
35. 展开**BAMPart**，然后拖动**DocumentID**到右窗格中**Orch3_**延续的左窗格中。  
  
    > [!NOTE]
    >  不要混淆 Orch3_ 延续替换 Orch3_ 延续 id。 表示延续 ID 的图标包含键 (![图标延续 ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示延续的图标不包含键 （![延续图标](../core/media/test.gif "测试"))。  
  
36. 单击**选择事件源**，然后单击**选择业务流程计划**。  
  
37. 在**程序集名称**部分**选择事件源父程序集**对话框中，选择**Microsoft.Samples.BizTalk.BamEndToEnd.Services**，然后单击**下一步**。  
  
38. 在**Orchestration 名称**部分**选择业务流程**对话框中，选择**BamEndToEnd.Services.Orchestration3**，然后单击**确定**.  
  
39. 右键单击**Receive1**形状，并依次**消息负载架构**。  
  
40. 在双击包含"Message_3"的值的行**消息**列和值"BAMPart"中**一部分**列。  
  
41. 展开**BAMPart**，然后拖动**DocumentID**到右窗格中**Orch3_**延续的左窗格中的 ID。  
  
    > [!NOTE]
    >  不要混淆 Orch3_ 延续替换 Orch3_ 延续 id。 表示延续 ID 的图标包含键 (![图标延续 ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示延续的图标不包含键 （![延续图标](../core/media/test.gif "测试"))。  
  
42. 单击文件夹图标带有箭头 (![使用文件夹和向上箭头的按钮](../core/media/abccd08b-2b01-49c6-80ed-a032bbbd10d4.gif "abccd08b-2b01-49c6-80ed-a032bbbd10d4")) 两次以显示业务流程。  
  
43. 拖动**Receive1**到右窗格中的形状**SBegin3**的左窗格中。  
  
44. 拖动**Send_1**到右窗格中的形状**SEnd3**的左窗格中。  
  
45. 右键单击**Send_1**形状，并依次**消息负载架构**。  
  
46. 展开**Schema3**，然后拖动**Data3**到右窗格中**Data3**的左窗格中。  
  
47. 右键单击**DocumentID**下面**Orch2_**延续任务，，然后单击**集端口映射**。  
  
    > [!NOTE]
    >  不要混淆 Orch2_ 延续替换 Orch2_ 延续 id。 表示延续 ID 的图标包含键 (![图标延续 ID](../core/media/2d04a714-ade9-4e96-b89e-00002da75bea.gif "2d04a714-ade9-4e96-b89e-00002da75bea"))，而表示延续的图标不包含键 （![延续图标](../core/media/test.gif "测试"))。  
  
48. 在**选择端口**部分**选择端口**对话框中，单击**BamEndToEnd_ReceivePort**，单击大于-号 ( **>**)，然后单击**确定**。  
  
49. 保存跟踪配置文件到*\<示例路径 >*\BAM\BamEndToEnd\BamEndToEnd.btt。  
  
## <a name="important-details"></a>重要详细信息  
 管道不支持跟踪配置文件。 但是，对的调用**BeginActivity**在管道组件是在业务流程中使用 ActivityID 相同。 调用**EnableContinuation**等同于业务流程中使用延续。  
  
## <a name="see-also"></a>另请参阅  
 [业务活动监视 （BizTalk Server 示例文件夹中）](../core/business-activity-monitoring-biztalk-server-samples-folder.md)