---
title: 任何属性节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fa2d25bc-3a8f-4fd9-acad-341b8e80c737
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 98cbd0ea288e14b68bc16f5e9a88f636bc229b9d
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014478"
---
# <a name="any-attribute-nodes"></a>“任何属性”节点
在 BizTalk 编辑器中，可以使用**任何属性**节点指示为其零个或多个未知的属性可能会出现的实例消息中的 （已知） 元素。 这适用于以下情况：您知道某特定元素将存在于实例消息中的特定位置，但您不十分确定该元素可能包含哪些属性。 如果将置于**任何属性**节点内的**记录**相关元素与关联的节点，BizTalk 可以处理该元素，并被所有关联的属性的唯一要求语法上正确 (attributeName ="attributeValue")。  
  
> [!NOTE]
>  在 BizTalk 编辑器中，**任何属性**节点表示的字符串\<AnyAttribute\>架构树视图中。  
> 
> [!NOTE]
>  您可以控制向其消息的未知的部分已验证为格式正确的 XML 使用的程度**Process Contents**属性。 在许多情况下，您可能需要设置**Process Contents**属性设置为**跳过**内容的实例消息的位置处**任何属性**要处理的节点. 保留的默认值**Strict**有关**Process Contents**属性将阻止实例消息验证。  
> 
> 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="xsd-representation"></a>XSD 表示形式  
 当**任何属性**节点添加到**记录**节点或**属性组**节点，单个 XML 标记添加到相应的 XML 架构定义 (XSD) 语言架构表示形式。 在以下示例中，一个新**任何属性**节点，显示其 XSD 表示形式中加粗，并且已添加到现有**记录**已包含的节点**字段元素**节点。  
  
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
  
 在前面的示例中，新的 XSD 表示形式**任何属性**节点将添加**anyAttribute**到末尾包含的元素 (**记录**节点) **元素**元素中，外部**序列**元素，就能在**complexType**元素。 这就是所有**特性**元素，而具有非**属性组**节点中，添加到其包含**元素**元素。  
  
 现在，并假定**Process Contents**的属性**任何属性**节点设置为**跳过**，在此架构片断，所控制的实例消息**ExistingRecord**元素预期行为，并且，只要它们是对于 XML 语法格式正确，它可以包含任何属性。 (为了符合在此示例中的 XSD 片断，它必须包含**ExistingFieldElement**元素。)  
  
## <a name="see-also"></a>请参阅  
 [BizTalk 架构表示法](../core/biztalk-representation-of-schemas.md)   
 [节点属性](../core/node-properties.md)   
 [如何设置节点属性](../core/how-to-set-node-properties.md)   
 [“任何元素”节点](../core/any-element-nodes.md)