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
# <a name="support-for-class-inheritance-in-the-business-rule-engine"></a><span data-ttu-id="3c5f2-102">对业务规则引擎中的类继承的支持</span><span class="sxs-lookup"><span data-stu-id="3c5f2-102">Support for Class Inheritance in the Business Rule Engine</span></span>
<span data-ttu-id="3c5f2-103">面向对象编程 (OOP) 语言的主要功能之一是继承。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-103">One of the key features of Object Oriented Programming (OOP) languages is inheritance.</span></span> <span data-ttu-id="3c5f2-104">继承是功能的类的能够使用的所有现有以及这些功能无需重新编写原始类进行扩展。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-104">Inheritance is the ability to use all of the functionality of an existing class, and extend those capabilities without rewriting the original class.</span></span>  
  
 <span data-ttu-id="3c5f2-105">业务规则框架支持两种类型的类继承： 实现和接口。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-105">The Business Rules Framework supports two types of class inheritance: implementation and interface.</span></span> <span data-ttu-id="3c5f2-106">实现继承是指使用基类的属性和方法与任何其他编码的功能。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-106">Implementation inheritance refers to the ability to use a base class's properties and methods with no additional coding.</span></span> <span data-ttu-id="3c5f2-107">接口继承是指能够使用只是名称的属性和方法，但子类必须提供实现。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-107">Interface inheritance refers to the ability to use just the names of the properties and methods, but the child class must provide the implementation.</span></span>  
  
 <span data-ttu-id="3c5f2-108">可以在一个公共基类，方面编写规则，但添加到引擎的对象可以是从派生类。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-108">The rules can be written in terms of a common base class, but the objects asserted into the engine can be from derived classes.</span></span> <span data-ttu-id="3c5f2-109">在以下示例中， **RegularEmployee**并**ContractEmployee**是类的基类的派生的类**员工**。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-109">In the following example, **RegularEmployee** and **ContractEmployee** are derived classes of the base class **Employee**.</span></span>  
  
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
  
 <span data-ttu-id="3c5f2-110">假设您有以下规则。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-110">Assume you have the following rule.</span></span>  
  
## <a name="rule-1"></a><span data-ttu-id="3c5f2-111">规则 1</span><span class="sxs-lookup"><span data-stu-id="3c5f2-111">Rule 1</span></span>  
  
```  
IF Employee.TimeInMonths < 12  
THEN Employee.Status = "New"  
```  
  
 <span data-ttu-id="3c5f2-112">在运行时，如果用户添加两个对象，其中一个实例的**ContractEmployee**和其他实例的**RegularEmployee**，这两个对象实例根据所述的规则进行计算前面。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-112">At run time, if the user asserts two objects, one an instance of **ContractEmployee** and the other an instance of **RegularEmployee**, both the object instances are evaluated against the rule described earlier.</span></span>  
  
 <span data-ttu-id="3c5f2-113">用户还可以通过添加在操作的派生的类对象**Assert**。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-113">The user can also assert derived class objects in actions by using an **Assert**.</span></span> <span data-ttu-id="3c5f2-114">这会导致包含派生的对象和在其条件中的其基类型，都会重新计算，如下面的示例中所示的规则。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-114">This causes the rules that contain the derived object and its base type in their conditions to be re-evaluated, as shown in the following example.</span></span>  
  
## <a name="rule-2"></a><span data-ttu-id="3c5f2-115">规则 2</span><span class="sxs-lookup"><span data-stu-id="3c5f2-115">Rule 2</span></span>  
  
```  
IF Employee.Status = "Contract"   
THEN Employee.Bonus = false  
Assert(new ContractEmployee())  
```  
  
 <span data-ttu-id="3c5f2-116">包含的所有规则**员工**类型或**ContractEmployee**断言之后重新计算在其条件中的类型。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-116">All rules containing the **Employee** type or the **ContractEmployee** type in their conditions get re-evaluated after the assertion.</span></span> <span data-ttu-id="3c5f2-117">在此示例中的类型是继承的实现。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-117">The type of inheritance in this example is implementation.</span></span> <span data-ttu-id="3c5f2-118">即使添加仅在派生的类的基类那么也会添加如果编写使用基类而不是派生类中方法的规则。</span><span class="sxs-lookup"><span data-stu-id="3c5f2-118">Even though only the derived class is asserted, the base class also gets asserted if rules are written using methods in the base instead of the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c5f2-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c5f2-119">See Also</span></span>  
 [<span data-ttu-id="3c5f2-120">规则引擎</span><span class="sxs-lookup"><span data-stu-id="3c5f2-120">Rule Engine</span></span>](../core/rule-engine.md)