---
title: 如何配置 Compensate 形状 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Compensate shape [Orchestration Designer], about Compensate shape
- Compensate shape [Orchestration Designer]
- compensations, Compensate shape [Orchestration Designer]
- configuring [Orchestration Designer], Compensate shape
- Compensate shape [Orchestration Designer], configuring
ms.assetid: 9f06289e-4d11-4864-9851-c210276865a7
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 059ac58d95d33234737033c00c4a6a2a36e256f6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248277"
---
# <a name="how-to-configure-the-compensate-shape"></a>如何配置 Compensate 形状
如果你在业务流程中使用嵌套的事务，你可以添加**Compensate**补偿块或事务范围的异常块中的形状。 这样可以使您的业务流程能够明确地对嵌套事务执行补偿操作。 指定你想要在补偿的事务**Compensate**形状，以及在嵌套事务中的任何补偿代码将运行，提供已成功提交的事务。  
  
> [!NOTE]
>  **补偿**属性指的事务作用域的唯一标识符; 它不是指作用域的名称。  
  
 如果你想要补偿多个嵌套的事务，则添加附加**Compensate**每个事务的形状。  
  
 不**Compensate**形状是外部事务中没有其他补偿代码是否有必要; 任何嵌套的事务的补偿代码将自动运行。 **Compensate**调整的允许你通过允许你决定是否要进行补偿的嵌套的事务控制该过程。  
  
### <a name="to-configure-a-compensate-shape"></a>配置补偿形状  
  
-   在属性窗口中，选择要从调用的补偿块**补偿**下拉列表。  
  
     该下拉列表将显示可以对其执行补偿操作的所有事务，其中包括当前事务以及当前事务的任何直接子事务。 如果您没有看到预期的事务，这可能是事务关系的原因导致的。  
  
    > [!NOTE]
    >  不能在当前事务的事务主体内对其执行补偿操作。  您可以从该事务的补偿模块或事务的异常块对其执行补偿操作。  
  
     如果您选择对当前事务执行补偿操作，这意味着将调用默认处理程序，而不是显式补偿模块（如果有）。 这是一种用于自动补偿已成功完成的直接嵌套的事务的机制。