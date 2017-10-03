---
title: "如何配置平面文件汇编管道组件 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component], configuring
- messages, flat files
ms.assetid: 5af61bba-4eb2-4bb9-a655-394a76d08d3b
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7fe9c7a0720db68d8e629410dd3f0a443a99d7a4
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-flat-file-assembler-pipeline-component"></a>如何配置平面文件汇编管道组件
平面文件组装器管道组件用于在将 XML 文档发出服务器之前将其序列化为分隔的平面文件格式或位置平面文件格式。  
  
### <a name="to-configure-the-properties-for-the-flat-file-assembler-pipeline-component"></a>若要配置平面文件汇编器管道组件的属性  
  
1.  将平面文件组装器管道组件拖至发送管道的组装阶段中。  
  
2.  在属性窗口中，在**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**文档架构**|选择用于将消息从 XML 格式序列化为平面文件格式的平面文件文档架构。 如果未指定任何架构，则会执行运行时架构发现操作。 可以在 BizTalk 编辑器中创建平面文件文档架构。<br /><br /> 默认值： 无|  
    |**标头架构**|为平面文件消息的头部部分选择架构。 此外可以在名为消息上下文属性中指定标头架构**HeaderSpecName** xmlnorm 命名空间下。 在这种情况下，该架构将会覆盖在管道设计器中指定的头部架构。<br /><br /> 可以使用 BizTalk 编辑器来为平面文件消息的头部部分创建架构。<br /><br /> 默认值： 无|  
    |**保留字节顺序标记**|指定是否将一个字节顺序标记 (BOM 到汇编程序组件生成的文档)。<br /><br /> 默认值： **False**|  
    |**目标 charset**|指定用于传出消息编码的目标字符集。<br /><br /> 默认值： 无|  
    |**尾部架构**|为平面文件消息的尾部部分选择架构。 可以在 BizTalk 编辑器中为平面文件消息的尾部部分创建架构。<br /><br /> 默认值： 无|  
  
## <a name="see-also"></a>另请参阅  
 [平面文件汇编管道组件](../core/flat-file-assembler-pipeline-component.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)   
 [XML、 平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)