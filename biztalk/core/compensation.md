---
title: 补偿 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eba08eecad12c08a3bebd6f4704d7df82b74d279
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357890"
---
# <a name="compensation"></a>补偿
如果发生错误，并且需要进行撤消或已成功提交事务的影响，就可以做到补偿代码添加到您的业务流程。  
  
 事务已成功完成其操作后，可以调用补偿。 此时，业务流程的状态已知的并且状态信息可供补偿，这意味着您可以编写代码时采取相应措施具体取决于业务流程的状态的事务提交中的代码。  
  
 也可以在原子事务提供补偿。 这些补偿只能在原子事务提交后调用。 您需要编写代码可以撤消的补偿中的常规执行路径。  
  
 补偿模块是灵活;它可以包含其他任何形状，包括另一个事务作用域。  
  
> [!NOTE]
>  你可以执行补偿只能一次在给定作用域。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何配置补偿形状](../core/how-to-configure-the-compensate-shape.md)  
  
-   [如何向业务流程添加自定义补偿](../core/how-to-add-custom-compensation-to-an-orchestration.md)  
  
-   [如何添加补偿块](../core/how-to-add-a-compensation-block.md)