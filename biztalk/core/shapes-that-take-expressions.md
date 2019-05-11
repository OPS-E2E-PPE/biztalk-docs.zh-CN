---
title: 使用表达式的形状 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 719ada151b3a9efaaea51fff84579b79579bd68d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65393177"
---
# <a name="shapes-that-take-expressions"></a>使用表达式的形状
多个形状在业务流程设计器中，包括**判定**并**循环**，使用布尔表达式来控制分支的窗体规则。 其他形状将表达式用于其他目的。 可以创建或使用 BizTalk 表达式编辑器中编辑这些形状的表达式。  
  
 下表总结了在业务流程设计器中使用表达式形状，并列出了对这些表达式有效的数据类型。  
  
|形状|表达式用法说明|有效的表达式数据类型|  
|-----------|-----------------------------------|---------------------------------|  
|**决定**|**决定**形状包含**规则**形状，而后者使用布尔表达式。|Boolean|  
|**Receive**|**接收**其激活属性设置为 True 的使用的形状**筛选器表达式**属性来筛选传入消息。 此属性中的表达式的计算结果必须为布尔值，其值确定接受传入的消息。<br /><br /> **筛选器表达式**对话框用于创建筛选器表达式。|Boolean|  
|**Loop**|一个**循环**形状需要**规则**形状，它又必须包含布尔表达式。|Boolean|  
|**规则**|**规则**形状 （作为"分支"形状显示在流程区域上） 是简单形状，只包含布尔表达式，并用在其他 （复杂） 形状来控制分支。|Boolean|  
|**Listen**|每个分支**侦听**形状，至少包含，或者**接收**形状，它只对筛选器表达式使用布尔表达式 (请参阅**接收**)或**延迟**形状，它使用**System.DateTime**对象或**System.TimeSpan**对象。|Boolean、 System.DateTime、 System.TimeSpan|  
|**Delay**|中使用的表达式**延迟**形状的计算结果必须为**System.DateTime**对象，表示最终期限，或者**System.TimeSpan**对象，表示持续时间。|System.DateTime、 System.TimeSpan|  
|**消息赋值**|中的表达式**消息赋值**形状将值分配到一条消息。 分配的值可以是任何类型，但通常分配一条消息。|Any|  
|**表达式**|**表达式**形状使您能够输入在业务流程中选择的任何表达式。 例如，可以进行.NET 调用来运行外部程序，或只需处理业务流程变量的值。|Any|  
  
## <a name="in-this-section"></a>本节内容  
 [如何使用表达式形状](../core/how-to-use-expression-shape.md)  
  
## <a name="see-also"></a>请参阅  
 [表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)   
 [构造消息](../core/constructing-messages.md)   
 [配置“流控制”形状](../core/configuring-flow-control-shapes.md)