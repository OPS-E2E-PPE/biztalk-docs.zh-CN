---
title: "序列组节点 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 139c3daa-a682-4bf7-bbb7-b5694ced0431
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b92c2165a84e5d539eac434ab140389c145b24b4
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="sequence-group-nodes"></a>“顺序组”节点

## <a name="overview"></a>概述
在 BizTalk 编辑器中，你可以插入**序列组**节点包含必须出现在与中出现的顺序相同实例消息中其他节点**序列组**节点。 包含的节点必须是与 XML 元素对应的节点，但不能是与 XML 属性对应的节点。  
  
> [!NOTE]
>  在 BizTalk 编辑器中，**序列组**节点表示默认情况下，使用字符串\<序列\>架构树视图中。 如果引用设置为**序列组**节点，如 x，则它会表示为\<组： x\>架构树视图中。  
  
 你可能想要添加**序列组**若要声明全局元素组。  
  
 可能需要为 XML 创建架构，如下所示：  
  
```  
<Root>  
    <Record1>  
        <GroupItem1/>  
        <GroupItem2/>  
        <NotAGroupItem>  
    </Record1>  
    <Record2>  
        <GroupItem1/>  
        <GroupItem2/>  
    </Record2>  
</Root>  
  
```  
  
 由于在两种情况下都存在 GroupItem1 和 GroupItem2，因此可以声明一个既是 Record1 的子项又是 Record2 的子项的全局顺序组。 有关如何声明一个全局序列组的分步说明，请参阅[对另一个节点或类型创建引用](../core/how-to-create-references-to-another-node-or-type.md)。  
  
 用户可以更改为的隐藏的组**选项组**节点或**所有组**节点 (因此它不一定是**序列组**节点) 通过更改**组顺序类型**属性。 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="xsd-representation"></a>XSD 表示形式  
 当**序列组**节点插入到**记录**节点，它将在任何其他子节点的末尾插入**序列**，**选择**，或**所有**中的元素**记录**节点。 下面的示例演示一个新**序列组**节点中的粗体类型，在末尾插入**序列**中的元素**记录**节点 (节点名为以阐明其标识）。  
  
```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  
  
```  
  
## <a name="see-also"></a>另请参阅  
-  [架构的 BizTalk 表示形式](../core/biztalk-representation-of-schemas.md)   
-  [节点属性](../core/node-properties.md)   
-  **序列组节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
-  [如何设置节点属性](../core/how-to-set-node-properties.md)