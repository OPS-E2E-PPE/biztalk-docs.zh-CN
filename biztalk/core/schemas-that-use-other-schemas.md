---
title: 使用其他架构的架构 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 02954d46-48ce-4cdf-a012-74c212ce8b6d
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53256b7367e3dd6c6fe5c887d5d312f03db56008
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395566"
---
# <a name="schemas-that-use-other-schemas"></a>使用其他架构的架构

## <a name="overview"></a>概述
当架构变得大而复杂，或者当表示不同类型的实例消息的架构具有某些部分共同点，它可用于将较小的架构合并到最终定义的实例的结构的架构你打算与贸易合作伙伴交换消息。 例如，你可能需要寄送地址，表示为其中的多个消息类型。 您可以在单个架构中定义发货地址的结构，然后使用该架构中定义，例如，订单、 发票和发运通知消息架构的其他架构。  

## <a name="import-include-and-redefine"></a>导入、 包括和重新定义  
 XML 架构定义 (XSD) 语言提供了三种相关的机制来将多个架构一起使用 BizTalk 编辑器支持。 下表总结了一种机制，特征，如由 XSD 定义。  
  
|多架构机制|使用方案|  
|---------------------------|--------------------|  
|导入|-访问和使用导入的架构中定义的类型。<br />-必须在导入的架构，使用类型或派生新类型;不允许的类型修改。<br />-提供用于使用其他命名空间中定义的类型的机制。 实际上，导入的架构必须具有不同于导入架构的目标命名空间。<br />-使用**导入**元素并将其**命名空间**并**schemaLocation**属性以引用其他架构。|  
|包括|-访问和使用包含的架构中定义的类型。<br />-必须使用类型中包含的架构，或从它们; 派生新类型不允许的类型修改。<br />-包含的架构必须是包含架构相同的目标命名空间中或包含的架构的目标命名空间必须为空。<br />-使用**包括**元素并将其**schemaLocation**属性来引用其他架构。|  
|重新定义|-访问，并使用重新定义的架构中定义的类型。<br />-可以重新定义的架构中的使用类型，以及从中派生新类型或指定对其进行修改。<br />-重新定义的架构必须在重新定义的架构相同的目标命名空间或重新定义的架构的目标命名空间必须为空。<br />-使用**重新定义**元素并将其**schemaLocation**属性来引用其他架构。 用指定的任何类型重新定义**重新定义**元素。 **注意：**     使用 redefine 机制是一种高级的 XSD 概念和仅用于已充分了解如何以及何时应使用它。|  
  
> [!NOTE]
>  有关差异和相似之处之间导入的完整信息，包括，和 redefine 机制，请参阅中列出的参考资料[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  

## <a name="important-details"></a>重要详细信息  
 若要使用另一个架构 (Schema2) 中的一个架构 (Schema1) 中定义的类型，必须提供对 Schema1 Schema2 中的引用。 若要执行此操作，请使用**导入**的属性**架构**Schema2 中的节点。 单击省略号 (**...**) 按钮**导入**属性字段**导入**对话框随即打开。 中**导入新的架构作为**下拉列表中，选择**XSD 导入**， **XSD Include**，或者**XSD Redefine**。 然后单击**外**以打开**BizTalk 类型选取器**对话框并选择在 BizTalk 项目中的浏览**Schema1**。  
  
 有关这些步骤的详细说明，请参阅[创建使用其他架构的](../core/how-to-create-schemas-that-use-other-schemas.md)。  
  
 当你使用**导入**对话框可以导入、 包括或重新定义其他架构、 一个或多个 XSD 元素**导入**，**包括**，和**重新定义**添加到您的架构，包括适当的属性和属性值的 XSD 表示形式。 更多的情况下**导入**元素，其他架构的命名空间前缀声明添加到**架构**元素。  
  
 所有全局类型 (如**ComplexTypes**， **SimpleTypes**，元素组、 特性组) 导入/包括/重新定义架构中将自动可供使用的架构中导入、 包括前, 一架构，或重新定义。 例如，全局**ComplexTypes**导入/包括/重新定义架构中定义添加到下拉列表**Data Structure Type**的所有属性**记录**导入、 包括或重新定义架构中的节点。 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>请参阅  
 [有关架构](../core/about-schemas.md)   
 [创建使用其他架构的架构](../core/how-to-create-schemas-that-use-other-schemas.md)   
 [创建对其他节点或类型的引用](../core/how-to-create-references-to-another-node-or-type.md)