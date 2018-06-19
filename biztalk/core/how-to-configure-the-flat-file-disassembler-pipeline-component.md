---
title: 如何配置平面文件反汇编程序管道组件 |Microsoft 文档
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
ms.openlocfilehash: 403262bc18115923cdc5552a3b5e9e68d52f013e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249045"
---
# <a name="how-to-configure-the-flat-file-disassembler-pipeline-component"></a>如何配置平面文件反汇编程序管道组件
平面文件拆装器管道组件用于拆装平面文件格式的文档，并将其转换为 XML 格式。  
  
### <a name="to-configure-the-properties-for-the-flat-file-disassembler-pipeline-component"></a>配置平面文件拆装器管道组件的属性  
  
1.  将平面文件拆装器管道组件拖至接收管道的拆装阶段。  
  
2.  在属性窗口中，在**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**文档架构**|选择用于将消息从平面文件解析为 XML 格式的平面文件文档架构。 可以使用 BizTalk 编辑器创建用于解析的平面文件文档架构。<br /><br /> 默认值： 无**注意：** 必须指定用于此属性的架构，否则会发生编译时错误。|  
    |**标头架构**|为平面文件消息的头部部分选择架构。 可以使用 BizTalk 编辑器创建用于平面文件消息头部部分的架构。<br /><br /> 默认值： 无|  
    |**保留标头**|将此属性设置为**True**如果你需要在消息上下文上存储的平面文件消息标头。 通过保留平面文件消息的头部，可以将头部的结构和内容随消息一起通过 BizTalk Server 发送。 然后，在使用平面文件组装器管道组件将该消息重新序列化为平面文件格式时可以使用该头部。<br /><br /> 在使用平面文件组装器序列化保留的头部时，头部文档设计时属性可以缺少头部架构的名称，因为在运行时可以动态获取此信息。 这可以通过使用保留的头部的消息类型来完成。<br /><br /> 默认值： **False**|  
    |**尾部架构**|为平面文件消息的尾部部分选择架构。 可以使用 BizTalk 编辑器创建用于平面文件消息尾部部分的架构。<br /><br /> 默认值： 无|  
    |**可恢复的交换处理**|如果为“False”，则表示整个交换作为一个单元拆装（如果所包含的任何消息失败，则挂起整个交换）。<br /><br /> 如果为“True”，则表示交换中的消息由拆装器分别提取，并可以挂起通过消息传送路径和其他路径的某些传播。<br /><br /> 可恢复的交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。|  
    |**验证文档结构**|将此属性设置为**True**如果您需要进行验证的平面文件消息 （标头、 正文和预告片） 以确保它们符合其架构的所有部分。 此选项可减少的平面文件反汇编程序，性能，因此将设置为**False**默认情况下。<br /><br /> 默认值： **False**|  
  
## <a name="see-also"></a>另请参阅  
 [平面文件反汇编程序管道组件](../core/flat-file-disassembler-pipeline-component.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)   
 [XML、 平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)