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
ms.openlocfilehash: 9c6e21beac4b0109fb1c0c6623bb823aa940a6d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36997542"
---
# <a name="property-interdependencies"></a>属性相互依存关系

## <a name="overview"></a>概述
使用 BizTalk 编辑器（特别是 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] 的“属性”窗口）更改属性的值时，您将看到属性之间具有广泛的相互依存关系。 有时，一个属性的特定设置将导致其他属性自动清除、启用或禁用、显示在“属性”窗口或从该窗口中完全消失。 这些相互依存关系数不胜数。 

但是，以下列表提供了一些常见示例，以便您了解它们的工作原理：  
  
- 设置的属性时**Field 元素**节点或**字段属性**节点为其数据类型从派生简单类型的使用限制机制，一个新的类别属性将变为可用：**限制**。 另外，基于基本数据类型是字符串型还是数字类型来启用或禁用此新类别中的属性。 有关这种形式的简单类型派生的详细信息，请参阅[简单类型派生使用限制机制](../core/simple-type-derivation-using-the-restriction-mechanism.md)。  
  
- 设置的属性时**字段元素**节点或**Field 特性**节点为其数据类型派生自简单类型通过使用列表或联合机制**Base数据类型**属性改为**项类型**属性或**成员类型**属性，分别。 在后一种情况下，将修改相应的下拉列表以包括复选框，允许选择多个类型。 有关这些形式的简单类型派生的详细信息，请参阅[简单类型派生使用列表机制](../core/simple-type-derivation-using-the-list-mechanism.md)并[简单类型派生使用联合机制](../core/simple-type-derivation-using-the-union-mechanism.md)。  
  
- 若要公开与平面文件架构相关联的属性，必须设置**架构编辑器扩展**的属性**架构**节点包括**平面文件扩展**. 与其他编辑器扩展，例如 EDI 扩展相关联的自定义属性公开相同的方式： 通过选择相应的扩展使用**架构编辑器扩展**属性。  
  
  此列表包括的示例旨在说明属性相互依存关系的类型（使用“属性”窗口时将可以看到这些属性相互依存关系），但它并不是这些相互依存关系的完整列表。  
  
## <a name="see-also"></a>请参阅  
- [节点属性](../core/node-properties.md)   
- 以下属性 [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
   -  节点属性按字母顺序排列列表
   -  所有架构的节点属性 
   -  架构编辑器扩展