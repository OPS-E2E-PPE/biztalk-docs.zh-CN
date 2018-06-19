---
title: 任何元素节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c7e30fcf-31bc-4d48-9bc7-0be90e927127
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f556a5629fd98d910cbbbd83632ac1a6a1702e74
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25963691"
---
# <a name="any-element-nodes"></a>“任何元素”节点
在 BizTalk 编辑器中，你可以使用**Any 元素**节点以指示实例消息中的未知的元素可能出现的位置。 这适用于以下情况：您知道某个元素可能会出现在实例消息内的特定位置，但不知道该元素的名称或其可能的复杂程度。 如果你将放置**Any 元素**在架构中，BizTalk 适当的位置的节点可以处理此类未知的部分消息。 唯一的要求是相应的 XML 应具有正确的格式。  
  
> [!NOTE]
>  在 BizTalk 编辑器中， **Any 元素**节点表示以字符串\<任何\>架构树视图中。  
  
> [!NOTE]
>  你可以控制到未知消息部分进行验证格式正确的 XML 使用程度**过程内容**属性。 在许多情况下，你可能需要设置**过程内容**属性**跳过**实例消息的位置处的内容**Any 元素**要处理的节点。 保留的默认值**Strict**为**过程内容**属性将阻止从传递的实例消息验证。  
> 
> 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="xsd-representation"></a>XSD 表示形式  
 当**Any 元素**节点添加到**记录**节点，或到另一个节点，它可以添加到如**序列组**，**选项组**，或**所有组**节点，单个 XML 标记添加到相应的 XML 架构定义 (XSD) 语言架构表示形式。 在下面的示例中，新**Any 元素**节点，粗体类型中显示其 XSD 表示形式，但已添加到现有**记录**已包含的节点**Field 元素**节点。  
  
```  
<xs:element name="ExistingRecord">  
    <xs:complexType>  
        <xs:sequence>  
             <xs:element name="ExistingFieldElement" type="xs:string" />  
            <xs:any />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
```  
  
 假设**过程内容**属性**Any 元素**节点设置为**跳过**中实例消息受此架构片段， **ExistingRecord**元素应包含**ExistingFieldElement**元素，其中包含字符串数据后, 跟任意复杂度的任何单个元素。  
  
## <a name="see-also"></a>另请参阅  
 [BizTalk 表示形式架构](../core/biztalk-representation-of-schemas.md)   
 [节点属性](../core/node-properties.md)   
 [如何设置节点属性](../core/how-to-set-node-properties.md)   
 [“任何属性”节点](../core/any-attribute-nodes.md)