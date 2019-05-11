---
title: 对业务规则引擎中的类继承的支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- code samples, Business Rules Engine
- Business Rules Engine, inheritance
- Business Rules Engine, code samples
- Business Rules Engine, examples
- examples, Business Rules Engine
ms.assetid: 50871f34-ccbe-4f77-8feb-5694e1b14837
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a21d9d300bf01e2ab792ca86f8a52b9b5831695c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321907"
---
# <a name="support-for-class-inheritance-in-the-business-rule-engine"></a>对业务规则引擎中的类继承的支持
面向对象编程 (OOP) 语言的主要功能之一是继承。 继承是功能的类的能够使用的所有现有以及这些功能无需重新编写原始类进行扩展。  
  
 业务规则框架支持两种类型的类继承： 实现和接口。 实现继承是指使用基类的属性和方法与任何其他编码的功能。 接口继承是指能够使用只是名称的属性和方法，但子类必须提供实现。  
  
 可以在一个公共基类，方面编写规则，但添加到引擎的对象可以是从派生类。 在以下示例中， **RegularEmployee**并**ContractEmployee**是类的基类的派生的类**员工**。  
  
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
  
 假设您有以下规则。  
  
## <a name="rule-1"></a>规则 1  
  
```  
IF Employee.TimeInMonths < 12  
THEN Employee.Status = "New"  
```  
  
 在运行时，如果用户添加两个对象，其中一个实例的**ContractEmployee**和其他实例的**RegularEmployee**，这两个对象实例根据所述的规则进行计算前面。  
  
 用户还可以通过添加在操作的派生的类对象**Assert**。 这会导致包含派生的对象和在其条件中的其基类型，都会重新计算，如下面的示例中所示的规则。  
  
## <a name="rule-2"></a>规则 2  
  
```  
IF Employee.Status = "Contract"   
THEN Employee.Bonus = false  
Assert(new ContractEmployee())  
```  
  
 包含的所有规则**员工**类型或**ContractEmployee**断言之后重新计算在其条件中的类型。 在此示例中的类型是继承的实现。 即使添加仅在派生的类的基类那么也会添加如果编写使用基类而不是派生类中方法的规则。  
  
## <a name="see-also"></a>请参阅  
 [规则引擎](../core/rule-engine.md)