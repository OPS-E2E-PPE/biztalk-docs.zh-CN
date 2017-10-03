---
title: "采用表达式的形状 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Expression Editor, shapes
- Decide shape [Orchestration Designer], expressions
- Message Assignment shape [Orchestration Designer], expressions
- Filter Expression property
- Listen shape [Orchestration Designer], expressions
- Delay shape [Orchestration Designer], expressions
- shapes, expressions
- Receive shape [Orchestration Designer], expressions
- Loop shape [Orchestration Designer], expressions
- Rule shape [Orchestration Designer]
ms.assetid: 0d27f711-ff7c-422b-b231-aa3c9a42ed0c
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3e78ada2c69205a0201c4bae9f3c7fa5b0656fa7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="shapes-that-take-expressions"></a>采用表达式的形状
多个形状中业务流程设计器中，包括**确定**和**循环**，使用控制分支的窗体规则的布尔表达式。 其他形状将表达式用于其他用途。 通过使用 BizTalk 表达式编辑器，您可以为这些形状创建或编辑表达式。  
  
 下表概括列出了可在业务流程设计器中使用表达式的形状，并列出了对这些表达式有效的数据类型：  
  
|形状|表达式用法说明|有效的表达式数据类型|  
|-----------|-----------------------------------|---------------------------------|  
|**决定**|**决定**形状包含**规则**形状，使用布尔表达式。|Boolean|  
|**接收**|**接收**激活属性设置为 True 的使用的形状**筛选器表达式**属性筛选传入消息。 此属性中的表达式的计算结果必须是布尔类型，该计算结果值将确定是否接受传入消息。<br /><br /> **筛选器表达式**对话框用于创建筛选器表达式。|Boolean|  
|**循环**|A**循环**形状需要**规则**形状，这反过来必须包含布尔表达式。|Boolean|  
|**规则**|**规则**形状 （作为"分支"形状显示过程区域上） 是简单形状，包含布尔表达式，用于在其他 （复杂） 形状内控制分支。|Boolean|  
|**侦听**|每个分支**侦听**形状，至少包含，或者**接收**形状，只对筛选器表达式中使用布尔表达式 (请参阅的条目**接收**)或**延迟**调整，它使用**System.DateTime**对象或**System.TimeSpan**对象。|Boolean、System.DateTime、System.TimeSpan|  
|**延迟**|中所用的表达式**延迟**形状的计算结果必须为**System.DateTime**对象，表示截止时间，或**System.TimeSpan**对象，表示持续时间。|System.DateTime、System.TimeSpan|  
|**消息赋值**|中的表达式**消息分配**形状将值分配给一条消息。 尽管赋值的对象通常是消息，但所赋的值可以为任何类型。|Any|  
|**表达式**|**表达式**形状使您能够输入您的业务流程中选择任何表达式。 例如，您可以借助 .NET 调用来运行外部程序，或仅处理业务流程变量的值。|Any|  
  
## <a name="in-this-section"></a>本节内容  
 [如何使用表达式形状](../core/how-to-use-expression-shape.md)  
  
## <a name="see-also"></a>另请参阅  
 [表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)   
 [构造消息](../core/constructing-messages.md)   
 [配置流控制形状](../core/configuring-flow-control-shapes.md)