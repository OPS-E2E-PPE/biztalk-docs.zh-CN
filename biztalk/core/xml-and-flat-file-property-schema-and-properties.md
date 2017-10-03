---
title: "XML 和平面文件属性架构和属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1d917b82-62c6-489f-99a9-97e429b6f7c0
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fb69a5375603d307c15a0bf884c924c0f6e6bb31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="xml-and-flat-file-property-schema-and-properties"></a>XML 和平面文件属性架构和属性
**Http://schemas.microsoft.com/BizTalk/2003/xmlnorm-properties**命名空间包含可用于配置平面文件汇编器和平面文件反汇编程序管道组件的属性。 以下表所述的属性。  

## <a name="properties-list"></a>属性列表
  
|属性|类型|Description|  
|--------------|----------|-----------------|  
|**FlatFileHeaderDocument**|xs:string|使用此属性可存储传入平面文件文档的标头。|  
|**AllowUnrecognizedMessage**|xs:Boolean|指定 XML 组件是否应处理无法识别的消息。|  
|**ProcessingInstruction**|xs:string|处理传出文档的指令文本。|  
|**DocumentSpecName**|xs:string|用于解析或序列化文档的 XML 组件的架构。<br /><br /> 此属性中指定的架构应具有唯一目标命名空间 # 根。 如果有任何架构的命名空间 # 根与之相同，则对文档实例的验证将可能无法按预期工作。 命名空间 # 根必须是唯一的。  如果多个架构必须使用同一命名空间 # 根，则应为每个架构创建单独的管道，并为每个 XML 拆装器管道组件指定一个架构，或者只使用一个管道但不将任何架构指定为该 XML 拆装器管道组件的参数。  如果没有目标命名空间，此操作依然有效。|  
|**EnvelopeSpecName**|xs:string|用于解析或序列化文档的 XML 组件的信封规范。<br /><br /> 此属性中指定的架构应具有唯一目标命名空间 # 根。 如果有任何架构的命名空间 # 根与之相同，则对文档实例的验证将可能无法按预期工作。 命名空间 # 根必须是唯一的。  如果多个架构必须使用同一命名空间 # 根，则应为每个架构创建单独的管道，并为每个 XML 拆装器管道组件指定一个架构，或者只使用一个管道但不将任何架构指定为该 XML 拆装器管道组件的参数。  如果没有目标命名空间，此操作依然有效。|  
|**TargetCharset**|xs:string|用于输出消息编码的 XML 组件的字符集。|  
|**SourceCharset**|xs:string|用于在 XML 拆装器处理文档前对文档进行编码的字符集。|  
|**ProcessingInstructionOption**|xs:int|指定向传出文档添加处理指令的方式。 有关 ProcessingInstructionOption 的详细信息，请参阅[处理 XML 汇编程序管道组件中的说明](../core/processing-instructions-in-the-xml-assembler-pipeline-component.md)。|  
|**AddXMLDeclaration**|xs:boolean|指定是否应向传出文档添加 XML 声明。|  
|**HeaderSpecName**|xs:string|指定平面文件文档标头。|  
|**TrailerSpecName**|xs:string|指定平面文件文档尾部。|  
|**PromotePropertiesOnly**|xs:boolean|当设置为**True**，XML 反汇编程序组件不会删除消息信封或反汇编它。 只能执行属性升级操作。|  
  
## <a name="see-also"></a>另请参阅  
-  [配置平面文件汇编管道组件](../core/how-to-configure-the-flat-file-assembler-pipeline-component.md)   
-  [配置平面文件反汇编程序管道组件](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)   
-  [配置 XML 汇编程序管道组件](../core/how-to-configure-the-xml-assembler-pipeline-component.md)   
-  [配置 XML 反汇编程序管道组件](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)   
-  [配置本机管道组件](../core/configuring-native-pipeline-components.md)   
-  **消息上下文属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]