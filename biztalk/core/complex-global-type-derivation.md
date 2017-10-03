---
title: "复杂全局类型派生 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fbf429d0-64f4-4c43-a5f7-e8af050803b9
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee4e6235af62b2c08c08382b897632d15e34e0cb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="complex-global-type-derivation"></a>复杂全局类型派生
XSD 中有两种类型的继承：扩展和限制。 BizTalk 编辑器通过使用以下两个提供与此 XSD 功能的访问权限**记录**节点属性：  
  
-   **基数据类型**。 此属性提供可用作基本数据类型的所有全局复杂类型和简单类型的列表。 复杂全局类型可以在同一架构中，也可以在任何导入的架构中。  
  
-   **通过派生**。 此属性用于在通过扩展派生和通过限制派生之间进行选择。 此属性自动设置为**扩展**当设置**基数据类型**到列表中的任何类型的属性。 如果将此属性设置为**（默认）**中的任何类型**基数据类型**删除属性，则禁用节点继承。  
  
> [!NOTE]
>  **内容类型**属性也将自动为**ComplexContent**何时使用通过扩展或限制派生了。  
  
 本部分较详细地介绍了使用扩展和限制机制进行的复杂类型派生。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用扩展机制的复杂类型派生](../core/complex-type-derivation-using-the-extension-mechanism.md)  
  
-   [使用限制机制的复杂类型派生](../core/complex-type-derivation-using-the-restriction-mechanism.md)