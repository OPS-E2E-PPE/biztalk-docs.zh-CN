---
title: 如何配置平面文件拆装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Flat File Disassembler [pipeline component], configuring
- pipeline components, Flat File Disassembler
- messages, flat files
ms.assetid: c09996f6-6035-42a3-a75f-4def4ac39a95
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d3c28c05b63f2bdbadf99e8eb191f3ed151c130c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386067"
---
# <a name="how-to-configure-the-flat-file-disassembler-pipeline-component"></a>如何配置平面文件拆装器管道组件
平面文件拆装器管道组件用于拆装平面文件格式的文档并将它们转换为 XML 格式。  
  
### <a name="to-configure-the-properties-for-the-flat-file-disassembler-pipeline-component"></a>若要配置平面文件拆装器管道组件的属性  
  
1.  将平面文件拆装器管道组件拖至接收管道的拆装阶段。  
  
2.  在属性窗口中**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**文档架构**|选择要用于解析为 XML 格式从平面文件消息的平面文件文档架构。 在 BizTalk 编辑器中，可以创建用于分析的平面文件文档架构。<br /><br /> 默认值：无**注意：** 必须指定此属性的架构，否则将发生编译时错误。|  
    |**标头架构**|选择平面文件消息的头部部分的架构。 可以在 BizTalk 编辑器创建平面文件消息的头部部分的架构。<br /><br /> 默认值：None|  
    |**保留标头**|将此属性设置为 **，则返回 True**如果你需要在消息上下文上存储的平面文件消息标头。 保留平面文件消息的标头可以标头结构和内容，以使用通过 BizTalk Server 消息的流。 仅序列化返回到平面文件组装器管道组件中的平面文件格式的消息时，然后可以使用标头。<br /><br /> 时序列化保留的头部的平面文件组装器，头部文档设计时属性可以缺少头部架构的名称，因为在运行时动态获取此信息。 这是通过使用保留的标头的消息类型实现的。<br /><br /> 默认值：**False**|  
    |**尾部架构**|选择平面文件消息的尾部部分架构。 可以在 BizTalk 编辑器创建平面文件消息的尾部部分的架构。<br /><br /> 默认值：None|  
    |**可恢复交换处理**|如果为"false"-，指示 （如果任何包含的消息失败，整个交换被挂起） 整个交换作为一个单元拆装。<br /><br /> 如果为"true"的指示，交换中的消息分别提取，拆装器使用的某些传播通过消息传送路径和其他人被挂起。<br /><br /> 可恢复交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。|  
    |**验证文档结构**|将此属性设置为 **，则返回 True**如果你需要验证平面文件消息 （标头、 正文和尾部） 以确保它们符合其架构的所有部分。 此选项会降低平面文件拆装器的性能，因此将设置为**False**默认情况下。<br /><br /> 默认值：**False**|  
  
## <a name="see-also"></a>请参阅  
 [平面文件拆装器管道组件](../core/flat-file-disassembler-pipeline-component.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [XML 和平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)