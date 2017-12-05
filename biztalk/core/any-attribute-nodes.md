---
title: "任何属性节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa2d25bc-3a8f-4fd9-acad-341b8e80c737
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 82490a114149e3d4f71e3598900be5599c8a36e2
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="any-attribute-nodes"></a>“任何属性”节点
在 BizTalk 编辑器中，你可以使用**任何属性**节点以指示可能出现零个或多个未知的属性实例消息中 （已知） 元素。 这适用于以下情况：您知道某特定元素将存在于实例消息中的特定位置，但您不十分确定该元素可能包含哪些属性。 如果你将放置**任何属性**中的节点**记录**的相关元素与关联的节点，BizTalk 可以处理该元素，与正在任何关联的属性，唯一的要求语法更正 (attributeName ="attributeValue")。  
  
> [!NOTE]
>  在 BizTalk 编辑器中，**任何属性**节点表示以字符串\<AnyAttribute\>架构树视图中。  
  
> [!NOTE]
>  你可以控制到未知消息部分进行验证格式正确的 XML 使用程度**过程内容**属性。 在许多情况下，你可能需要设置**过程内容**属性**跳过**实例消息的位置处的内容**任何属性**要处理的节点. 保留的默认值**Strict**为**过程内容**属性将阻止从传递的实例消息验证。  
>
> 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="xsd-representation"></a>XSD 表示形式  
 当**任何属性**节点添加到**记录**节点或**属性组**节点，单个 XML 标记添加到相应的 XML 架构定义 (XSD) 语言架构表示形式。 在下面的示例中，新**任何属性**节点，显示其 XSD 表示形式中加粗，并且已添加到现有**记录**已包含的节点**Field 元素**节点。  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
        <xs:anyAttribute />  
    </xs:complexType>  
</xs:element  
```  
  
 在前面的示例中，新的 XSD 表示**任何属性**节点将添加**anyAttribute**到末尾的包含的元素 (**记录**节点) **元素**元素、 外部**序列**元素，就能在**complexType**元素。 这就是所有**属性**元素，而那些具有非**属性组**节点，添加到其包含**元素**元素。  
  
 现在，并假定**过程内容**属性**任何属性**节点设置为**跳过**中实例消息受此架构片段， **ExistingRecord**元素预期行为，而且它可以包含任何属性，只要它们是与 XML 语法格式正确。 (若要符合在此示例中的 XSD 片段，它必须包含**ExistingFieldElement**元素也。)  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk 表示形式架构](../core/biztalk-representation-of-schemas.md)   
 [节点属性](../core/node-properties.md)   
 [如何设置节点属性](../core/how-to-set-node-properties.md)   
 [“任何元素”节点](../core/any-element-nodes.md)