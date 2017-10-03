---
title: "如何将 XML 汇编程序管道组件配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], configuring
- messages, XML documents
- messages, envelopes
- configuring, pipeline components
- pipeline components, XML Assembler
ms.assetid: 6d883819-a1d4-4ad0-b08f-fcd7583134d6
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3cf69d5bd982571aefcf794d6ad32b0e69499470
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-the-xml-assembler-pipeline-component"></a>如何将 XML 汇编程序管道组件配置
XML 汇编程序管道组件用于在发送从消息之前包装到 XML 包络线的 XML 文档[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
### <a name="to-configure-the-properties-for-the-xml-assembler-pipeline-component"></a>配置 XML 组装器管道组件的属性  
  
1.  将 XML 组装器管道组件拖入发送管道的组装阶段中。  
  
2.  在属性窗口中，在**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**添加处理指令**|**追加**： 值的**添加处理指令文本**应附加到预先存在的消息中的处理指令。<br /><br /> **创建新：**的值**添加处理指令文本**中输入的字段应覆盖或替换预先存在的任何处理消息中的说明。<br /><br /> 如果**新建**选中，则**添加处理指令文本**必须包含有效的处理指令。<br /><br /> **忽略**： 如果处理指令文本消息中存在，则会删除。<br /><br /> 默认值：**追加**|  
    |**添加处理指令文本**|指定 XML 处理指令以将添加到目标 XML 文档的开头。 **注意：**处理指令文本应符合 W3C XML 处理指令标准。 <br /><br /> 默认值： 无|  
    |**添加 XML 声明**|当**True**，将类似于以下 XML 声明添加到传出的文档： `<?xml version='1.0' encoding='UTF-8'>`。 通过在运行时编码集目标文档确定编码。<br /><br /> 默认值： **True**|  
    |**文档架构**|指明要应用于文档的一个或多个架构的命名空间和类型名。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。 **注意：**如果你指定两个或多个架构，可能会收到"两个或多个所选架构共享相同的目标命名空间"的错误**文档架构**属性。 <br /><br /> 默认值：空集合|  
    |**信封架构**|指示命名空间和架构或将应用于信封的架构的类型名称。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。 **注意：**如果你指定两个或多个架构，可能会收到"两个或多个所选架构共享相同的目标命名空间"的错误**信封架构**属性。 <br /><br /> 默认值：空集合|  
    |**保留字节顺序标记**|指定是否向组装器组件所生成的文档添加字节顺序标记 (BOM)。<br /><br /> 默认值： **True**|  
    |**处理指令作用域**|指定处理指令是在最外层信封上定义还是在文档级别上定义。<br /><br /> 默认值：**文档**|  
    |**目标 charset**|指定用于对传出消息进行编码的字符集。<br /><br /> 默认值： 无|  
  
## <a name="see-also"></a>另请参阅  
 [XML 汇编程序管道组件](../core/xml-assembler-pipeline-component.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)   
 [XML、 平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [管道 AssemblerDisassembler （BizTalk Server 示例文件夹中）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)