---
title: "如何将 XML 反汇编程序管道组件配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, pipeline components
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], configuring
- disassembly stage, pipelines
- receive pipelines, disassembly stage
ms.assetid: 93dd9148-4ae4-4868-b85d-66eada354f58
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 376daf04abb9bb555e9190fc819c3a3360cbe3cf
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-xml-disassembler-pipeline-component"></a>如何将 XML 反汇编程序管道组件配置
接收管道的拆装阶段中，应使用 XML 反汇编程序管道组件。  
  
### <a name="to-configure-the-properties-for-the-xml-disassembler-pipeline-component"></a>配置 XML 拆装器管道组件的属性  
  
1.  将 XML 拆装器管道组件拖至接收管道的拆装阶段中。  
  
2.  在属性窗口中，在**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**允许无法识别的消息**|指明是否允许不属于可识别的消息类型的消息通过拆装器。<br /><br /> 默认值： **False**|  
    |**文档架构**|指明要应用于文档的一个或多个架构的命名空间和类型名。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。<br /><br /> 此属性中指定的架构应具有唯一目标命名空间。 如果有任何架构的命名空间与之相同，则对文档实例的验证将可能无法按预期方式工作。 如果架构必须具有相同的命名空间，你应创建用于每个架构的单独管道和指定每个 XML 反汇编程序管道组件的一个架构或使用一条管线但未指定任何架构作为 XML 反汇编程序管道的参数组件。<br /><br /> 默认值：空集合|  
    |**信封架构**|指明要应用于信封的一个或多个架构的命名空间和类型名。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。<br /><br /> 此属性中指定的架构应具有唯一目标命名空间。 如果有任何架构的命名空间与之相同，则对文档实例的验证将可能无法按预期方式工作。 如果架构必须具有相同的命名空间，你应创建用于每个架构的单独管道和指定每个 XML 反汇编程序管道组件的一个架构或使用一条管线但未指定任何架构作为 XML 反汇编程序管道的参数组件。<br /><br /> 默认值：空集合|  
    |**可恢复的交换处理**|如果为“False”，则表示整个交换作为一个单元拆装（如果所包含的任何消息失败，则挂起整个交换）。<br /><br /> 如果为“True”，则表示交换中的消息由拆装器分别提取，并可以挂起通过消息传送路径和其他路径的某些传播。<br /><br /> 可恢复的交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。|  
    |**验证文档结构**|当**True**，执行对文档和 （可选） 信封架构的传入消息验证。<br /><br /> 如果已提升的属性没有默认值或固定的值，此属性设置为**False**，该属性不提升。<br /><br /> 默认值： **False** **注意：**时**True**，如果你指定两个或多个架构，可能会收到"两个或多个所选架构共享相同的目标命名空间"错误有关**文档架构**或**信封架构**属性。|  
  
## <a name="see-also"></a>另请参阅  
 [XML 反汇编程序管道组件](../core/xml-disassembler-pipeline-component.md)   
 [XML、 平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)