---
title: 简单类型派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d43932a0-039c-4211-82c0-087bae186145
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c1b1904c96c2786abad283db7133a9755c8743d6
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998494"
---
# <a name="simple-type-derivation"></a>简单类型派生
XML 架构定义 (XSD) 语言提供了定义简单类型的变体的若干机制（基于现有简单类型的派生），如下所示：  
  
- **限制**。 通过使用限制机制进行简单类型派生将引入对该类型的可能值的限制。 例如，数字类型的最小和/或最大值，或者字符串类型的最小和最大长度。  
  
- **列表**。 通过使用列表机制进行简单类型派生将允许实例消息中的单个属性或元素值定义为由特定类型的空格分隔的值的列表组成。  
  
- **联合**。 通过使用联合机制进行简单类型派生将允许实例消息中的单个属性或元素值定义为多个指定类型之一的单个值。  
  
  本部分将详细介绍这些简单类型派生，包括如何通过在“属性”窗口中设置相应节点属性定义这些派生以及如何构造相应 XSD。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用限制机制进行简单类型派生](../core/simple-type-derivation-using-the-restriction-mechanism.md)  
  
-   [使用列表机制进行简单类型派生](../core/simple-type-derivation-using-the-list-mechanism.md)  
  
-   [使用联合机制进行简单类型派生](../core/simple-type-derivation-using-the-union-mechanism.md)