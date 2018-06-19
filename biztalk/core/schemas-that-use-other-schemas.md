---
title: 使用其他架构的架构 |Microsoft 文档
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
ms.openlocfilehash: 563260031e545b5223697d49992c1ae85bae3891
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22271597"
---
# <a name="schemas-that-use-other-schemas"></a>使用其他架构的架构

## <a name="overview"></a>概述
你的架构变得大而复杂，或表示你不同类型的实例消息的架构的共同点某些部分时，它可用于将较小的架构合并到最终定义结构的实例的架构你打算与贸易合作伙伴交换的消息。 例如，您可能需要在其中表示一个邮寄地址的多个消息类型。 你可以在单个架构中定义的一个邮寄地址的结构，然后使用该架构中定义，例如，顺序、 Invoice 和传送的通知消息架构的其他架构。  

## <a name="import-include-and-redefine"></a>导入，包括，并且重新定义  
 XML 架构定义 (XSD) 语言提供结合使用多个架构的三个相关的机制 BizTalk 编辑器支持。 下表总结了这些机制的特征定义 xsd。  
  
|Multischema 机制|使用方案|  
|---------------------------|--------------------|  
|导入|的访问，并使用在导入的架构中定义的类型。<br />-必须在导入的架构，使用类型或它们; 从其派生新类型不允许的类型修改。<br />-提供有关使用其他命名空间中定义的类型的机制。 事实上，导入的架构必须具有不同于导入架构的目标命名空间。<br />-使用**导入**元素并将其**命名空间**和**schemaLocation**属性来引用的其他架构。|  
|包括|-访问和使用包含的架构中定义的类型。<br />-必须在包含的架构，使用类型或它们; 从其派生新类型不允许的类型修改。<br />-包含的架构必须包括的架构中，相同的目标命名空间中或包含架构的目标命名空间必须为空。<br />-使用**包括**元素并将其**schemaLocation**属性来引用的其他架构。|  
|重新定义|的访问，并使用重新定义架构中定义的类型。<br />-可以重新定义架构中的使用类型按原样，新类型派生，或指定对其进行修改。<br />-重新定义的架构必须重新定义的架构相同的目标命名空间中，或重新定义架构的目标命名空间必须为空。<br />-使用**重新定义**元素并将其**schemaLocation**属性来引用的其他架构。 使用指定了任何类型重新定义**重新定义**元素。 **注意：** 使用重新定义机制是一个高级的 XSD 概念，并且仅用于后必须足够了解如何以及何时应使用。|  
  
> [!NOTE]
>  有关的差异和相似性之间导入的完整信息，包括，和重新定义机制，请参阅中列出的引用[在 Web 上找到的 XSD 资源](../core/xsd-resources-on-the-web.md)。  

## <a name="important-details"></a>重要详细信息  
 若要使用另一个架构 (Schema2) 内的一个架构 (Schema1) 中定义的类型，必须提供对中 Schema2 Schema1 的引用。 为此，请使用**导入**属性**架构**Schema2 中的节点。 当您单击省略号 (**...**) 按钮**导入**属性字段**导入**对话框随即打开。 在**导入的新架构**下拉列表中，选择**XSD 导入**， **XSD 包括**，或**重新定义 XSD**。 然后单击**添加**以打开**BizTalk 类型选取器**对话框并浏览您的 BizTalk 项目选择中**Schema1**。  
  
 有关这些步骤的详细说明，请参阅[创建架构，使用其他架构](../core/how-to-create-schemas-that-use-other-schemas.md)。  
  
 当你使用**导入**对话框中，若要导入，包括，或重新定义另一个架构、 一个或多个 XSD 元素**导入**，**包括**，和**重新定义**添加到你的架构，包括适当的属性和属性值的 XSD 表示。 此外，对于**导入**元素，前缀声明命名空间的其他架构添加到**架构**元素。  
  
 所有全局类型 (如**Complextype**， **SimpleTypes**，元素组、 特性组) 导入/包含/重新定义架构中将自动可供中的架构中使用导入以前的架构，将其包含，或重新定义。 例如，全局**Complextype**导入/包含/重新定义架构中定义添加到下拉列表的**数据结构类型**的所有属性**记录**导入，包括，或重新定义架构中的节点。 此属性的详细信息[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]。
  
## <a name="see-also"></a>另请参阅  
 [有关架构](../core/about-schemas.md)   
 [创建使用其他架构的架构](../core/how-to-create-schemas-that-use-other-schemas.md)   
 [创建到另一个节点或类型的引用](../core/how-to-create-references-to-another-node-or-type.md)