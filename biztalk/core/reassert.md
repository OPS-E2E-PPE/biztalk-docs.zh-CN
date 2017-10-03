---
title: "重新声明 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Assert function [Business Rules Engine]
ms.assetid: 9cd640a2-bfeb-4c7a-b737-1c92cc122a9c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22fcc8be7760d85a12cb05c53137177703c0fa73
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="reassert"></a>重新声明
到*重新声明*意味着调用**断言**对已在引擎中的对象的函数的工作内存。 重新添加命令相当于向该对象发出取消命令，然后执行添加命令。  
  
## <a name="net-objects"></a>.NET 对象  
 首先会取消对象，并删除针使用该对象（在谓词或操作中）的规则议程中的所有操作。 然后，将该对象添加回工作内存中，并将其作为任何新添加的对象进行计算。 这意味着将重新计算所有在谓词中使用该对象的规则，并且根据需要将其操作添加到议程中。 以前计算结果为任何规则**true**并仅使用其操作中的对象将具有重新添加到安排其操作。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 在最高级别时**TypedXmlDocument** (**TXD**) reasserted 子**TXD**时，会创建的 s 顶级**TXD**最初是声明具有不同的行为，具体取决于子状态**TXD**s。 对于新的子节点或子节点已更新，这意味着到至少一个其字段已更改的策略中使用的规则操作，一个断言，或重新声明操作执行的子节点。 所有未更新的现有子节点都将保留在工作内存中。 以下示例是一个简化的方案，该方案对重新添加其父节点时这些子节点的行为进行了说明。  
  
 假定有三个**TXD**当前在工作内存中的 s: **P**， **C**1， **C**2，和**C**3。 **P**是最高级别**TXD**，父节点; 每个子节点包含一个字段**x**。  
  
 **P**  
  
 **C**1 (**C**1。**x** = 1)  
  
 **C**2 (**C**2。**x** = 1)  
  
 **C**3 (**C**3。**x** = 1)  
  
 接下来，假定规则操作由于执行了以下操作：  
  
-   字段 (**x**) 值，则为**C**更新 2。  
  
-   **C**3 删除通过用户代码。  
  
-   另外，其他子节点， **D**，添加到**P**通过用户代码。  
  
> [!NOTE]
>  业务规则引擎不会根据其不知道的操作来将节点标记为已更新。 例如，在外部应用程序中通过编程方式添加、删除或修改节点。  
  
 使用内存中对象的新表示如下所示。  
  
 **P**  
  
 **C**1 (**C**1。**x** = 1)  
  
 **C**2 (**C**2。**x** = *0*)  
  
 **D**  
  
 现在，重新声明**P**。以下几点汇总的子节点的行为：  
  
-   节点**C**reasserted 2，因为它已变得脏后其正在更新的字段。  
  
-   节点**C**3 是否被收回从工作内存。  
  
-   节点**D**到工作内存断言。  
  
-   节点**C**1 保持在工作内存中，不变，因为它未更新之前**P**已 reasserted。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 如果**重新声明**上发出**TypedDataRow**，收回，然后断言工作内存到该行。 如果**重新声明**上发出**TypedDataTable**，所有关联**TypedDataRow**进行收回，然后断言。  
  
## <a name="dataconnection"></a>DataConnection  
 所有**TypedDataRow**通过检索 s**该组**收回。 使用的所有谓词**该组**然后重新评估，从而导致**该组**以重新查询以创建相关**TypedDataRow**s。  
  
## <a name="see-also"></a>另请参阅  
 [引擎控制功能](../core/engine-control-functions.md)