---
title: "针对业务规则引擎中的类继承的支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- code samples, Business Rules Engine
- Business Rules Engine, inheritance
- Business Rules Engine, code samples
- Business Rules Engine, examples
- examples, Business Rules Engine
ms.assetid: 50871f34-ccbe-4f77-8feb-5694e1b14837
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 930fc5591ce55f1a2ec988b307203a4154e85c2b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-class-inheritance-in-the-business-rule-engine"></a>业务规则引擎中对类继承的支持
面向对象编程 (OOP) 语言的主要功能之一是继承。 通过继承，可以使用现有类的所有功能，并且无需重新编写原始类就可以对这些功能进行扩展。  
  
 业务规则框架支持两种类型的类继承：实现和接口。 实现继承是指使用基类的属性和方法而不进行额外编码的能力。 接口继承是指只使用属性和方法的名称，但子类必须提供实现的能力。  
  
 规则可以按照常见基类进行编写，但添加到引擎中的对象可以来自派生类。 在下面的示例中， **RegularEmployee**和**ContractEmployee**是基本类的派生的类**员工**。  
  
```  
class Employee  
   {  
      public string Status()  
      {   
         // member definition  
      }  
      public string TimeInMonths()        
      {   
         // member definition  
      }  
   }  
  
class ContractEmployee : Employee  
{  
   // class definition  
}  
class RegularEmployee : Employee  
{  
   // class definition  
}  
```  
  
 假定你具有以下规则。  
  
## <a name="rule-1"></a>规则 1  
  
```  
IF Employee.TimeInMonths < 12  
THEN Employee.Status = "New"  
```  
  
 在运行时，如果用户断言两个对象，其中一个实例的**ContractEmployee**和其他实例的**RegularEmployee**，针对所述的规则进行了评估两个对象实例更早版本。  
  
 用户还可以通过使用断言中操作的派生的类对象**断言**。 这将导致在其条件中包含派生对象及其基本类型的规则重新计算，如下例所示。  
  
## <a name="rule-2"></a>规则 2  
  
```  
IF Employee.Status = "Contract"   
THEN Employee.Bonus = false  
Assert(new ContractEmployee())  
```  
  
 包含的所有规则**员工**类型或**ContractEmployee**断言后获取重新评估其条件中的类型。 在此示例中，继承的类型是实现。 即使只添加派生类，但如果使用基类而不是派生类中的方法来编写规则，那么也会添加基类。  
  
## <a name="see-also"></a>另请参阅  
 [规则引擎](../core/rule-engine.md)