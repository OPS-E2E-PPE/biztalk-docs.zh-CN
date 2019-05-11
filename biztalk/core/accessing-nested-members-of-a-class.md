---
title: 访问类的嵌套的成员 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 358e1edf-ae0b-4916-b8db-7277f39e36f4
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3cff7c701a7e2c98d5e26bebc3e8e1b63086733
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65361964"
---
# <a name="accessing-nested-members-of-a-class"></a><span data-ttu-id="5cd54-102">类的嵌套的成员访问</span><span class="sxs-lookup"><span data-stu-id="5cd54-102">Accessing Nested Members of a Class</span></span>
<span data-ttu-id="5cd54-103">规则引擎允许您在规则中使用对象的嵌套属性或方法。</span><span class="sxs-lookup"><span data-stu-id="5cd54-103">The rule engine allows you to use a nested property or method of an object in a rule.</span></span> <span data-ttu-id="5cd54-104">例如，假定具有名为 AClass 的类，该类具有名为 B、类型为 BClass 的属性，BClass 又具有名为 C 的字段。规则引擎允许您使用 A.B.C 语法生成访问字段 C 的规则。</span><span class="sxs-lookup"><span data-stu-id="5cd54-104">For example, suppose you have a class named AClass, which has a property named B of type BClass, which has a field named C. The rule engine allows you to build rules accessing the field C by using the A.B.C syntax.</span></span> <span data-ttu-id="5cd54-105">不过，只有在以编程方式生成规则时才能使用此语法，使用业务规则编辑器工具时不能使用此语法。</span><span class="sxs-lookup"><span data-stu-id="5cd54-105">However, it is possible to use this syntax only when building the rules programmatically, not when using the Business Rule Composer tool.</span></span> <span data-ttu-id="5cd54-106">下面的示例代码演示如何使用某个对象的属性，而该对象又是另一个对象的属性：</span><span class="sxs-lookup"><span data-stu-id="5cd54-106">The following sample code demonstrates how to use a property of an object, which is a property of another object:</span></span>  
  
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