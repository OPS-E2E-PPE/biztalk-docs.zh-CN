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
ms.openlocfilehash: e0a8343fe49f104cc00622e6489237fde48d0f7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393339"
---
# <a name="sequence-group-nodes"></a>序列组节点

## <a name="overview"></a>概述
在 BizTalk 编辑器中，可以插入**序列组**节点以包含其他节点必须出现在实例消息中出现的相同顺序**序列组**节点。 包含的节点必须是与 XML 元素相对应的节点，但不能为对应于 XML 特性的节点。  

> [!NOTE]
>  在 BizTalk 编辑器中，**序列组**节点的表示方法的字符串的默认\<序列\>架构树视图中。 如果引用设置为**序列组**节点，如 x，它将表示为\<Group: x\>架构树视图中。  

 您可能想要添加**序列组**声明全局元素组。  

 您可能需要为 XML，如下所示创建架构。  

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

 因为 GroupItem1 和 GroupItem2 存在两种情况下，您可能会声明是 Record1 和 Record2 的子项的全局顺序组。 有关如何声明全局顺序组的分步说明，请参阅[到另一个节点或类型创建引用](../core/how-to-create-references-to-another-node-or-type.md)。  

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
