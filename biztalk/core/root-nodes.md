---
title: 根节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2161f877-835e-434d-a8d1-2426f977d60e
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d8b2746e9e1886b676e656db883579b28898e3d5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019656"
---
# <a name="root-nodes"></a>根节点
在 BizTalk 编辑器中的子节点**架构**节点被称为**根**节点。 **根**节点是特殊类型的**记录**节点，并且具有了几个属性比常规**记录**节点。 **根**节点表示架构所描述的文档类型，可以重命名是根据需要。 例如，你可以重命名**根**节点，以使其描述架构表示的诸如 purchaseOrder、 orderAcknowledgment 或 shipnotice 等消息的类型。  

 在 BizTalk 编辑器中，创建新的 XML 架构时**架构**节点和一个**根**自动创建节点。 您可以创建其他**根**节点的子级作为节点**架构**节点; 这使您可以创建一个库中的单个 XML 架构定义 (XSD) 语言表示形式的架构。 例如，可以创建一个架构库以描述与发送采购订单相关的消息的各种架构，并将多个根节点分别命名为 purchaseOrder、orderAcknowledgment 和 shipNotice。  

## <a name="xsd-representation"></a>XSD 表示形式  
 下面的示例显示行中对应于架构的 XSD 表示形式**根**架构的树视图中的节点。  

```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="Root">  
        <xs:complexType />   
    </xs:element>  
</xs:schema>  
```  

 **根**节点在 BizTalk 编辑器中表示所涉及的消息的相应 XML 实例中的主要元素。 例如，如果**根**特定架构的节点已重命名为 purchaseOrder，相应的 XSD 表示形式具有以下高级结构。  

```  
<?xml version="1.0" encoding="utf-16" ?>  
<xs:schema xmlns="http://BizTalk_Server_Project1.Schema2"  
    xmlns:b="http://schemas.microsoft.com/BizTalk/2003"  
    targetNamespace="http://BizTalk_Server_Project1.Schema2"  
    xmlns:xs="http://www.w3.org/2001/XMLSchema">  
    <xs:element name="">  
        <xs:complexType>   
            ...  
        </xs:complexType>   
    </xs:element>  
</xs:schema>  
```  

 相应的 XML 实例消息必须具有以下基本结构：  

```  
<?xml version="1.0"?>  
<purchaseOrder ...>  
    ...  
</purchaseOrder>  
```  

> [!NOTE]
>  根节点可能没有**字段**属性。 **字段**特性附加到**根**节点将不与架构一起保存。  

## <a name="see-also"></a>请参阅  
- [架构的 BizTalk 表示形式](../core/biztalk-representation-of-schemas.md)   
- [节点属性](../core/node-properties.md)   
- **记录节点属性**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
- [如何设置节点属性](../core/how-to-set-node-properties.md)
