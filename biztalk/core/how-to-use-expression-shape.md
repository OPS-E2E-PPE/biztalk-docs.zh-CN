---
title: 如何使用表达式形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- configuring [Orchestration Designer], Expression shapes
- Expression shape [Orchestration Designer]
- Expression shape [Orchestration Designer], configuring
- Expression shape [Orchestration Designer], about Expression shape
ms.assetid: 2d702aa9-b824-4f47-a416-70707ce8ef29
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f26184af9976764f77276e256332d5750e35e5fc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383406"
---
# <a name="how-to-use-expression-shape"></a>如何使用表达式形状
**表达式**形状使您能够输入在业务流程中选择的任何 XLANG/s 表达式。 例如，可以进行.NET 调用来运行外部程序，或只需处理业务流程变量的值。  
  
 虽然**表达式**形状是非常灵活，而不是使用它来执行高级业务流程逻辑，最好是在业务流程设计图本身中可见的好办法。 一般情况下，很容易理解和维护您的业务流程，如果你**表达式**形状包含简单的模块化表达式。  
  
### <a name="to-configure-an-expression-shape"></a>若要配置的表达式形状  
  
1.  如果 BizTalk 表达式编辑器不可见，请右键单击**表达式**形状，然后单击**编辑表达式**或在属性窗口中，单击省略号 (**...**) 按钮**表达式**属性。  
  
2.  在 BizTalk 表达式编辑器中，创建要分配值的表达式。 有关详细信息，请参阅[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)。  
  
## <a name="see-also"></a>请参阅  
 [XLANG-s 语言](../core/xlang-s-language.md)