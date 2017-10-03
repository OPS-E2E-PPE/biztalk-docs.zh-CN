---
title: "自定义参与方解析 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- examples, parties
- pipeline components [custom], examples
- pipeline components [custom], parties
- examples, pipeline components [custom]
- parties, pipeline components [custom]
- parties, custom
ms.assetid: 1f88450f-5fe9-486d-bfb8-fd11181c78b4
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c7b88d8126a1d63760888edbcd7691ad4bd76426
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="custom-party-resolution-biztalk-server-sample"></a>自定义参与方解析（BizTalk Server 示例）
自定义参与方解析示例演示如何编写自定义管道组件以解析自定义参与方。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 自定义参与方解析示例使用以下一系列步骤完成其任务：  
  
1.  从文件夹检索 XML 文档。  
  
2.  管道解析参与方。  
  
3.  将 XML 消息写入文件夹。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径 >*\Pipelines\CustomPartyResolution\  
  
 下表显示了本示例中的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|AssemblyInfo.cs|程序集信息 C# 源文件。|  
|Cleanup.bat|清除批处理文件。|  
|CustomPartyResolution.sln|解决方案文件。|  
|CustomPartyResolutionBinding.xml|绑定文件。|  
|CustomPartyResolutionPipeline.btp|管道文件。|  
|CustomPartyResolutionPipeline.btproj|管道项目文件。|  
|CustomPartyResolutionPipelineComponent.cs|管道组件 C# 源代码。|  
|CustomPartyResolutionPipelineComponent.csproj|管道组件 Visual Studio 项目文件。|  
|InboundDocumentSchema.xsd|入站文档架构。|  
|PartyResolutionStream.cs|参与方解析流 C# 源代码。|  
|RoutingPropertySchema.xsd|路由属性架构文件。|  
|SampleInboundDocumentSchema.xml|入站文档架构文件。|  
|SampleInboundDocumentSchema_Party1.xml|示例数据实例。|  
|SampleInboundDocumentSchema_Party2.xml|示例数据实例。|  
|Setup.bat|生成和安装示例管道组件批处理文件。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
  
#### <a name="to-build-and-initialize-the-custom-party-resolution-sample"></a>生成并初始化自定义参与方解析示例  
  
1.  在命令窗口中，将目录更改 (**cd**) 的以下文件夹：  
  
     *\<示例路径 >*\Pipelines\CustomPartyResolution\  
  
2.  运行 Setup.bat 文件，这将执行以下操作：  
  
    -   创建示例中使用的输入和输出目录。  
  
    -   生成新的密钥文件。  
  
    -   生成和部署自定义参与方解析管道组件。  
  
    -   将复制到生成的管道组件*\<安装路径 >*\Pipeline 组件的目录。  
  
    -   创建发送端口和接收端口。  
  
> [!NOTE]
>  在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。  
  
## <a name="running-this-sample"></a>运行本示例  
  
#### <a name="to-run-the-custom-party-resolution-sample"></a>运行自定义参与方解析示例  
  
1.  将文件 SampleInboundDocumentSchema_Party1.xml 或 SampleInboundDocumentSchema_Party2.xml 复制到 \In 文件夹中。  
  
2.  结果将显示在 \Out 文件夹以 filename *guid*.xml。  
  
## <a name="see-also"></a>另请参阅  
 [管道 （BizTalk Server 示例文件夹中）](../core/pipelines-biztalk-server-samples-folder.md)