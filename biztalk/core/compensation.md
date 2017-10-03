---
title: "补偿 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- compensations, errors
- compensations
- errors, compensations
- compensations, about compensations
- compensations, atomic transactions
- atomic transactions, compensations
- transactions, compensations
ms.assetid: 0a80dd16-fd35-4f45-95b7-52bb9df80cbb
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0c572638ea6212c3fb79e6b239aa8ffbe713c3c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="compensation"></a>补偿
如果出现错误，并且你需要撤消或反向成功提交事务的效果，你可以这样做将补偿代码添加到您的业务流程。  
  
 事务成功完成其操作后，可以调用补偿。 此时，已知的业务流程的状态，并且状态信息可供中的补偿，这意味着你可以编写代码以采取相应措施具体取决于业务流程的状态在事务提交时的代码。  
  
 也可以在原子事务提供补偿。 原子事务提交后，可以仅调用这些补偿。 你需要编写代码以撤消或反向补偿在正常执行路径中。  
  
 补偿块是灵活;它可以包含任何其他形状，包括另一个事务范围。  
  
> [!NOTE]
>  你可以执行一次在给定作用域上的补偿。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何配置 Compensate 形状](../core/how-to-configure-the-compensate-shape.md)  
  
-   [如何将自定义补偿添加到业务流程](../core/how-to-add-custom-compensation-to-an-orchestration.md)  
  
-   [如何添加补偿块](../core/how-to-add-a-compensation-block.md)