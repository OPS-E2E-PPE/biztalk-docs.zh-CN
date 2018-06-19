---
title: 对泛型类型和泛型方法的支持 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc6b5b51-e084-4828-ad25-9209aa74dc6f
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65d8a17a9ac1f055312f0f1cdf3bc1231319842d
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
ms.locfileid: "25972315"
---
# <a name="support-for-generic-types-and-generic-methods"></a>对泛型类型和泛型方法的支持
规则引擎支持在规则中使用专用的泛型类型和专用的泛型方法。 但不支持在规则中使用泛型类型和泛型方法本身。 例如，在业务规则可以使用**列表**\<*int*\>，但不是**列表**\<T\> （从**System.Collections.Generic** .NET 类库中的命名空间)。 目前，业务规则编辑器工具不支持使用专用的泛型类型和专用的泛型方法创建规则。 您必须使用规则引擎对象模型通过编程方式来创建规则。 下面的示例代码演示如何使用**列表**业务规则中的泛型类：  
  
```  
  
// Create the condition list IF 1 == 1  
Equal eq = new Equal(new Constant(1), new Constant(1));  
  
// Create the action list List<int>.Add(3)  
ActionCollection ac = new ActionCollection();  
  
//Create class binding and class member bindings  
ClassBinding lstClass = new ClassBinding(typeof(System.Collections.Generic.List<int>));  
ArgumentCollection argc = new ArgumentCollection();  
argc.Add(new Constant(3));  
ClassMemberBinding add = new ClassMemberBinding("Add", lstClass, argc);  
  
// Wrapping the .NET binding as a user function  
UserFunction uf = new UserFunction(add);  
ac.Add(uf);  
  
// Create the rule  
Rule rl = new Rule("AddToList", eq, ac);  
  
// Create the policy  
RuleSet rs = new RuleSet("GenericTest");  
rs.Rules.Add(rl);  
  
// Create the .NET List object  
List<int> lst = new List<int>();  
lst.Add(1);  
lst.Add(2);  
  
// Print the list before executing the policy  
Console.WriteLine("Contents of the lists before executing the policy");  
foreach (int i in lst)  
    Console.WriteLine(i);  
  
PolicyTester pt = new PolicyTester(rs);  
pt.Execute(lst);  
  
// Print the list after executing the policy  
Console.WriteLine("Contents of the lists before executing the policy");  
foreach (int i in lst)  
    Console.WriteLine(i);  
```