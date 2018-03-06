---
title: "配置框架汇编程序管道 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fd51047-b9dd-4b98-a968-45d69148664e
caps.latest.revision: 
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8816d021c49de2b683471246d4d0fa89cd003af7
ms.sourcegitcommit: 32f380810b90b70e5df7be72a6a14988a747868e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2018
---
# <a name="configure-the-biztalk-framework-assembler-pipeline-component"></a>配置 BizTalk Framework 汇编程序管道组件
  
1.  将 BizTalk 框架组装器管道组件拖至发送管道的组装阶段中。  
  
2.  在属性窗口中，在 **管道组件属性** 部分中，设置以下属性值。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**添加处理指令文本**|允许装配的 XML 文档为此属性的值包含处理指令。 这也允许文档包含应用程序的指令。 **注意︰**  处理指令文本应符合 W3C XML 处理指令标准。 <br /><br /> 默认值︰ 追加|  
    |**添加 XML 声明**|将 XML 声明添加到传出消息。 为 true 时，下面的 XML 声明将添加到传出消息︰ `<?xml version='1.0' encoding='UTF8'>`。 指定的编码取决于使用 BizTalk Framework 汇编程序遵循执行编码的信息的特定运行时属性的编码。<br /><br /> 默认值︰ **True**|  
    |**送达回执地址**|指定应向其发送 BizTalk 框架文档的送达回执的地址。 **警告︰**  与启用的确认中使用 BizTalk Framework 汇编程序，时，确认处理可能出现囤积导致死锁的机会。 在不同的批中处理一条消息的多个确认时会发生死锁。 若要避免出现此问题，您应将输入的送达回执地址端口位置的批大小配置为 1。|  
    |**送达回执地址类型**|指定应向其发送 BizTalk Framework 文档的送达回执的地址类型。<br /><br /> 默认值： biz:**注意：** biz： 前缀用于表示在 BizTalk Server 中的源和目标终结点和与这些系统的互操作性的组织标识符。 该前缀是作为默认值提供的。 例如，键入 ="biz︰ 单位名称"，(src &#124; dest) ="Party1"。|  
    |**按时间发送送达回执**|指定必须在多长时间内收到 BizTalk 框架文档的送达回执（以分钟计）。<br /><br /> 默认值︰ 30|  
    |**目标地址**|指定目标地址。<br /><br /> 默认值： 无|  
    |**目标地址类型**|指定目标地址类型。<br /><br /> 默认值： biz:**注意：** biz： 前缀用于表示在 BizTalk Server 中的源和目标终结点和与这些系统的互操作性的组织标识符。 该前缀是作为默认值提供的。 例如，键入 ="biz︰ 单位名称"，(src &#124; dest) ="Party1"。|  
    |**文档架构**|指明要应用于文档的一个或多个架构的命名空间和类型名。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。 **注意︰**  如果你指定两个或多个架构，可能会收到"两个或多个所选架构共享相同的目标命名空间"的错误 **文档架构** 属性。 <br /><br /> 默认值：空集合|  
    |**文档主题**|标识唯一地标识 BizTalk 框架文档的全部用途的 URI 引用。<br /><br /> 默认值： 无|  
    |**信封架构**|指示命名空间和架构或将应用于信封的架构的类型名称。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。 **注意︰**  如果你指定两个或多个架构，可能会收到"两个或多个所选架构共享相同的目标命名空间"的错误 **信封架构** 属性。 <br /><br /> 默认值：BTF2Schemas.btf2_envelope|  
    |**生成请求返回送达回执**|指明是否应生成 BizTalk 框架文档的送达回执请求。 此选项用于为 BizTalk 框架启用可靠的消息传送。<br /><br /> 默认值︰ **True**|  
    |**消息 （以分钟为单位） 生存时间**|指定消息保持有效的总时间（以分钟计）。<br /><br /> 默认值︰ 30|  
    |**处理指令**|指定在 XML 实例文档中如何处理 XML 处理指令。<br /><br /> **追加**︰ 的值 **添加处理指令文本** 应附加到预先存在的消息中的处理指令。<br /><br /> **创建新**︰ 的值 **添加处理指令文本** 中输入的字段应覆盖或替换预先存在的任何处理消息中的说明。<br /><br /> 如果 **新建** 选中，则 **添加处理指令文本** 必须包含有效的处理指令。<br /><br /> **忽略**︰ 如果处理指令文本消息中存在，则会删除。<br /><br /> 默认值︰ **追加**|  
    |**源地址**|指定源地址。<br /><br /> 默认值： 无|  
    |**源地址类型**|指定源地址类型。<br /><br /> 默认值： biz:**注意：** biz： 前缀用于表示在 BizTalk Server 中的源和目标终结点和与这些系统的互操作性的组织标识符。 该前缀是作为默认值提供的。 例如，键入 ="biz︰ 单位名称"，(src &#124; dest) ="Party1"。|  
    |**目标 charset**|指定用于传出消息编码的目标字符集。<br /><br /> 默认值： 无|  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk Framework 汇编程序管道组件](../core/biztalk-framework-assembler-pipeline-component.md)   
 [配置本机管道组件](../core/configuring-native-pipeline-components.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)