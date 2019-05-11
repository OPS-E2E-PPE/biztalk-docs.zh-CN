---
title: CustomComponent （BizTalk Server 示例） |Microsoft Docs
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
ms.openlocfilehash: 51b5d3e6f90184143b59fe8637b88352f610981b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65353265"
---
# <a name="customcomponent-biztalk-server-sample"></a>CustomComponent （BizTalk Server 示例）
CustomComponent 示例演示如何创建和使用修改流的消息的自定义管道组件。 此示例还演示了在管道设计器的自定义管道组件的配置。  

## <a name="what-this-sample-does"></a>本示例的用途  
 此示例实现一个自定义管道组件，可作为前缀或将字符串追加到输入消息。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 处理在流式处理模式下，这意味着整个消息永远不会加载到内存中的消息。 自定义管道组件进行了演示使用以下步骤序列：  

1. BizTalk 从特定文件夹中的文件中检索文本消息。  

2. 通过包含 FixMsg 自定义管道组件的接收管道发送文本消息。 配置要在该消息的开始处插入一个字符串，此组件。  

3. 发送通过包含 FixMsg 自定义管道组件的发送管道生成的文本消息。 配置要将一个字符串追加到的消息末尾的组件。  

4. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 将得到的文本消息写入到特定文件夹中的文件。  

## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 \<*Samples Path*\>\Pipelines\CustomComponent\  

 下表显示了本示例中的文件及其用途说明：  


|                                                     文件                                                     |                                                                                              Description                                                                                               |
|-----------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                                                   Cleanup.bat                                                   | 用于取消部署程序集并从全局程序集缓存 (GAC) 中删除它们。 删除发送和接收端口。 根据需要删除 Microsoft Internet 信息服务 (IIS) 虚拟目录。 |
|                                                    Input.txt                                                    |                                                                                           示例输入的文件。                                                                                           |
|                                                    Setup.bat                                                    |                                                                               用于生成和初始化本示例。                                                                                |
|                  在 \FixMsg 文件夹中：<br /><br /> AssemblyInfo.cs、 FixMsg.csproj、 FixMsg.sln                  |                                              此示例的自定义管道组件部分的项目、 解决方案和程序集信息文件。                                               |
|                                  在 \FixMsg 文件夹中：<br /><br /> FixMsg.cs                                   |                                                                             实现管道组件接口。                                                                              |
|                               在 \FixMsg 文件夹中：<br /><br /> FixMsgStream.cs                                |                                                      实现的包装器**System.IO.Stream**类，并启用流式处理的数据。                                                      |
|                             在 \FixMsg 文件夹中：<br /><br /> FixMsgDescription.cs                             |                                                       提供用于访问和显示管道设计器中的组件 UI 资源的方法。                                                        |
|                                 在 \FixMsg 文件夹中：<br /><br /> FixMsg.resx                                  |                                                                      包含属性说明、 图标和错误消息。                                                                      |
| 在 \PipelineComponentSample 文件夹中：<br /><br /> PipelineComponentSample.btproj, PipelineComponentSample.sln |                                                               此示例的 BizTalk 项目部分的项目和解决方案文件。                                                               |
|             在 \PipelineComponentSample 文件夹中：<br /><br /> PipelineComponentSampleBinding.xml              |                                                                             用于如端口绑定之类的自动化设置。                                                                             |
|      在 \PipelineComponentSample 文件夹中：<br /><br /> FixMsgReceivePipeline.btp、 FixMsgSendPipeline.btp      |  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 分别包含 FixMsg 自定义管道组件，用于接收和发送管道的管道。   |

## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  

#### <a name="to-build-and-initialize-the-customcomponent-sample"></a>若要生成并初始化 CustomComponent 示例  

1. 在命令窗口中，导航到以下文件夹：  

    \<*Samples Path*\>\Pipelines\CustomComponent  

2. 运行文件 Setup.bat，以执行以下操作：  

   - 创建输入 (In) 和输出 (Out) 文件夹的文件夹中的以下示例：  

      \<*Samples Path*\>\Pipelines\CustomComponent  

   - 编译并部署[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]本示例项目。  

   - 创建并绑定[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]接收位置、 发送和接收端口。  

     > [!NOTE]
     >  此示例将显示以下警告时创建并绑定端口：  
     >   
     >  `Warning: Receive handler not specified for receive location "PCReceiveLocation"; updating with first receive handler with matching transport type.`  
     >   
     >  `Warning: Host not specified for orchestration "CustomComponent"; updating with first available host.`  
     >   
     >  您可以放心地忽略这些警告。 （若要应对可能的命名差异在用户安装中，主机名和接收处理程序中已省略绑定文件。）  

   - 启用该接收位置，并启动发送端口。  

> [!NOTE]
>  您应确认[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]未报告任何错误在生成和初始化过程中尝试运行此示例之前。  
> 
> [!NOTE]
>  如果你选择打开并生成此示例中的项目，而无需运行 Setup.bat 文件，必须首先创建强名称密钥对使用.NET Framework 强名称实用工具 (sn.exe)。 使用此密钥对可以对生成程序集进行签名。  
> 
> [!NOTE]
>  若要撤消 Setup.bat 所做的更改，必须先停止并重新启动主机实例从[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理 MMC 控制台。 接下来，运行 Cleanup.bat。 必须运行 Setup.bat 前运行 Cleanup.bat 时间。  

## <a name="running-this-sample"></a>运行本示例  

#### <a name="to-run-the-customcomponent-sample"></a>若要运行 CustomComponent 示例  

1.  粘贴到 in 文件夹中的文本的副本文件 Input.txt。  

2.  查看在 Out 文件夹中创建的文本文件。此文件包含 Input.txt 文件的内容插入 （由接收管道） 的开头和末尾 （由发送管道） 的其他文本。 此文件的名称的格式\< *MessageID*\>.xml，其中*\<MessageID\>* 生成的 GUID 来唯一标识消息.  

## <a name="comments"></a>注释  
 通过执行以下步骤，可以在管道设计器中查看预配置的管道：  

1.  在解决方案资源管理器，双击 ReceivePipeline.btp 以便在管道设计器中打开接收管道。 查看 FixMsg 组件是否位于**验证**接收管道阶段。  

2.  单击中的 FixMsg 组件**验证**设计图面上的阶段。 在属性窗口中，可以看到该管道组件的配置属性。 观察**PrependData**属性设置为**数据在前面加上在接收管道字符串**。  

3.  在解决方案资源管理器，双击 SendPipeline.btp 以便在管道设计器中打开该发送管道。 查看 FixMsg 组件是否位于**预组装**发送管道阶段。  

4.  单击中的 FixMsg 组件**预组装**设计图面上的阶段。 请注意， **AppendData**属性设置为**要中追加数据在发送管道字符串**。  

## <a name="see-also"></a>请参阅  
 [管道 （BizTalk Server 示例文件夹中）](../core/pipelines-biztalk-server-samples-folder.md)