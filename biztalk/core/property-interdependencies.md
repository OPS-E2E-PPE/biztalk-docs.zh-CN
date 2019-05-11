---
title: 属性相互依存关系 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3ed5b75e-db1c-43d4-a287-fc4cd1c529f5
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a871fcccc61795569a3d93c0d558f91d13bb67f9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398478"
---
# <a name="property-interdependencies"></a>属性相互依存关系

## <a name="overview"></a>概述
使用 BizTalk 编辑器中，如，尤其是[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]属性窗口中，若要更改属性的值，您将注意到属性之间是否存在大量相互依赖关系。 有时一个属性的特定设置将导致其他属性自动清除、 启用或禁用，或甚至出现或从属性窗口中完全消失。 这些相互依存关系数不胜数。 

但是，以下列表提供了一些常见的示例，以便您了解它们的工作原理：  
  
- 设置的属性时**Field 元素**节点或**字段属性**节点为其数据类型从派生简单类型的使用限制机制，一个新的类别属性可用：**限制**。 此外，此新类别中的属性启用或禁用基于的基本数据类型是否是字符串类型或数值类型。 有关这种形式的简单类型派生的详细信息，请参阅[简单类型派生使用限制机制](../core/simple-type-derivation-using-the-restriction-mechanism.md)。  
  
- 设置的属性时**字段元素**节点或**Field 特性**节点为其数据类型派生自简单类型通过使用列表或联合机制**Base数据类型**属性改为**项类型**属性或**成员类型**属性，分别。 在后一种情况下，修改相应的下拉列表以包括复选框，允许选择多个类型。 有关这些形式的简单类型派生的详细信息，请参阅[简单类型派生使用列表机制](../core/simple-type-derivation-using-the-list-mechanism.md)并[简单类型派生使用联合机制](../core/simple-type-derivation-using-the-union-mechanism.md)。  
  
- 若要公开与平面文件架构相关联的属性，必须设置**架构编辑器扩展**的属性**架构**节点包括**平面文件扩展**. 与其他编辑器扩展，例如 EDI 扩展相关联的自定义属性公开相同的方式： 通过选择相应的扩展使用**架构编辑器扩展**属性。  
  
  此列表包含旨在说明属性相互依存关系，您将看到属性窗口中工作时的类型的示例，但它并不是这些相互依存关系的详尽列表。  
  
## <a name="see-also"></a>请参阅  
- [节点属性](../core/node-properties.md)   
- 以下属性 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
   -  节点属性按字母顺序排列列表
   -  所有架构的节点属性 
   -  架构编辑器扩展