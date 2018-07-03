---
title: 业务规则的策略测试跟踪输出信息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, business rules
- testing, policies
- business rules, testing
- policies, testing
ms.assetid: 26ff584e-97a1-4d76-a8a9-a55b4c99231f
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e8795e926d496f586d032bb85fe4a1fddb473ec5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005134"
---
# <a name="policy-test-trace-output-information-for-business-rules"></a>业务规则的策略测试跟踪输出信息
本部分介绍了在业务规则编辑器中测试策略时显示的跟踪信息。 使用“组中心”页上的消息事件和服务实例跟踪查询查看策略执行的跟踪结果时，会看到非常相似的信息。  
  
 跟踪输出中显示有四种语句类型：  
  
- 事实活动  
  
- 条件评估  
  
- 议程更新  
  
- 触发的规则  
  
  下面介绍了每种语句类型。  
  
## <a name="fact-activity"></a>事实活动  
 此语句指示对引擎工作内存中存在的事实的更改。 下面列出了一个事实活动条目示例：  
  
```  
FACT ACTIVITY 3/16/2004 9:50:28 AM  
Rule Engine Instance Identifier: 9effe3f9-d3ad-4125-99fa-56bb379188f7  
Ruleset Name: LoanProcessing  
Operation: Assert  
Object Type: MyTest.test  
Object Instance Identifier: 872  
```  
  
### <a name="rule-engine-instance-identifier"></a>规则引擎实例标识符  
 唯一标识符**RuleEngine**提供规则触发的执行环境的实例。  
  
### <a name="ruleset-name"></a>规则集名称  
 规则集（策略）的名称。  
  
### <a name="operation"></a>运算  
 可以在事实活动中执行三种类型的操作：  
  
 ActualRebinds  
  
 事实将添加到工作内存中。  
  
 Update  
  
 事实将按规则进行更新，然后需要重新添加到引擎中，才能根据新的数据和状态重新进行评估。  
  
 收回  
  
 事实将从工作内存中删除。  
  
> [!NOTE]
>  如果所添加事实，其类型不匹配任何策略中使用的类型，则添加操作将显示"添加-事实无法识别"。  
  
### <a name="object-type"></a>对象类型  
 特定活动的事实类型：  
  
-   DataConnection  
  
-   TypedDataTable  
  
-   TypedDataRow  
  
     添加 TypedDataTable 时，包含的所有行都将作为 TypedDataRows 添加。  在评估条件并执行结果查询后，才会添加与 DataConnection 关联的 TypedDataRows。  
  
-   TypedXmlDocument  
  
     父 TypedXmlDocument 实例和子 TypedXmlDocument 实例的断言都可以看到。  
  
### <a name="object-instance-identifier"></a>对象实例标识符  
 事实引用的唯一实例 ID。  
  
## <a name="condition-evaluation"></a>条件评估  
 此活动指示评估各个谓词的结果。 下面列出了一个条件评估条目示例：  
  
```  
CONDITION EVALUATION TEST (MATCH) 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Test Expression: TypedXmlDocument:Microsoft.Samples.BizTalk.LoansProcessor.Case:Root.EmploymentType/TimeInMonths >= 18  
Left Operand Value: 31  
Right Operand Value: 18  
Test Result: True  
```  
  
 下面对上例中的某些术语进行了说明：  
  
-   **测试表达式。** 规则中的简单（一元或二元）表达式。  
  
-   **左的操作数的值。** 表达式左侧项的值。  
  
-   **右操作数的值。** 表达式右侧项的值。  
  
-   **测试结果。** 评估的结果，即 True 或 False。  
  
## <a name="agenda-update"></a>议程更新  
 此活动指示添加到规则引擎议程中以便随后执行的规则。 下面列出了一个议程更新条目示例：  
  
```  
AGENDA UPDATE 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Operation: Add  
Rule Name: Employment Status Rule  
Conflict Resolution Criteria: 0  
```  
  
 下面对上例中的某些术语进行了说明：  
  
-   **操作。** 可以在议程中添加或删除规则。  
  
-   **规则名称。** 向议程添加的规则的名称。  
  
-   **冲突解决标准。** 规则的优先级，用于确定执行操作的相对顺序（首先执行优先级较高的操作）。  
  
## <a name="rule-fired"></a>触发的规则  
 此活动指示规则操作的执行情况。 下面列出了一个规则触发条目示例：  
  
```  
RULE FIRED 1/07/2004 5:33:13 PM  
Rule Engine Instance Identifier: f1dd3ff2-b4a8-4fe1-8d46-4d9b3e2502d3  
Ruleset Name: LoanProcessing  
Rule Name: Residency Status Rule  
Conflict Resolution Criteria: 10  
```