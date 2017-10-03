---
title: "所有组节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0e28d98c-746a-44d8-bed2-ba539b8432aa
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f51d6420b7d754ffb8706e2bc729a02df00b4338
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="all-group-nodes"></a>“全部组”节点
在 BizTalk 编辑器中，你可以插入**所有组**节点包含其他节点将出现零次或一次，按任何顺序。 在 XML 架构定义 (XSD) 语言中，**所有组**具有比的详细使用情况限制**序列**和**选择**组，将转换为中的几种情况下其中你将能够创建 BizTalk 编辑器**所有组**节点。  
  
 若要使用**所有组**节点在 BizTalk 编辑器中，你需要执行一些额外步骤： 创建的最简单办法**所有组**节点是更改的值**组顺序类型**父属性**记录**节点**所有**。 这样可确保所有的从属节点**记录**节点都包含在**所有组**节点。  请参阅**组顺序类型** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
 使用另一种**所有组**开头插入一个新节点在 BizTalk 编辑器**记录**节点。 在插入新后**记录**节点，更改其**内容类型**属性**ComplexContent**。 然后你可以将插入**所有组**节点的子级作为**记录**节点。 这是必需的因为**所有组**只能当继承涉及到插入。 通过指定包含**记录**节点包含复杂内容，其数据类型将成为基于数据类型**xs: anytype**派生的扩展。  
  
> [!NOTE]
>  在 BizTalk 编辑器中，**所有组**节点表示以字符串\<所有 > 架构树视图中。 如果引用设置为**所有组**节点，如到 x，它会表示为\<组： x > 架构树视图中。  
  
## <a name="xsd-representation"></a>XSD 表示形式  
 **所有组**节点可以插入到**记录**节点，但仅当它是唯一的非属性子节点的**记录**节点。 下面的示例显示，在步骤中，如何新**所有组**节点表示 XML 架构定义 (XSD) 语言**所有**元素作为 BizTalk 编辑器中的步骤执行 （具有名为的节点若要阐明其标识）。  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType />   
</xs:element>  
```  
  
 在前面的 XSD 片段中，所示添加一条新记录后其**内容类型**属性更改为**ComplexContent**，从而导致以下 XSD 修改。  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
             <xs:extension base="xs:anyType" />  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  
  
 现在**所有组**可以作为新的记录的子级插入节点，如下面的 XSD 段中所示。  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
            <xs:extension base="xs:anyType">  
                <xs:all />   
             </xs:extension>  
          </xs:complexContent>  
     </xs:complexType>  
</xs:element>  
```  
  
 最后，可以作为新的子级插入相应的节点**所有组**节点。 下面的示例演示**记录**节点和**Field 元素**节点作为新的子节点插入**所有组**节点。  
  
```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
            <xs:extension base="xs:anyType">  
                <xs:all>  
                    <xs:element name="RecordChildOfAllGroup">  
                        <xs:complexType />  
                    </xs:element>  
                    <xs:element name="FieldElementChildOfAllGroup" type="xs:string" />  
                </xs:all>  
            </xs:extension>  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  
  
## <a name="see-also"></a>另请参阅  
-  [BizTalk 表示形式架构](../core/biztalk-representation-of-schemas.md)   
-  [节点属性](../core/node-properties.md)   
-  **序列组节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] 
-  [如何设置节点属性](../core/how-to-set-node-properties.md)