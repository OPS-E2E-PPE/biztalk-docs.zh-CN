---
title: "根节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2161f877-835e-434d-a8d1-2426f977d60e
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2070982a6bca09e8bffb2bcc88e5997360c86851
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="root-nodes"></a>根节点
在 BizTalk 编辑器中，子节点的**架构**节点称为**根**节点。 **根**节点是特殊类型的**记录**节点，并且具有比常规的几个更多属性**记录**节点。 **根**节点表示的类型的文档所述的架构，并可以重命名为相应。 例如，你可以重命名**根**节点，以使其描述的架构表示，如 purchaseOrder、 orderAcknowledgment 或 shipNotice 消息的类型。  
  
 在 BizTalk 编辑器中，创建新的 XML 架构时**架构**节点和一个**根**自动创建的节点。 你可以创建其他**根**节点的子级**架构**节点; 这使你可以创建单个的 XML 架构定义 (XSD) 语言表示中的架构的库。 例如，可以创建一个架构库以描述与发送采购订单相关的消息的各种架构，并将多个根节点分别命名为 purchaseOrder、orderAcknowledgment 和 shipNotice。  
  
## <a name="xsd-representation"></a>XSD 表示形式  
 下面的示例显示中对应的架构的 XSD 表示行**根**架构的树视图中的节点。  
  
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
  
 **根**节点在 BizTalk 编辑器代表所涉及的消息的相应 XML 实例中的主要元素。 例如，如果**根**的特定架构的节点已重命名为 purchaseOrder、 相应的 XSD 表示形式具有以下的高级结构。  
  
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
>  根节点可能没有**字段**属性。 **字段**属性附加到**根**节点不会保存具有架构。  
  
## <a name="see-also"></a>另请参阅  
-  [BizTalk 表示形式架构](../core/biztalk-representation-of-schemas.md)   
-  [节点属性](../core/node-properties.md)   
-  **记录节点属性**  [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
-  [如何设置节点属性](../core/how-to-set-node-properties.md)