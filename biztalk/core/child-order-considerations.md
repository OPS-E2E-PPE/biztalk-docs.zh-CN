---
title: 子顺序的注意事项 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4f7aa81-5c08-4932-9e28-31e22e037999
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ee4c9bf7fe2b6a43951032f5043489f73d94bde
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357360"
---
# <a name="child-order-considerations"></a>子顺序的注意事项

## <a name="requirements-for-header-in-a-flat-file"></a>平面文件中的标头的要求
有两种与分隔平面文件的特殊注意事项将应用设置时相关的方案**子顺序**属性。 第一次此类情况涉及平面文件文档中拥有一个标头、 正文和尾部 （可选） 的情况。 在这些情况下，必须遵守以下要求：  

- 必须设置**子顺序**到标头的 （分隔） 根记录的属性**后缀**。  

- 如果存在尾部，则必须设置**子顺序**正文的 （分隔） 根记录的属性**后缀**。  

- 如果不存在尾部，则可以设置**子顺序**正文的 （分隔） 根记录的属性**前缀**，**中缀**，或**后缀**.  

- 如果存在尾部，则可以设置**子顺序**该尾部的 （分隔） 根记录的属性**前缀**，**中缀**，或**后缀**.  

- 您可以设置**子顺序**属性的标头、 正文和尾部的分隔从属记录**前缀**，**中缀**，或**后缀**.  

  与第二个方案带分隔符的平面文件和**子顺序**属性是根据运行时组件预期节点必须设置此属性。 为正确的设置**子顺序**属性可能不是明显的根节点和组节点，如以下方案中所示：  

- **根节点。** 请考虑其结构由跟 CR/LF 组合的记录组成的典型平面文件。 分隔符用于分隔记录在文件中，并且顺序通常记录、 分隔符、 记录、 分隔符，等等。 在这种情况下，分隔符始终遵循数据，这对应于**子顺序**属性设置为**后缀**。  

- **组节点。** 不在实例消息的平面文件表示形式显式存在于架构的 BizTalk Server 和 XSD 表示形式中所示的组节点。 假设一个采购订单 (PO) 包含一系列记录每个行项，并且这些记录重复多次以表示单个 PO 中的多个行项。 此类消息的架构可能包括名为 LineItems 充当重复集的 （有时概念） 容器的节点： 在平面文件表示的实例消息中，LineItems 容器本质上是概念性，由表示数据和分隔符; 的合适的规则在实例消息的 XML 表示中，LineItems 容器则以的形式显式存在于**LineItems**中 XML 元素。  

  假设某消息包含一个根节点并且只有一个组节点。 很容易就可以看出输入流中的最后一个分隔符将属于根节点。 因此，概念循环中的数据/分隔符序列只会是一个或多个行项目记录。 仅在这种情况中有多个行项目记录会分隔符将其隔开。 情况下，分隔符数是一个不会早于要分隔的集，分隔符位于称为中缀的结构中的带分隔符的项之间。  

## <a name="see-also"></a>请参阅  
- [分隔记录注意事项](../core/delimited-record-considerations.md)   
- **子顺序 （平面文件架构的节点属性）** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
