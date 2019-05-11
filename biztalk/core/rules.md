---
title: 规则 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- business rules, actions
- Business Rules Engine, business rules
- business rules, about business rules
- business rules, conditions
- business rules, facts
- business rules
ms.assetid: b288dd07-33f1-42fe-bbfb-02674ef3b3ca
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d51492beb69b2789100f7328e84323cfff7ae2c9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65254621"
---
# <a name="rules"></a>规则
业务规则是控制业务流程的行为准则的声明性语句。 规则由条件和操作组成。 计算条件时，如果其计算结果为 **，则返回 true**，规则引擎将启动一个或多个操作。  
  
 通过使用以下格式定义业务规则框架中的规则：  
  
 如果`condition`然后`action`  
  
 请看下面的示例：  
  
 IF 金额小于或等于可用资金  
  
 THEN 执行交易并打印收据  
  
 此规则确定是否将通过对数据或事务量和可用资金的窗体中事实数据应用业务逻辑，比较的两个货币值，窗体中执行事务。  
  
 您可以使用业务规则编辑器来创建、 修改版本，并部署业务规则。 或者，可以以编程方式执行上述任务。  
  
## <a name="conditions"></a>条件  
 条件是一个 true/false （布尔） 表达式，由应用于事实的一个或多个谓词组成。  
  
 在本示例中，谓词**小于或等于**应用于事实**量**并**可用资金**。 此条件将计算结果始终为任一 **，则返回 true**或**false**。  
  
 可以使用逻辑运算符组合谓词**AND**，**或者**，并**不**到逻辑表达式，表示可能很复杂，但将计算结果始终为窗体任一 **，则返回 true**或**false**。  
  
## <a name="actions"></a>操作  
 操作是条件计算的功能性结果。 如果满足规则条件，则启动相应的操作。  
  
 在本示例中，"行为准则 transaction"和"打印收据"是，当且仅当条件 （在这种情况下，"金额小于或等于可用资金"） 为 true 时执行的操作。  
  
 操作表示业务规则框架中调用方法或设置属性的对象，或通过执行 XML 文档或数据库表的 set 操作。  
  
## <a name="facts"></a>事实  
 事实是在其规则所操作的数据。 在本例中为"金额"和"可用资金"是事实。 有关详细信息，请参阅[事实](../core/facts.md)。  
  
## <a name="see-also"></a>请参阅  
 [如何创建策略和规则](../core/how-to-create-policies-and-rules.md)