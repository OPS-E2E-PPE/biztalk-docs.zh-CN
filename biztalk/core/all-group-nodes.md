---
title: 所有节点进行分组 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0e28d98c-746a-44d8-bed2-ba539b8432aa
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 084b12f16e72507a7d5568bdee022925eca52c0e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989230"
---
# <a name="all-group-nodes"></a>“全部组”节点
在 BizTalk 编辑器中，可以插入**全部组**节点可包含零个或一个时，按任意顺序将出现其他节点。 在 XML 架构定义 (XSD) 语言中，**所有组**具有更多的使用情况限制比**序列**并**选择**组，这会转换为内，这样的情况BizTalk 编辑器中，你将能够创建**全部组**节点。  

 若要使用**全部组**节点在 BizTalk 编辑器中，你需要遵循一些额外的步骤： 创建的最简单办法**全部组**节点是将的值更改**Group Order Type**属性的父**记录**节点到节点**所有**。 这可确保所有的从属节点**记录**节点中包含**全部组**节点。  请参阅**组顺序类型** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

 另一种方法使用**全部组**节点在 BizTalk 编辑器中首先插入一个新**记录**节点。 插入新后**记录**节点，更改其**内容类型**属性设置为**ComplexContent**。 然后可以插入**全部组**节点的子级作为节点**记录**节点。 这是必需的因为**全部组**仅涉及继承时，要插入。 通过指定包含**记录**节点包含复杂内容，其数据类型将变为基于的数据类型**xs: anytype**、 通过扩展派生。  

> [!NOTE]
>  在 BizTalk 编辑器中，**全部组**节点表示的字符串\<所有 > 架构树视图中。 如果引用设置为**全部组**节点，例如为 x，它表示为\<Group: x > 架构树视图中。  

## <a name="xsd-representation"></a>XSD 表示形式  
 **全部组**节点可以插入到**记录**节点，但只有它的唯一非属性子节点**记录**节点。 下面的示例所示，在步骤中，一个新的方式**全部组**节点以 XML 架构定义 (XSD) 语言表示**所有**元素与在 BizTalk 编辑器中的步骤执行 （具有节点名分别为以说明其标识）。  

```  
<xs:element name="NewRecord">  
    <xs:complexType />   
</xs:element>  
```  

 按照以上 XSD 片断中, 所示添加新记录后其**内容类型**属性更改为**ComplexContent**，从而导致以下 XSD 修改。  

```  
<xs:element name="NewRecord">  
    <xs:complexType>  
        <xs:complexContent mixed="false">  
             <xs:extension base="xs:anyType" />  
        </xs:complexContent>  
    </xs:complexType>  
</xs:element>  
```  

 现在**全部组**中以下 XSD 片断所示，可以为新记录的子级插入节点。  

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

 最后，可以插入相应的节点作为新的子级**全部组**节点。 下面的示例演示**记录**节点和一个**Field 元素**节点作为新的子节点插入**全部组**节点。  

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

## <a name="see-also"></a>请参阅  
- [架构的 BizTalk 表示形式](../core/biztalk-representation-of-schemas.md)   
- [节点属性](../core/node-properties.md)   
- **序列组节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)] 
- [如何设置节点属性](../core/how-to-set-node-properties.md)
