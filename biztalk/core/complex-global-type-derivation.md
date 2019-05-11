---
title: 复杂全局类型派生 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbf429d0-64f4-4c43-a5f7-e8af050803b9
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b82c7482204195010cf4d1177c4e6ccad4713df2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356713"
---
# <a name="complex-global-type-derivation"></a>复杂全局类型派生
有两种类型的 XSD 中的继承： 扩展和限制。 BizTalk 编辑器中通过使用以下两个提供访问此 XSD 功能**记录**节点属性：  
  
-   **基本数据类型**。 此属性提供的所有全局复杂类型的列表，并可用于简单类型将用作基本数据类型。 复杂全局类型可以是同一架构中或在任何导入的架构。  
  
-   **通过派生**。 此属性用于通过扩展或限制派生之间进行选择。 此属性自动设置为**扩展**设置时**Base Data Type**到列表中的任何类型的属性。 如果此属性设置为 **（默认值）**，在任何类型**Base Data Type**属性会被删除，禁用节点继承。  
  
> [!NOTE]
>  **内容类型**属性也设置自动向**ComplexContent**时正在使用通过扩展或限制进行派生。  
  
 本部分介绍通过使用更详细地扩展和限制机制进行复杂类型派生。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [使用扩展机制进行复杂类型派生](../core/complex-type-derivation-using-the-extension-mechanism.md)  
  
-   [使用限制机制进行复杂类型派生](../core/complex-type-derivation-using-the-restriction-mechanism.md)