---
title: 架构解析器组件 （BizTalk Server 示例） |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], examples
- examples, schemas
- schemas, examples
- examples, Flat File Disassembler [pipeline component]
ms.assetid: 9ef68988-c4ee-42d5-83b5-a5c978b2007d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d34ef9109c95ae853c9d3b8319961a7c22d73628
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396914"
---
# <a name="schema-resolver-component-biztalk-server-sample"></a>架构解析器组件 （BizTalk Server 示例）
架构解析器组件示例演示如何扩展的功能[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]平面文件拆装器组件。  
  
 平面文件拆装器组件通常要求您在设计时定义分析架构。 因此如果您希望收到相同的接收位置上的不同的平面文件文档，则通常在接收管道，一个用于每个架构中包含多个平面文件拆装器。 在运行时，使用管道探测机制选择正确的拆装器组件。 但是，这种方法是如果你有多个平面文件架构，因为探测每个对应的拆装器组件会降低管道性能开销。  
  
## <a name="what-this-sample-does"></a>本示例的用途  
 架构解析器组件演示为平面文件拆装器中选择架构的一种替代方法。 在此示例中，定义四个架构，并且每个架构的消息的前两个字符是唯一的。 唯一的前两个字符和相应的架构之间定义了一个映射。 当输入的消息发送到架构解析器组件时，它读取前两个字符，确定要用于对应的文档的架构、 将架构信息保存在消息上下文，，然后调用成标准的平面文件拆装器组件。 标准平面文件拆装器组件从消息上下文读取架构信息，并使用该架构分析文档。  
  
## <a name="where-to-find-this-sample"></a>本示例所在的位置  
 *\<Samples Path\>* \Pipelines\SchemaResolverComponent\  
  
 下表显示了此示例中使用的文件，并说明其用途。  
  
|文件|Description|  
|---------------|-----------------|  
|SchemaResolverSample.sln|运用自定义管道组件的 BizTalk 项目的解决方案。|  
|SchemaResolverSample.btproj|运用自定义管道组件的 BizTalk 项目。|  
|SchemaResolverRP.btp|接收包含自定义组件的管道。|  
|PurchaseOrder.xsd, PurchaseRequest.xsd, SalesOrder.xsd, SalesRequest.xsd|平面文件架构。|  
|POInstance.txt、 PRInstance.txt、 SOInstance.txt、 SRInstance.txt|相应的平面文件文档实例。|  
|SchemaResolverFlatFileDasm.sln|实现管道组件的解决方案。|  
|SchemaResolverFlatFileDasm.csproj|C#实现管道组件的项目。|  
|SchemaResolverFlatFileDasmComp.cs|管道组件的实现。|  
|SeekableReadOnlyStream.cs|实现组件使用的可查找只读流。|  
|VirtualStream.cs|实现管道组件使用的虚拟流。|  
  
## <a name="building-and-initializing-this-sample"></a>生成并初始化此示例  
 使用以下过程生成并初始化架构解析器组件示例。  
  
#### <a name="to-build-and-initialize-this-sample"></a>若要生成并初始化本示例  
  
1.  在命令窗口中，将目录 (cd) 更改到以下文件夹：  
  
     *\<Samples Path\>* \Pipelines\SchemaResolverComponent  
  
2.  运行文件 Setup.bat，以执行以下操作：  
  
    -   生成组件。  
  
    -   将组件程序集复制到 BizTalk \Pipeline components 文件夹中。  
  
    -   生成和部署示例 BizTalk 项目。  
  
    -   配置接收位置和发送端口，并启动它们。  
  
    > [!NOTE]
    >  在尝试运行本示例前，你应确认在生成和初始化过程中未报告任何错误。  
  
## <a name="running-this-sample"></a>运行本示例  
 使用以下过程运行架构解析器组件示例。  
  
#### <a name="to-run-this-sample"></a>运行本示例的步骤  
  
1.  POInstance.txt、 PRInstance.txt、 SOInstance.txt 和 SRInstance.txt 文件放入接收位置\<*安装路径*\>\SDK\Samples\Pipelines\SchemaResolverComponent\In  
  
2.  查看写入到的四个.xml 文件\<Installdir\>\SDK\Samples\Pipelines\SchemaResolverComponent\Out 文件夹。  
  
## <a name="see-also"></a>请参阅  
 [管道 （BizTalk Server 示例文件夹中）](../core/pipelines-biztalk-server-samples-folder.md)