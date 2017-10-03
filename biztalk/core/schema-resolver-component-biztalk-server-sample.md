---
title: "架构冲突解决程序组件 （BizTalk Server 示例） |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], examples
- examples, schemas
- schemas, examples
- examples, Flat File Disassembler [pipeline component]
ms.assetid: 9ef68988-c4ee-42d5-83b5-a5c978b2007d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37ec562cbc64d15e66d2f265c52606817169bb85
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="schema-resolver-component-biztalk-server-sample"></a>架构冲突解决程序组件 （BizTalk Server 示例）
架构冲突解决程序组件示例演示如何扩展的功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]平面文件反汇编程序组件。  
  
 平面文件拆装器组件通常要求您在设计时定义分析架构。 因此，如果希望在同一接收位置接收不同的平面文件文档，则通常在接收管道中为每个架构包含一个平面文件拆装器。 在运行时，将使用管道探测机制选择正确的拆装器组件。 但是，如果您的平面文件架构很多，这种方法的开销会很大，原因是探测每个对应的拆装器组件会降低管道的性能。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 架构解析器组件演示为平面文件拆装器选择架构的备用方法。 在本示例中，定义了四个架构，每个架构的消息的前两个字符是唯一的。 在唯一的前两个字符与对应的架构之间定义了一个映射。 当将输入消息发送到架构解析器组件时，架构解析器读取前两个字符，确定要用于对应文档的架构，将架构信息保存在消息上下文中，然后调用标准平面文件拆装器组件。 标准平面文件拆装器组件从消息上下文读取架构信息，然后使用该架构分析文档。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<示例路径 >*\Pipelines\SchemaResolverComponent\  
  
 下表显示了本示例中使用的文件及其用途说明：  
  
|文件|Description|  
|---------------|-----------------|  
|SchemaResolverSample.sln|运用自定义管道组件的 BizTalk 项目解决方案。|  
|SchemaResolverSample.btproj|运用自定义管道组件的 BizTalk 项目。|  
|SchemaResolverRP.btp|包含自定义组件的接收管道。|  
|PurchaseOrder.xsd、PurchaseRequest.xsd、SalesOrder.xsd、SalesRequest.xsd|平面文件架构。|  
|POInstance.txt、PRInstance.txt、SOInstance.txt、SRInstance.txt|对应的平面文件文档实例。|  
|SchemaResolverFlatFileDasm.sln|实现管道组件的解决方案。|  
|SchemaResolverFlatFileDasm.csproj|实现管道组件的 C# 项目。|  
|SchemaResolverFlatFileDasmComp.cs|实现管道组件。|  
|SeekableReadOnlyStream.cs|实现组件使用的可查找只读流。|  
|VirtualStream.cs|实现管道组件使用的虚拟流。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 请按下面的过程生成并初始化架构解析器组件示例。  
  
#### <a name="to-build-and-initialize-this-sample"></a>构建和初始化此示例  
  
1.  在命令窗口中，将目录更改 (cd) 为以下文件夹：  
  
     *\<示例路径 >*\Pipelines\SchemaResolverComponent  
  
2.  运行 Setup.bat 文件，该文件将执行以下操作：  
  
    -   生成组件。  
  
    -   将组件程序集复制到 BizTalk \Pipeline 组件文件夹中。  
  
    -   生成和部署示例 BizTalk 项目。  
  
    -   配置并启动接收位置和发送端口。  
  
    > [!NOTE]
    >  在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程可以运行架构解析器组件示例。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  POInstance.txt、 PRInstance.txt、 SOInstance.txt、 和 SRInstance.txt 文件放在接收位置\<*安装路径*> \SDK\Samples\Pipelines\SchemaResolverComponent\In  
  
2.  观察写入到的四个.xml 文件\<Installdir > \SDK\Samples\Pipelines\SchemaResolverComponent\Out 文件夹。  
  
## <a name="see-also"></a>另请参阅  
 [管道 （BizTalk Server 示例文件夹中）](../core/pipelines-biztalk-server-samples-folder.md)