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
# <a name="support-for-class-inheritance-in-the-business-rule-engine"></a><span data-ttu-id="3c485-102">业务规则引擎中对类继承的支持</span><span class="sxs-lookup"><span data-stu-id="3c485-102">Support for Class Inheritance in the Business Rule Engine</span></span>
<span data-ttu-id="3c485-103">面向对象编程 (OOP) 语言的主要功能之一是继承。</span><span class="sxs-lookup"><span data-stu-id="3c485-103">One of the key features of Object Oriented Programming (OOP) languages is inheritance.</span></span> <span data-ttu-id="3c485-104">通过继承，可以使用现有类的所有功能，并且无需重新编写原始类就可以对这些功能进行扩展。</span><span class="sxs-lookup"><span data-stu-id="3c485-104">Inheritance is the ability to use all of the functionality of an existing class, and extend those capabilities without rewriting the original class.</span></span>  
  
 <span data-ttu-id="3c485-105">业务规则框架支持两种类型的类继承：实现和接口。</span><span class="sxs-lookup"><span data-stu-id="3c485-105">The Business Rules Framework supports two types of class inheritance: implementation and interface.</span></span> <span data-ttu-id="3c485-106">实现继承是指使用基类的属性和方法而不进行额外编码的能力。</span><span class="sxs-lookup"><span data-stu-id="3c485-106">Implementation inheritance refers to the ability to use a base class's properties and methods with no additional coding.</span></span> <span data-ttu-id="3c485-107">接口继承是指只使用属性和方法的名称，但子类必须提供实现的能力。</span><span class="sxs-lookup"><span data-stu-id="3c485-107">Interface inheritance refers to the ability to use just the names of the properties and methods, but the child class must provide the implementation.</span></span>  
  
 <span data-ttu-id="3c485-108">规则可以按照常见基类进行编写，但添加到引擎中的对象可以来自派生类。</span><span class="sxs-lookup"><span data-stu-id="3c485-108">The rules can be written in terms of a common base class, but the objects asserted into the engine can be from derived classes.</span></span> <span data-ttu-id="3c485-109">在下面的示例中， **RegularEmployee**和**ContractEmployee**是基本类的派生的类**员工**。</span><span class="sxs-lookup"><span data-stu-id="3c485-109">In the following example, **RegularEmployee** and **ContractEmployee** are derived classes of the base class **Employee**.</span></span>  
  
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
  
 <span data-ttu-id="3c485-110">假定你具有以下规则。</span><span class="sxs-lookup"><span data-stu-id="3c485-110">Assume you have the following rule.</span></span>  
  
## <a name="rule-1"></a><span data-ttu-id="3c485-111">规则 1</span><span class="sxs-lookup"><span data-stu-id="3c485-111">Rule 1</span></span>  
  
```  
IF Employee.TimeInMonths < 12  
THEN Employee.Status = "New"  
```  
  
 <span data-ttu-id="3c485-112">在运行时，如果用户断言两个对象，其中一个实例的**ContractEmployee**和其他实例的**RegularEmployee**，针对所述的规则进行了评估两个对象实例更早版本。</span><span class="sxs-lookup"><span data-stu-id="3c485-112">At run time, if the user asserts two objects, one an instance of **ContractEmployee** and the other an instance of **RegularEmployee**, both the object instances are evaluated against the rule described earlier.</span></span>  
  
 <span data-ttu-id="3c485-113">用户还可以通过使用断言中操作的派生的类对象**断言**。</span><span class="sxs-lookup"><span data-stu-id="3c485-113">The user can also assert derived class objects in actions by using an **Assert**.</span></span> <span data-ttu-id="3c485-114">这将导致在其条件中包含派生对象及其基本类型的规则重新计算，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="3c485-114">This causes the rules that contain the derived object and its base type in their conditions to be re-evaluated, as shown in the following example.</span></span>  
  
## <a name="rule-2"></a><span data-ttu-id="3c485-115">规则 2</span><span class="sxs-lookup"><span data-stu-id="3c485-115">Rule 2</span></span>  
  
```  
IF Employee.Status = "Contract"   
THEN Employee.Bonus = false  
Assert(new ContractEmployee())  
```  
  
 <span data-ttu-id="3c485-116">包含的所有规则**员工**类型或**ContractEmployee**断言后获取重新评估其条件中的类型。</span><span class="sxs-lookup"><span data-stu-id="3c485-116">All rules containing the **Employee** type or the **ContractEmployee** type in their conditions get re-evaluated after the assertion.</span></span> <span data-ttu-id="3c485-117">在此示例中，继承的类型是实现。</span><span class="sxs-lookup"><span data-stu-id="3c485-117">The type of inheritance in this example is implementation.</span></span> <span data-ttu-id="3c485-118">即使只添加派生类，但如果使用基类而不是派生类中的方法来编写规则，那么也会添加基类。</span><span class="sxs-lookup"><span data-stu-id="3c485-118">Even though only the derived class is asserted, the base class also gets asserted if rules are written using methods in the base instead of the derived class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c485-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3c485-119">See Also</span></span>  
 [<span data-ttu-id="3c485-120">规则引擎</span><span class="sxs-lookup"><span data-stu-id="3c485-120">Rule Engine</span></span>](../core/rule-engine.md)