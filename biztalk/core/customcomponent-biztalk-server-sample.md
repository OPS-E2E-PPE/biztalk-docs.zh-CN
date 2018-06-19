---
title: CustomComponent （BizTalk Server 示例） |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components [custom], examples
- examples, pipeline components [custom]
- messages, streamed
- pipeline components [custom], configuring
ms.assetid: ed0da9f5-8cc7-4528-be8c-35b80744fd38
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fd774848dec1ae54541e749a0cc551bf7c42d49
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25969731"
---
# <a name="customcomponent-biztalk-server-sample"></a>CustomComponent （BizTalk Server 示例）
CustomComponent 示例演示如何创建和使用修改流消息的自定义管道组件。 本示例还演示如何在管道设计器中对自定义管道组件进行配置。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 本示例实现了一个可将字符串作为前缀或后缀添加到输入消息中的自定义管道组件。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]处理在流式处理模式下，这意味着整个消息永远不会加载到内存中的消息。 使用以下一系列步骤演示该自定义管道组件：  
  
1.  BizTalk 从位于特定文件夹的某个文件中检索文本消息。  
  
2.  通过包含 FixMsg 自定义管道组件的接收管道发送文本消息。 您将该组件配置为在消息的开始处插入字符串。  
  
3.  通过包含 FixMsg 自定义管道组件的发送管道发送得到的文本消息。 您将该组件配置为将字符串附加到消息的末尾。  
  
4.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将得到的文本消息写入位于特定文件夹的文件中。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*示例路径*\>\Pipelines\CustomComponent\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|Cleanup.bat|用于取消部署程序集并从全局程序集缓存 (GAC) 删除这些程序集。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。|  
|Input.txt|示例输入文件。|  
|Setup.bat|用于生成和初始化本示例。|  
|在 \FixMsg 文件夹中：<br /><br /> AssemblyInfo.cs、FixMsg.csproj、FixMsg.sln|用于本示例的自定义管道组件部分的项目、解决方案和程序集信息文件。|  
|在 \FixMsg 文件夹中：<br /><br /> FixMsg.cs|实现管道组件接口。|  
|在 \FixMsg 文件夹中：<br /><br /> FixMsgStream.cs|实现的包装**System.IO.Stream**类，并启用流处理的数据。|  
|在 \FixMsg 文件夹中：<br /><br /> FixMsgDescription.cs|提供用于在管道设计器中访问和显示组件 UI 资源的方法。|  
|在 \FixMsg 文件夹中：<br /><br /> FixMsg.resx|包含属性说明、图标和错误消息。|  
|在 \PipelineComponentSample 文件夹中：<br /><br /> PipelineComponentSample.btproj、PipelineComponentSample.sln|用于本示例的 BizTalk 项目部分的项目和解决方案文件。|  
|在 \PipelineComponentSample 文件夹中：<br /><br /> PipelineComponentSampleBinding.xml|用于如端口绑定之类的自动化设置。|  
|在 \PipelineComponentSample 文件夹中：<br /><br /> FixMsgReceivePipeline.btp、FixMsgSendPipeline.btp|包含 FixMsg 自定义管道组件的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管道，分别用于接收和发送管道。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-customcomponent-sample"></a>生成并初始化 CustomComponent 示例  
  
1.  在命令窗口中，导航到下面的文件夹：  
  
     \<*示例路径*\>\Pipelines\CustomComponent  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   在以下文件夹中，为本示例创建输入 (In) 和输出 (Out) 文件夹：  
  
         \<*示例路径*\>\Pipelines\CustomComponent  
  
    -   编译并将部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]此示例的项目。  
  
    -   创建并绑定 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 接收位置、发送和接收端口。  
  
        > [!NOTE]
        >  在创建并绑定端口时，本示例将显示以下警告：  
        >   
        >  `Warning: Receive handler not specified for receive location "PCReceiveLocation"; updating with first receive handler with matching transport type.`  
        >   
        >  `Warning: Host not specified for orchestration "CustomComponent"; updating with first available host.`  
        >   
        >  可以安全地忽略这些警告。 （考虑可能命名在用户安装中，主机名的差异和接收处理程序省略了从绑定文件。）  
  
    -   启用接收位置并启动发送端口。  
  
> [!NOTE]
>  在尝试运行本示例之前，应确认在生成和初始化过程中 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 未报告任何错误。  
  
> [!NOTE]
>  如果你选择打开并生成此示例中的项目，而运行 Setup.bat 文件，则必须首先创建强名称密钥对使用.NET Framework 强名称工具 (sn.exe)。 使用该密钥对可以对生成的程序集进行签名。  
  
> [!NOTE]
>  若要撤消 Setup.bat 所做的更改，必须首先从 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理 MMC 控制台停止并重新启动主机实例。 然后运行 Cleanup.bat。 在第二个运行 Setup.bat 之前，必须运行 Cleanup.bat，时间。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-customcomponent-sample"></a>运行 CustomComponent 示例  
  
1.  将文本文件 Input.txt 的副本粘贴到 In 文件夹中。  
  
2.  查看在 Out 文件夹中创建的文本文件。该文件包含 Input.txt 文件的内容以及在 Input.txt 文件内容的开头（由接收管道）和末尾（由发送管道）插入的其他文本。 此文件的名称的格式是\< *MessageID*\>.xml，其中 *\<MessageID\>*  GUID 生成以唯一标识消息.  
  
## <a name="comments"></a>注释  
 通过执行以下步骤，可以在管道设计器中查看预配置管道：  
  
1.  在解决方案资源管理器中，双击 ReceivePipeline.btp 以便在管道设计器中打开该接收管道。 观察 FixMsg 组件将置于**验证**接收管道的阶段。  
  
2.  单击中的 FixMsg 组件**验证**设计图面上的阶段。 在“属性”窗口中，可以看到该管道组件的配置属性。 注意， **PrependData**属性设置为**数据以便在之前接收管道字符串**。  
  
3.  在解决方案资源管理器中，双击 SendPipeline.btp 以便在管道设计器中打开该发送管道。 观察 FixMsg 组件将置于**预组建**发送管道的阶段。  
  
4.  单击中的 FixMsg 组件**预组建**设计图面上的阶段。 请注意， **AppendData**属性设置为**要中追加数据发送管道字符串**。  
  
## <a name="see-also"></a>另请参阅  
 [管道（BizTalk Server 示例文件夹）](../core/pipelines-biztalk-server-samples-folder.md)