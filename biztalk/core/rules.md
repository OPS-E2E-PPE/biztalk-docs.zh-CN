---
title: 规则 |Microsoft 文档
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
ms.openlocfilehash: 35f398cf98181d17833be79fbe9d282e8515e052
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268773"
---
# <a name="rules"></a>规则
业务规则是规定的业务流程开展的声明性语句。 规则由条件和操作组成。 对条件进行评估，如果其计算结果为**true**，规则引擎启动一个或多个操作。  
  
 业务规则框架中的规则定义通过使用以下格式：  
  
 如果`condition`然后`action`  
  
 请参考如下示例：  
  
 如果量小于或等于可用基金  
  
 THEN 执行交易和打印收据  
  
 此规则确定是否将通过将业务逻辑，两个的货币值的比较的形式应用于数据或在事务量和可用基金的形式事实执行事务。  
  
 你可以使用业务规则编辑器来创建、 修改、 版本，然后部署业务规则。 或者，你可以以编程方式执行上述任务。  
  
## <a name="conditions"></a>条件  
 条件是 true/false （布尔） 表达式包含的适用于在事实的一个或多个谓词。  
  
 在本示例中，谓词**小于或等于**应用于这些事实**量**和**可用基金**。 这种情况将始终评估为**true**或**false**。  
  
 可以使用逻辑运算符组合谓词**AND**，**或者**，和**不**到逻辑表达式，表示可能很大，但将计算结果始终为窗体任一**true**或**false**。  
  
## <a name="actions"></a>操作  
 操作是条件计算的功能后果。 如果满足规则条件，则启动相应的操作。  
  
 在本示例中，"准则事务"和"打印回执"都执行时，并且仅当条件 （在这种情况下，"如果数量小于或等于可用基金"） 为 true 的操作。  
  
 通过调用方法或在对象上设置属性或执行在 XML 文档或数据库表上的设置操作的业务规则 Framework 中表示操作。  
  
## <a name="facts"></a>事实  
 事实数据是在其规则进行操作的数据。 在本示例中，"amount"和"可用基金"是事实。 有关详细信息，请参阅[事实](../core/facts.md)。  
  
## <a name="see-also"></a>另请参阅  
 [如何创建策略和规则](../core/how-to-create-policies-and-rules.md)