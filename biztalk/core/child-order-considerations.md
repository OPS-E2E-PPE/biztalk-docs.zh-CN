---
title: "子顺序注意事项 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c4f7aa81-5c08-4932-9e28-31e22e037999
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0909a8d69f5079e493fbc579d6ef4b0ca56f9c61
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="child-order-considerations"></a>子顺序注意事项

## <a name="requirements-for-header-in-a-flat-file"></a>平面文件中的标头的要求
与分隔的平面文件，对于这种特殊的注意事项适用时设置相关的两种方案**子顺序**属性。 第一种此类情况涉及平面文件文档包含头部、正文和尾部（可选）的情况。 在这些情况下，必须遵守以下要求：  
  
-   必须设置**子顺序**（分隔） 根记录的标头到属性**后缀**。  
  
-   如果尾部不存在，则必须设置**子顺序**到正文 （分隔） 根记录的属性**后缀**。  
  
-   如果尾部不存在，则可设置**子顺序**到正文 （分隔） 根记录的属性**前缀**，**中缀**，或**后缀**.  
  
-   如果存在尾部，则可能会设置**子顺序**到该预告片 （分隔） 根记录的属性**前缀**，**中缀**，或**后缀**.  
  
-   您可以设置**子顺序**属性的标头、 正文和到预告片分隔从属记录**前缀**，**中缀**，或**后缀**.  
  
 与第二个方案分隔平面文件和**子顺序**属性是根据运行时组件针对各个节点的期望必须设置此属性。 正确设置**子顺序**属性不可以是明显的根和组节点，如以下方案中所示：  
  
-   **根节点。** 假设一个典型的平面文件，其结构由后跟 CR/LF 组合的记录组成。 分隔符将文件中的记录隔开，并且顺序通常为记录、分隔符、记录、分隔符，以此类推。 在此情况下，分隔符始终遵循的数据，它对应于**子顺序**属性设置的**后缀**。  
  
-   **组节点。** 架构的 BizTalk Server 和 XSD 表示形式中所显示的组节点不会显式存在于实例消息的平面文件表示形式中。 假设一个采购订单 (PO) 包含每个行项目的记录集合，并且这些记录重复多次以表示单个 PO 中的多个行项目。 此类消息的架构可能包含名为 LineItems 以用作重复组 （有时概念） 容器的节点： 在平面文件表示的实例消息中，LineItems 容器是在本质，由表示概念相应的序列的数据和分隔符;实例消息的 XML 表达形式，LineItems 容器位于显式的窗体**LineItems**中 XML 元素。  
  
 假设某消息包含一个根节点并且只有一个组节点。 可以很容易地看出输入流中最后一个分隔符将属于根节点。 因此，概念循环中的数据/分隔符序列只会是一个或多个行项目记录。 只有当存在多个行项目记录时，才会使用分隔符将其隔开。 在这种情况下，分隔符数少于要分隔的对象总数，并且在称为中缀的结构中，分隔符位于所分隔的项目之间。  
  
## <a name="see-also"></a>另请参阅  
-  [分隔记录的注意事项](../core/delimited-record-considerations.md)   
-  **子顺序 （从节点属性的平面文件架构）**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]