---
title: Framework 组装器管道配置为 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2fd51047-b9dd-4b98-a968-45d69148664e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9be5eae765fbcdda9bb26f31a674d996e6200216
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386190"
---
# <a name="configure-the-biztalk-framework-assembler-pipeline-component"></a>配置 BizTalk 框架组装器管道组件
  
1.  将 BizTalk 框架组装器管道组件拖至发送管道的组装阶段。  
  
2.  在属性窗口中**管道组件属性**部分中，设置以下属性值。  
  
    |使用此选项|执行的操作|  
    |--------------|----------------|  
    |**添加处理指令文本**|允许已组装的 XML 文档作为此属性的值包含处理指令。 这也允许文档包含用于应用程序的说明。 **注意：** 处理指令文本应符合 W3C XML 处理指令标准。 <br /><br /> 默认值：追加|  
    |**添加 XML 声明**|将 XML 声明添加到传出消息。 为 true 时，向传出消息添加以下 XML 声明： `<?xml version='1.0' encoding='UTF8'>`。 指定的编码取决于由携带编码信息的特定运行时属性，BizTalk 框架组装器所使用的编码。<br /><br /> 默认值：**True**|  
    |**送达回执地址**|指定应发送到 BizTalk 框架文档的送达回执的地址。 警告：使用 BizTalk 框架组装器使用已启用的确认，时确认处理可能会导致死锁积压的机会。 按一条消息的不同批次处理多个确认时，将发生死锁。 若要避免此问题应该配置批大小为 1。 对于输入的送达回执地址端口位置。|  
    |**送达回执地址类型**|指定应发送 BizTalk 框架文档的送达回执地址类型。<br /><br /> 默认值： biz:**注意：** Biz： 前缀用于表示在 BizTalk Server 中的源和目标终结点和互操作性与这两个系统的组织标识符。 默认情况下提供前缀。 例如，键入 ="biz: OrganizationName"，(src&#124;dest) ="Party1"。|  
    |**按时间发送送达回执**|由 BizTalk 框架文档的送达回执必须接收指定的时间 （以分钟为单位）。<br /><br /> 默认值：30|  
    |**目标地址**|指定的目标地址。<br /><br /> 默认值：None|  
    |**目标地址类型**|指定目标地址类型。<br /><br /> 默认值： biz:**注意：** Biz： 前缀用于表示在 BizTalk Server 中的源和目标终结点和互操作性与这两个系统的组织标识符。 默认情况下提供前缀。 例如，键入 ="biz: OrganizationName"，(src&#124;dest) ="Party1"。|  
    |**文档架构**|指示命名空间和类型名或多个架构应用于文档。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。 **注意：** 如果指定两个或多个架构，可能会收到错误"两个或多个所选架构共享同一目标命名空间"**文档架构：** 属性。 <br /><br /> 默认值：空集合|  
    |**文档主题**|标识唯一标识 BizTalk 框架文档的全部用途的 URI 引用。<br /><br /> 默认值：None|  
    |**信封架构**|指示命名空间和类型名或多个将应用于信封的架构。 有关详细信息，请参阅[如何使用架构集合属性编辑器](../core/how-to-use-the-schema-collection-property-editor.md)。 **注意：** 如果指定两个或多个架构，可能会收到错误"两个或多个所选架构共享同一目标命名空间"**信封架构**属性。 <br /><br /> 默认值：BTF2Schemas.btf2_envelope|  
    |**生成送达回执请求**|指示是否应生成 BizTalk 框架文档的送达回执请求。 这用于启用可靠消息传送的 BizTalk 框架。<br /><br /> 默认值：**True**|  
    |**消息生存时间 （以分钟为单位）**|指定消息保持有效的时间 （以分钟为单位）。<br /><br /> 默认值：30|  
    |**处理指令**|指定如何在 XML 实例文档中处理 XML 处理指令。<br /><br /> **追加**:值**添加处理指令文本**应附加到预先存在的消息中的处理指令。<br /><br /> **创建新的**:值**添加处理指令文本**中输入该字段应覆盖或替换已存在的任何消息中的处理指令。<br /><br /> 如果**创建新**已选中**添加处理指令文本**必须包含有效的处理指令。<br /><br /> **忽略**:如果存在处理指令文本消息中，它将被删除。<br /><br /> 默认值：**追加**|  
    |**源地址**|指定的源地址。<br /><br /> 默认值：None|  
    |**源地址类型**|指定源地址类型。<br /><br /> 默认值： biz:**注意：** Biz： 前缀用于表示在 BizTalk Server 中的源和目标终结点和互操作性与这两个系统的组织标识符。 默认情况下提供前缀。 例如，键入 ="biz: OrganizationName"，(src&#124;dest) ="Party1"。|  
    |**目标字符集**|指定用于编码的传出消息的目标字符集。<br /><br /> 默认值：None|  
  
## <a name="see-also"></a>请参阅  
 [BizTalk 框架组装器管道组件](../core/biztalk-framework-assembler-pipeline-component.md)   
 [配置本地管道组件](../core/configuring-native-pipeline-components.md)   
 [Pipelines-AssemblerDisassembler（BizTalk Server 示例文件夹）](../core/pipelines-assemblerdisassembler-biztalk-server-samples-folder.md)