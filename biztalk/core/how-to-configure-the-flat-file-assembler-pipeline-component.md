---
title: 如何配置平面文件组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- pipeline components, Flat File Assembler
- Flat File Assembler [pipeline component], configuring
- messages, flat files
ms.assetid: 5af61bba-4eb2-4bb9-a655-394a76d08d3b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0db8ce0e52ec4dfc5368f172747dc51ef7704626
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340868"
---
# <a name="how-to-configure-the-flat-file-assembler-pipeline-component"></a>如何配置平面文件组装器管道组件
平面文件组装器管道组件用于将其发送占服务器之前序列化为分隔或位置平面文件格式的 XML 文档。  
  
### <a name="to-configure-the-properties-for-the-flat-file-assembler-pipeline-component"></a>若要配置平面文件组装器管道组件的属性  
  
1.  将平面文件组装器管道组件拖至发送管道的组装阶段。  
  
2.  在属性窗口中**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**文档架构**|选择要用于序列化到平面文件格式从 XML 消息的平面文件文档架构。 如果不指定任何架构，进行运行时架构发现。 您可以在 BizTalk 编辑器创建平面文件文档架构。<br /><br /> 默认值：None|  
    |**标头架构**|选择平面文件消息的头部部分的架构。 此外可以在名为消息上下文属性中指定的标头架构**HeaderSpecName** xmlnorm 命名空间下。 在这种情况下，它将覆盖在管道设计器中指定的标头架构。<br /><br /> 您可以使用 BizTalk 编辑器创建平面文件消息的标头部分的架构。<br /><br /> 默认值：None|  
    |**保留字节顺序标记**|指定是否添加字节顺序标记 (BOM) 到组装器组件生成的文档。<br /><br /> 默认值：**False**|  
    |**目标字符集**|指定用于编码的传出消息的目标字符集。<br /><br /> 默认值：None|  
    |**尾部架构**|选择平面文件消息的尾部部分架构。 您可以创建用于平面文件消息尾部部分的架构在 BizTalk 编辑器中。<br /><br /> 默认值：None|  
  
## <a name="see-also"></a>请参阅  
 [平面文件组装器管道组件](../core/flat-file-assembler-pipeline-component.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [XML 和平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)