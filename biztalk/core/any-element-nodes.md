---
title: 任何元素节点 |Microsoft Docs
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
ms.openlocfilehash: 905d6c25c5c2021840f4257c29df015d4bcb374e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37002430"
---
# <a name="any-element-nodes"></a>“任何元素”节点
在 BizTalk 编辑器中，可以使用**Any 元素**节点指示实例消息中可能出现未知的元素的位置。 这适用于以下情况：您知道某个元素可能会出现在实例消息内的特定位置，但不知道该元素的名称或其可能的复杂程度。 如果将置于**Any 元素**BizTalk 架构中适当的位置的节点可以处理此类未知的消息部分。 唯一的要求是相应的 XML 应具有正确的格式。  
  
> [!NOTE]
>  在 BizTalk 编辑器中， **Any 元素**节点表示的字符串\<任何\>架构树视图中。  
> 
> [!NOTE]
>  您可以控制向其消息的未知的部分已验证为格式正确的 XML 使用的程度**Process Contents**属性。 在许多情况下，您可能需要设置**Process Contents**属性设置为**跳过**内容的实例消息的位置处**Any 元素**要处理的节点。 保留的默认值**Strict**有关**Process Contents**属性将阻止实例消息验证。  
> 
> 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="xsd-representation"></a>XSD 表示形式  
 当**Any 元素**节点添加到**记录**节点，或到另一个节点，它可以添加到如**序列组**，**选择组**，或**全部组**节点，单个 XML 标记添加到相应的 XML 架构定义 (XSD) 语言架构表示形式。 在以下示例中，一个新**Any 元素**节点，其 XSD 表示形式以粗体显示，已被添加到现有**记录**已包含的节点**字段元素**节点。  
  
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
  
 假设**Process Contents**的属性**Any 元素**节点设置为**跳过**，在此架构片断，所控制的实例消息**ExistingRecord**元素应包含**ExistingFieldElement**元素，其中包含字符串数据后, 跟任意复杂程度的任何单个元素。  
  
## <a name="see-also"></a>请参阅  
 [BizTalk 架构表示法](../core/biztalk-representation-of-schemas.md)   
 [节点属性](../core/node-properties.md)   
 [如何设置节点属性](../core/how-to-set-node-properties.md)   
 [“任何属性”节点](../core/any-attribute-nodes.md)