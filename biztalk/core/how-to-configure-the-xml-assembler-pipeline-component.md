---
title: 如何配置 XML 组装器管道组件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- XML Assembler [pipeline component], configuring
- messages, XML documents
- messages, envelopes
- configuring, pipeline components
- pipeline components, XML Assembler
ms.assetid: 6d883819-a1d4-4ad0-b08f-fcd7583134d6
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 738ba6f7baf4291273e85a50d84300fb1edb5008
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65340277"
---
# <a name="how-to-configure-the-xml-assembler-pipeline-component"></a>如何配置 XML 组装器管道组件
XML 组装器管道组件用于从消息发送之前将 XML 文档包装到 XML 信封[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。  
  
### <a name="to-configure-the-properties-for-the-xml-assembler-pipeline-component"></a>若要配置 XML 组装器管道组件的属性  
  
1.  将 XML 组装器管道组件拖至发送管道的组装阶段。  
  
2.  在属性窗口中**管道组件属性**部分中，执行以下操作。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**添加处理指令**|**追加**:值**添加处理指令文本**应附加到预先存在的消息中的处理指令。<br /><br /> **创建新:** 值**添加处理指令文本**中输入该字段应覆盖或替换已存在的任何消息中的处理指令。<br /><br /> 如果**创建新**已选中**添加处理指令文本**必须包含有效的处理指令。<br /><br /> **忽略**:如果存在处理指令文本消息中，它将被删除。<br /><br /> 默认值：**追加**|  
    |**添加处理指令文本**|指定 XML 处理指令，若要添加到目标 XML 文档的开头。 **注意：** 处理指令文本应符合 W3C XML 处理指令标准。 <br /><br /> 默认值：None|  
    |**添加 XML 声明**|当 **，则返回 True**，向传出文档添加类似于以下 XML 声明： `<?xml version='1.0' encoding='UTF-8'>`。 编码取决于目标文档编码在运行时。<br /><br /> 默认值：**True**|  
    |**文档架构**|指示命名空间和类型名或多个架构应用于文档。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。 **注意：** 如果指定两个或多个架构，可能会收到错误"两个或多个所选架构共享同一目标命名空间"**文档架构：** 属性。 <br /><br /> 默认值：空集合|  
    |**信封架构**|指示命名空间和类型名或多个将应用于信封的架构。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。 **注意：** 如果指定两个或多个架构，可能会收到错误"两个或多个所选架构共享同一目标命名空间"**信封架构**属性。 <br /><br /> 默认值：空集合|  
    |**保留字节顺序标记**|指定是否添加字节顺序标记 (BOM) 到组装器组件生成的文档。<br /><br /> 默认值：**True**|  
    |**处理指令作用域**|指定是否在最外层信封上或在文档级别定义处理指令。<br /><br /> 默认值：**文档**|  
    |**目标字符集**|指定用于传出消息进行编码的字符集。<br /><br /> 默认值：None|  
  
## <a name="see-also"></a>请参阅  
 [XML 组装器管道组件](../core/xml-assembler-pipeline-component.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [XML 和平面文件属性架构和属性](../core/xml-and-flat-file-property-schema-and-properties.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)