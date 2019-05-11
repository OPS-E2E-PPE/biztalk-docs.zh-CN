---
title: 实例使用属性升级的消息处理 |Microsoft Docs
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
ms.openlocfilehash: df619a7e8ec48565d06f16f4f8acbc5ac81c524f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65331873"
---
# <a name="instance-message-processing-using-property-promotion"></a>使用属性升级处理实例消息
通过使用升级属性**属性字段**方法需要创建属性架构。 有关创建属性架构的详细信息，请参阅[如何创建属性架构](../core/how-to-create-property-schemas.md)。 因为所有属性升级，你都使用**升级属性**对话框中，通过使用可访问该**升级属性**属性**架构**中的节点消息架构。  
  
> [!NOTE]
>  必须选择升级才能访问和使用升级属性的属性的管道。 例如，如果您使用 PassthruReceive 管道，将不升级任何属性;因此，基于内容的路由和其他功能将不按预期工作。  
  
 在中**升级属性**对话框框中，请确保**属性字段**右侧的对话框中选择选项卡。 接下来，确保相应的属性架构包含在属性架构列表的顶部**属性字段**选项卡。如有必要，使用文件夹按钮通过选择相应的属性架构**BizTalk 类型选取器**对话框。 接下来，依次展开对话框中查找并选择左侧的架构树中节点**Field 元素**节点或**字段属性**你想要升级为属性字段，然后单击的节点**添加**。 最后，使用下拉列表中的**属性**的列**属性-字段字典**要选择表**字段元素**中用到的属性架构的节点将升级的属性相关联。 有关将属性升级为属性字段中使用的分步说明**升级属性**对话框 ox，请参阅[如何将数据复制到消息上下文为属性字段](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)。  
  
> [!NOTE]
>  你还可以升级**记录**节点到节点**字段元素**节点中的属性架构，但是只有当**内容类型**属性**记录**节点设置为**SimpleContent**。  
  
> [!NOTE]
>  相同的属性可以将升级多个时间架构内，只要所有这些升级都不同的根节点下执行。 这是因为该消息进行验证的单个根节点和在运行时计算该根节点下升级的唯一属性。  
  
 若要删除**字段元素**节点或**Field 特性**节点的属性升级为属性字段集从选择中的升级的属性**属性-字段字典**表上**属性字段**选项卡，然后依次**删除**。  
  
 **节点路径**中的列**属性-字段字典**表显示了对应于已升级的属性的架构节点的 XPath。 可以通过直接编辑此值**编辑实例 XPath**对话框。 可以通过单击省略号打开此对话框 (**...**) 时选择该单元格将显示在相应的单元格右侧的按钮。 直接编辑 XPath 值，因为无法解析由 BizTalk 编辑器中的 Xpath 将阻止相应的验证操作时必须小心。  
  
 BizTalk 编辑器还提供了简化的命令，对升级属性使用**属性字段**机制。 此命令称为快速升级，它是可通过 **Promote &#124; 快速升级** BizTalk 和快捷菜单上的命令。 此命令将升级所选**字段**节点 (或**记录**节点) 到属性字段中指定的属性架构自动创建**默认属性架构名**中的属性**属性页**包含架构的对话框。 有关将属性升级为属性字段使用快速升级命令的分步说明，请参阅[如何将数据复制到消息上下文为属性字段](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)。  
  
 使用属性字段机制升级属性，当两个 XML 架构定义 (XSD) 语言片段添加到的消息架构的 XSD 表示形式。 第一个 XSD 片断是与关联的批注片断**架构**元素，它标识相应的属性架构，如以下示例所示：  
  
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
  
 第二个 XSD 片断是与关联的批注片断**根**元素 （无论是否它已被重命名），用于标识**Field 元素**节点或**字段属性**已通过使用属性升级的节点值字段机制，如以下示例所示：  
  
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
  
## <a name="see-also"></a>请参阅  
 [使用消息内容控制消息处理方法](../core/ways-to-use-message-content-to-control-message-processing.md)   
 [如何将数据复制到消息上下文为属性字段](../core/how-to-copy-data-to-the-message-context-as-property-fields.md)