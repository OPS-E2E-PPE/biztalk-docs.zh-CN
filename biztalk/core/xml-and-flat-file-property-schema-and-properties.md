---
title: XML 和平面文件属性架构和属性 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1d917b82-62c6-489f-99a9-97e429b6f7c0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b26340ca16435ba7900d2d4bc4ffb42cee803622
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399388"
---
# <a name="xml-and-flat-file-property-schema-and-properties"></a>XML 和平面文件属性架构和属性
**http://schemas.microsoft.com/BizTalk/2003/xmlnorm-properties** 命名空间包含可用于配置平面文件组装器和平面文件拆装器管道组件的属性。 下表中所介绍的属性。  

## <a name="properties-list"></a>属性列表

|属性|类型|Description|  
|--------------|----------|-----------------|  
|**FlatFileHeaderDocument**|xs:string|标头的传入的平面文件文档可以存储与此属性。|  
|**AllowUnrecognizedMessage**|xs:Boolean|指定 XML 组件是否应处理无法识别的消息。|  
|**ProcessingInstruction**|xs:string|传出文档的处理指令文本。|  
|**DocumentSpecName**|xs:string|要用于解析或序列化文档的 XML 组件的架构。<br /><br /> 此属性中指定的架构应具有唯一的目标命名空间 # 根。 如果任何架构具有相同的命名空间 # 根，文档实例的验证可能不会按预期工作。 命名空间 # 根必须是唯一的。  如果架构必须具有相同的命名空间 # 根，则应创建单独的管道为每个架构和指定每个 XML 拆装器管道组件的一个架构，或使用一个管道但不是指定任何架构作为参数的 XML 拆装器管道组件。  如果没有目标命名空间，这还将工作。|  
|**EnvelopeSpecName**|xs:string|针对要用于解析或序列化文档的 XML 组件的信封规范。<br /><br /> 此属性中指定的架构应具有唯一的目标命名空间 # 根。 如果任何架构具有相同的命名空间 # 根，文档实例的验证可能不会按预期工作。 命名空间 # 根必须是唯一的。  如果架构必须具有相同的命名空间 # 根，则应创建单独的管道为每个架构和指定每个 XML 拆装器管道组件的一个架构，或使用一个管道但不是指定任何架构作为参数的 XML 拆装器管道组件。  如果没有目标命名空间，这还将工作。|  
|**TargetCharset**|xs:string|要用于输出消息编码的 XML 组件的字符集。|  
|**SourceCharset**|xs:string|使用的字符集编码由 XML 拆装器处理之前的文档。|  
|**ProcessingInstructionOption**|xs:int|指定如何向传出文档添加处理指令。 有关 ProcessingInstructionOption 的详细信息，请参阅[XML 组装器管道组件中处理指令](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)。|  
|**AddXMLDeclaration**|xs:boolean|指定是否应该向传出文档添加 XML 声明。|  
|**HeaderSpecName**|xs:string|指定平面文件文档标头。|  
|**TrailerSpecName**|xs:string|指定平面文件文档尾部。|  
|**PromotePropertiesOnly**|xs:boolean|如果设置为 **，则返回 True**，XML 拆装器组件不会删除消息信封或其拆装。 执行仅属性升级操作。|  

## <a name="see-also"></a>请参阅  
- [配置平面文件汇编程序管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)   
- [配置平面文件反汇编程序管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
- [配置 XML 汇编程序管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
- [配置 XML 反汇编程序管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)   
- [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
- **消息上下文属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
