---
title: 序列组节点 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 139c3daa-a682-4bf7-bbb7-b5694ced0431
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c113d0cfd0f6055d55b0329bba3c1ec60bf835e8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37019739"
---
# <a name="sequence-group-nodes"></a>“顺序组”节点

## <a name="overview"></a>概述
在 BizTalk 编辑器中，可以插入**序列组**节点以包含其他节点必须出现在实例消息中出现的相同顺序**序列组**节点。 包含的节点必须是与 XML 元素对应的节点，但不能是与 XML 属性对应的节点。  

> [!NOTE]
>  在 BizTalk 编辑器中，**序列组**节点的表示方法的字符串的默认\<序列\>架构树视图中。 如果引用设置为**序列组**节点，如 x，它将表示为\<Group: x\>架构树视图中。  

 您可能想要添加**序列组**声明全局元素组。  

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

 由于在两种情况下都存在 GroupItem1 和 GroupItem2，因此可以声明一个既是 Record1 的子项又是 Record2 的子项的全局顺序组。 有关如何声明全局顺序组的分步说明，请参阅[到另一个节点或类型创建引用](../core/how-to-create-references-to-another-node-or-type.md)。  

 用户可以更改的隐藏的组要**选择组**节点或**全部组**节点 (因此它不一定是**序列组**节点) 通过更改**组顺序类型**属性。 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。

## <a name="xsd-representation"></a>XSD 表示形式  
 当**序列组**节点插入到**记录**节点中的其他所有子节点结尾处插入该实体**序列**，**选择**，或**所有**中的元素**记录**节点。 下面的示例显示了一个新**序列组**节点，以粗体类型，在末尾处插入**序列**中的元素**记录**节点 (节点命名以说明其标识）。  

```  
<xs:element name="ContainingRecord">  
    <xs:complexType>  
        <xs:sequence>  
            <xs:element name="ExistingFieldElement" type="xs:string" />  
        </xs:sequence>  
    </xs:complexType>  
</xs:element>  

```  

## <a name="see-also"></a>请参阅  
- [架构的 BizTalk 表示形式](../core/biztalk-representation-of-schemas.md)   
- [节点属性](../core/node-properties.md)   
- **序列组节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
- [如何设置节点属性](../core/how-to-set-node-properties.md)
