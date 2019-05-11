---
title: 如何配置补偿形状 |Microsoft Docs
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
ms.openlocfilehash: e04ffee84b47a6a4e5520ece823575b030ccd6ba
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65341007"
---
# <a name="how-to-configure-the-compensate-shape"></a>如何配置补偿形状
如果您在业务流程中使用嵌套的事务，您可以添加**补偿**中的补偿模块或异常块的事务作用域形状。 这使您的业务流程来明确地对嵌套事务执行补偿。 指定你想要进行补偿的事务**补偿**形状和在嵌套事务中的任何补偿代码将运行，提供已成功提交的事务。  
  
> [!NOTE]
>  **补偿**属性引用事务作用域的唯一标识符; 它不是指作用域的名称。  
  
 如果你想要补偿多个嵌套的事务，则添加额外**补偿**形状的每个事务。  
  
 否**补偿**形状是外部事务中没有其他补偿代码是否有必要; 任何嵌套事务的补偿代码将自动运行。 **补偿**形状使您能够确定你是否想要补偿的嵌套的事务控制该过程。  
  
### <a name="to-configure-a-compensate-shape"></a>若要配置补偿形状  
  
-   在属性窗口中，选择要从调用的补偿块**补偿**下拉列表。  
  
     下拉列表将显示所有可以进行补偿，其中包括当前事务和当前事务的任何直接子事务的事务。 如果看不到预期的事务，它可能是由于事务的关系。  
  
    > [!NOTE]
    >  不能补偿的事务主体内从当前事务。  可以补偿其补偿模块或异常块在事务中。  
  
     如果您选择补偿当前事务，这意味着，将调用默认处理程序，并不是显式补偿模块 （如果有）。 这是用于自动补偿已成功完成的直接嵌套的事务的机制。