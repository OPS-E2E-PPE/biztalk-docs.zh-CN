---
title: 如何插入的任何元素或属性的任何节点 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4cbfdc04-6c83-4639-82de-169b6f009a2e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 913d7d0c68d61df1c457dd22500a9e4a8d90ec68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22253957"
---
# <a name="how-to-insert-an-any-element-or-any-attribute-node"></a>如何插入任何元素或任何属性节点
BizTalk 编辑器支持两种类型的任何节点： **Any 元素**和**任何属性**。 使用这些节点，您可以在架构中创建与相应实例消息中的位置对应的位置，您不知道哪些元素或属性会出现在这些位置。 有关如何在处理实例消息时解释这些节点的详细信息，请直接参阅 Web 上有关 XML 架构定义 (XSD) 语言的信息。 此信息的链接，请参阅[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  
  
## <a name="insert-an-any-element-node-or-an-any-attribute-node"></a>插入的任何元素节点或任何属性节点  
  
1.  在架构树视图中，选择**记录**你想要插入到其中的节点**Any 元素**节点或**任何属性**节点。  
  
2.  上**BizTalk**菜单上，指向**插入架构节点**，然后单击**Any 元素**或**任何属性**适当。  
  
> [!IMPORTANT]
>  设置**过程内容**属性**Lax**为**Any 元素**或**任何属性**节点可能无法正常工作。 将验证传递上**Any 元素**或**任何属性**节点，将属性设置为**跳过**。  此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
>
>  若要创建包含地图**Any 元素**或**任何属性**节点，则必须使用[大容量复制](mass-copy-functoid.md)functoid 或[脚本](scripting-functoid.md)functoid （具有内联 XSLT 或内联 XSLT 调用模板） 来执行映射，使此类节点，或只需将这些节点不映射。  
  
## <a name="see-also"></a>另请参阅  
-  [将节点插入到架构](../core/inserting-nodes-into-a-schema.md)
- **Functoid 引用**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]