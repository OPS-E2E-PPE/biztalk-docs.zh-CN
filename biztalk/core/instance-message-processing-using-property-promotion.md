---
title: 实例消息处理使用属性提升 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 753571b8-4609-4ac4-a974-8bd6dfecb077
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 288657d43443582c5a05df5dd6e67059eca572e9
ms.sourcegitcommit: 36350889f318e1f7e0ac9506dc8df794d475bda6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2018
---
# <a name="instance-message-processing-using-property-promotion"></a>使用属性升级处理实例消息
将属性提升使用 **属性字段** 方法，则需要创建的属性架构。 有关创建属性架构的详细信息，请参阅[如何创建属性架构](../core/how-to-create-property-schemas.md)。 因为所有属性提升，与你使用 **升级属性** 对话框中，这是可访问通过使用 **升级属性** 属性 **架构** 消息架构中的节点。  
  
> [!NOTE]
>  您必须选择升级属性的管道，以便访问和使用升级属性。 例如，如果您使用 PassthruReceive 管道，将不会升级任何属性；因此，基于内容的路由和其他功能将无法按预期使用。  
  
 在 **升级属性** 对话框框中，请确保 **属性字段** 在对话框中的右侧选择选项卡。 接下来，请确保相应的属性架构包含在顶部的属性架构列表 **属性字段** 选项卡。如有必要，使用文件夹按钮通过选择适当的属性架构**BizTalk 类型选取器**对话框。 接下来，展开以查找并选择对话框左侧的架构树中节点 **Field 元素** 节点或 **字段特性** 你想要将提升为的属性字段中，然后单击的节点 **添加**。 最后，使用下拉列表中的 **属性** 列 **属性字段字典** 表选择 **Field 元素** 属性架构与之关联的提升的属性中的节点。 有关升级到使用的属性字段的属性的分步说明**升级属性**对话框 ox，请参阅[如何将数据复制到作为属性字段消息上下文](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)。  
  
> [!NOTE]
>  你还可以升级 **记录** 节点 **Field 元素** 中属性的架构，但仅当节点 **内容类型** 属性 **记录** 节点设置为 **SimpleContent**。  
  
> [!NOTE]
>  在一个架构中，可以对同一属性升级多次，只要所有这些升级都是在不同的根节点下进行即可。 这是因为消息是根据单个根节点进行验证的，只有在该根节点下升级的属性才会在运行时进行评估。  
  
 若要删除 **Field 元素** 节点或 **字段特性** 节点的属性字段会提升的属性集从选择中的提升的属性 **属性字段字典** 表上 **属性字段** 选项卡上，并依次 **删除**。  
  
 **节点路径** 中的列 **属性字段字典** 表显示为对应于提升的属性的架构节点的 XPath。 你可以通过直接编辑此值 **编辑实例 XPath** 对话框。 你可以打开此对话框中，通过单击省略号 (**...**) 时选择该单元格将显示在相应的单元格右侧的按钮。 在直接编辑 XPath 值时必须谨慎，因为如果 BizTalk 编辑器无法解析 XPath，则会妨碍相应的验证操作。  
  
 BizTalk 编辑器还提供简化的命令，可提升属性使用 **属性字段** 机制。 此命令称为快速升级，它是可通过 **Promote & #124;快速升级** BizTalk 和快捷菜单上的命令。 此命令将升级所选 **字段** 节点 (或 **记录** 节点) 在指定的属性架构中自动创建的属性字段 **默认属性架构名称** 中的属性 **属性页** 包含架构的对话框。 有关将升级到使用快速升级命令的属性字段的属性的分步说明，请参阅[如何将数据复制到作为属性字段消息上下文](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)。  
  
 在使用属性字段机制升级属性时，将会向消息架构的 XSD 表示形式中添加两个 XML 架构定义 (XSD) 语言片段。 第一个 XSD 片段是与关联的批注片段 **架构** 标识相应的属性架构，如以下示例所示的元素︰  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:imports>  
            <b:namespace prefix="ns0"  
                uri="http://BizTalk_Server_Project1.PropertySchema1"  
                location=".\propertyschema1.xsd" />  
        </b:imports>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
 第二个 XSD 片段是与关联的批注片段 **根** （无论是否它已被重命名） 的元素，它标识 **Field 元素** 节点或 **字段特性** 已提升使用属性的节点值字段机制，如以下示例所示︰  
  
```  
<xs:annotation>  
    <xs:appinfo>  
        <b:properties>  
            <b:property name="ns0:PromProp1"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/@*[local-  
                 name()='Field_x0020_1']" />  
            <b:property name="ns0:PromProp2"  
                xpath="/*[local-name()='Root' and namespace-  
                 uri()='http://BizTalk_Server_Project1.Schema2']/  
                 *[local-name()='MyRec1']/*[local-  
                 name()='ProgramManager']/*[local-name()='Name']" />  
        </b:properties>  
    </xs:appinfo>  
</xs:annotation>  
```  
  
## <a name="see-also"></a>另请参阅  
 [使用与控件消息处理的消息内容的方法](../core/ways-to-use-message-content-to-control-message-processing.md)   
 [如何将数据复制到作为属性字段的消息上下文](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)