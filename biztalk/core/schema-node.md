---
title: Schema 节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7ea02c2a-ee00-4f44-9086-83d7ac4a8832
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c14658eb48e4031345ec8ce3e9618ef601f5f5ab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396938"
---
# <a name="schema-node"></a>Schema 节点

## <a name="overview"></a>概述
在 BizTalk 编辑器中，架构层次结构的顶层是始终**架构**节点，不能重命名。 **架构**节点对应于**架构**架构的 XML 架构定义 (XSD) 语言表示形式中的元素。  
  
> [!NOTE]
>  在 BizTalk 编辑器中，**架构**节点表示的字符串\<架构\>架构树视图中。  
  
 在常规的属性**架构**节点对应的属性**架构**架构的 XSD 表示形式中的元素。 有关节点属性的常规信息，请参阅[节点属性](../core/node-properties.md)。 有关参考信息的属性**架构**节点，请参阅**Schema 节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 在 BizTalk 编辑器中，创建新的 XML 架构时**架构**节点和一个**根**自动创建节点。  
  
## <a name="xsd-representation"></a>XSD 表示形式  
 以下示例所示，在粗体类型中，对应于架构的 XSD 表示形式中的行**\<架构\>** 架构的树视图中的节点。  
  
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
  
## <a name="see-also"></a>请参阅  
 [BizTalk 架构表示法](../core/biztalk-representation-of-schemas.md)   
 [节点属性](../core/node-properties.md)   
 [设置节点属性](../core/how-to-set-node-properties.md)