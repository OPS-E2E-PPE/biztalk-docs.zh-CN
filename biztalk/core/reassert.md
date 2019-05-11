---
title: 重新添加 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Assert function [Business Rules Engine]
ms.assetid: 9cd640a2-bfeb-4c7a-b737-1c92cc122a9c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 23cebbb268e57d71a1702a03d2516892c1851e8c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398250"
---
# <a name="reassert"></a>重新添加
向*重新添加*意味着调用**Assert**函数已在引擎中的对象上的工作内存。 重新添加命令相当于发出取消命令的对象，然后添加命令。  
  
## <a name="net-objects"></a>.NET 对象  
 首先取消该对象，并删除上使用该对象 （在谓词或操作） 的规则议程中的任何操作。 然后，该对象会添加回工作内存，并计算为新添加的任何对象。 这意味着在谓词中使用的对象的任何规则将重新计算，并将其操作添加到根据议程。 以前计算为任何规则 **，则返回 true**和仅使用在其操作中的对象都会将其重新添加到议程的操作。  
  
## <a name="typedxmldocument"></a>TypedXmlDocument  
 在最高级别时**TypedXmlDocument** (**TXD**) 重新添加，子**TXD**s 时创建的最高级别**TXD**最初是添加具有不同的行为，具体取决于子状态**TXD**s。 对于新的子节点或已更新，这意味着，至少一个其字段已更改的策略中使用规则操作中，声明，或重新添加操作的子节点的子节点上执行。 未更新任何现有子节点保留在工作内存中。 下面的示例是介绍时重新添加其父节点的子节点的行为的简化的方案。  
  
 假设有三个**TXD**工作内存中当前：**P**， **C**1， **C**2，和**C**3。 **P**级别为顶级**TXD**，父节点; 并且每个子节点都包含字段**x**。  
  
 **P**  
  
 **C**1 (**C**1.**x** = 1)  
  
 **C**2 (**C**2.**x** = 1)  
  
 **C**3 (**C**3.**x** = 1)  
  
 接下来，假定由于规则操作执行了以下操作：  
  
-   字段 (**x**) 的值**C**更新 2。  
  
-   **C**3 删除了使用用户代码。  
  
-   另一个子节点**D**，添加到**P**通过用户代码。  
  
> [!NOTE]
>  节点将不会标记已更新的操作，其中引擎并不知道从业务规则引擎。 例如，添加、 删除或修改以编程方式在外部应用程序中的节点。  
  
 在工作内存中对象的新表示形式如下所示。  
  
 **P**  
  
 **C**1 (**C**1.**x** = 1)  
  
 **C**2 (**C**2.**x** = *0*)  
  
 **D**  
  
 现在，重新添加**P**。以下几点汇总的子节点的行为：  
  
-   节点**C**2 重新添加，因为它已变为已更新后更新其字段。  
  
-   节点**C**从工作内存取消 3。  
  
-   节点**D**添加到工作内存中。  
  
-   节点**C**1 保持工作内存中保持不变，因为之前未更新该**P**重新添加。  
  
## <a name="typeddatatable"></a>TypedDataTable  
 如果**重新添加**会发出**TypedDataRow**，可以取消，然后将其添加到工作内存中的行。 如果**重新添加**会发出**TypedDataTable**，则所有关联**TypedDataRow**进行取消，然后将其添加。  
  
## <a name="dataconnection"></a>DataConnection  
 所有**TypedDataRow**通过检索 s **DataConnection**中取消。 使用的所有谓词**DataConnection**然后重新评估，从而导致**DataConnection**以重新查询以创建相关**TypedDataRow**s。  
  
## <a name="see-also"></a>请参阅  
 [引擎控制函数](../core/engine-control-functions.md)