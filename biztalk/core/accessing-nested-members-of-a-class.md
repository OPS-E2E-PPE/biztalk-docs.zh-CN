---
title: "访问类的嵌套的成员 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 358e1edf-ae0b-4916-b8db-7277f39e36f4
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 110244f9f007a417450b5bbfdce831d5f255cfe5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="accessing-nested-members-of-a-class"></a>嵌套类成员访问
规则引擎允许您在规则中使用对象的嵌套属性或方法。 例如，假定具有名为 AClass 的类，该类具有名为 B、类型为 BClass 的属性，BClass 又具有名为 C 的字段。规则引擎允许您使用 A.B.C 语法生成访问字段 C 的规则。 不过，只有在以编程方式生成规则时才能使用此语法，使用业务规则编辑器工具时不能使用此语法。 下面的示例代码演示如何使用某个对象的属性，而该对象又是另一个对象的属性：  
  
```  
// Create the condition list IF 1 == 1  
Equal eq = new Equal(new Constant(1), new Constant(1));  
  
// Create the action collection  
ActionCollection ac = new ActionCollection();  
  
// Create class binding and class member binding to cField  
// Set the value of cField to "Changed"  
Constant chg = new Constant("Changed");  
ArgumentCollection argCol = new ArgumentCollection();  
argCol.Add(chg);  
ClassBinding lstClass = new ClassBinding(typeof(AClass));  
ClassMemberBinding bBinding = new ClassMemberBinding("bObj", lstClass);  
ClassMemberBinding CBinding = new ClassMemberBinding("cField", bBinding,argCol);  
UserFunction uf_C = new UserFunction(CBinding);  
ac.Add(uf_C);  
  
// Create the rule  
Rule rl = new Rule("ChangeCField", eq, ac);  
  
// Create the policy  
RuleSet rs = new RuleSet("NestedNodeTest");  
rs.Rules.Add(rl);  
  
//Create the facts  
AClass aObj = new AClass();  
Console.WriteLine("The value of aObj.bObj.cField BEFORE executing the policy");  
Console.WriteLine(aObj.bObj.cField);  
  
//Execute the policy  
PolicyTester tester = new PolicyTester(rs);  
tester.Execute(aObj);  
  
Console.WriteLine("The value of aObj.bObj.cField AFTER executing the policy");  
Console.WriteLine(aObj.bObj.cField);  
```