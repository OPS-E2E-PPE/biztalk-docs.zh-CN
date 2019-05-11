---
title: 如何配置 XML 拆装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring, pipeline components
- pipeline components, XML Disassembler
- XML Disassembler [pipeline component], configuring
- disassembly stage, pipelines
- receive pipelines, disassembly stage
ms.assetid: 93dd9148-4ae4-4868-b85d-66eada354f58
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: aa38f975042256a52184c44e75f9b079dd00c6df
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385998"
---
# <a name="how-to-configure-the-xml-disassembler-pipeline-component"></a>如何配置 XML 拆装器管道组件
XML 拆装器管道组件应在接收管道的拆装阶段中使用。  
  
### <a name="to-configure-the-properties-for-the-xml-disassembler-pipeline-component"></a>若要配置 XML 拆装器管道组件的属性  
  
1.  将 XML 拆装器管道组件拖至接收管道的拆装阶段。  
  
2.  在属性窗口中**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**允许无法识别的消息**|指示是否允许不具有可识别的消息类型通过拆装器传递的消息。<br /><br /> 默认值：**False**|  
    |**文档架构**|指示命名空间和类型名或多个架构应用于文档。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。<br /><br /> 此属性中指定的架构应具有唯一目标命名空间。 如果具有相同的命名空间的任何架构，对文档实例的验证可能不会按预期工作。 如果架构必须具有相同的命名空间，您应创建单独的管道为每个架构和指定每个 XML 拆装器管道组件的一个架构，或使用一个管道但不是执行任何架构指定为 XML 拆装器管道的参数组件。<br /><br /> 默认值：空集合|  
    |**信封架构**|指示命名空间和类型名或多个要应用于信封的架构。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。<br /><br /> 此属性中指定的架构应具有唯一目标命名空间。 如果具有相同的命名空间的任何架构，对文档实例的验证可能不会按预期工作。 如果架构必须具有相同的命名空间，您应创建单独的管道为每个架构和指定每个 XML 拆装器管道组件的一个架构，或使用一个管道但不是执行任何架构指定为 XML 拆装器管道的参数组件。<br /><br /> 默认值：空集合|  
    |**可恢复的交换处理**|如果为"false"-，指示 （如果任何包含的消息失败，整个交换被挂起） 整个交换作为一个单元拆装。<br /><br /> 如果为"true"的指示，交换中的消息分别提取，拆装器使用的某些传播通过消息传送路径和其他人被挂起。<br /><br /> 可恢复交换处理的详细信息，请参阅[可恢复交换处理](../core/recoverable-interchange-processing.md)。|  
    |**验证文档结构**|当 **，则返回 True**，执行对文档和信封架构 （可选） 将传入消息的验证。<br /><br /> 如果升级的属性不具有默认值或固定的值，并且此属性设置为**False**，则不升级该属性。<br /><br /> 默认值：**False** **注意：** 当 **，则返回 True**，如果指定两个或多个架构，可能会收到错误"两个或多个所选架构共享同一目标命名空间"**文档架构**或**信封架构**属性。|  
  
## <a name="see-also"></a>请参阅  
 [XML 拆装器管道组件](../core/xml-disassembler-pipeline-component.md)   
 [XML 和平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [Pipelines-assemblerdisassembler （BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)