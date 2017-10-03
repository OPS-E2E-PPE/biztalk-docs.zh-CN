---
title: "可以为 Null 的类型的支持 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a5ea191-09d5-47ab-a197-390fbbcf6306
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: abd277db970a00e9d7d8f20de65e85c607c2a861
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="support-for-nullable-types"></a><span data-ttu-id="63b8e-102">可以为 Null 的类型的支持</span><span class="sxs-lookup"><span data-stu-id="63b8e-102">Support for Nullable Types</span></span>
<span data-ttu-id="63b8e-103">规则引擎支持业务规则中使用可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="63b8e-103">The rule engine supports using nullable types in a business rule.</span></span> <span data-ttu-id="63b8e-104">你可以使用.NET 类绑定、 XML 绑定和数据库绑定中可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="63b8e-104">You can use nullable types in .NET class bindings, XML bindings, and database bindings.</span></span> <span data-ttu-id="63b8e-105">目前，业务规则编辑器工具不支持业务规则中使用可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="63b8e-105">Currently, the Business Rule Composer tool does not support using nullable types in a business rule.</span></span> <span data-ttu-id="63b8e-106">以编程方式创建规则时，你可以使用可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="63b8e-106">You can use the nullable types when creating rules programmatically.</span></span>  
  
## <a name="using-nullable-types-in-net-class-bindings"></a><span data-ttu-id="63b8e-107">在.NET 类绑定中使用可以为 Null 的类型</span><span class="sxs-lookup"><span data-stu-id="63b8e-107">Using Nullable Types in .NET Class Bindings</span></span>  
 <span data-ttu-id="63b8e-108">你可以创建绑定到的属性或其类型为 null 的类型的字段的类成员。</span><span class="sxs-lookup"><span data-stu-id="63b8e-108">You can create a class member binding to a property or a field whose type is a nullable type.</span></span> <span data-ttu-id="63b8e-109">你还可以创建绑定到采用可以为 null 的类型的参数和/或返回值为 null 的类型的方法的类成员。</span><span class="sxs-lookup"><span data-stu-id="63b8e-109">You can also create a class member binding to a method that takes a parameter of nullable type and/or returns a value of nullable type.</span></span> <span data-ttu-id="63b8e-110">下面的示例代码演示如何访问的可以为 null 的字段，以及如何从业务规则中的方法访问可以为 null 的类型的返回值。</span><span class="sxs-lookup"><span data-stu-id="63b8e-110">The following sample code demonstrates how to access a nullable field, and how to access a return value of nullable type from a method in a business rule.</span></span> <span data-ttu-id="63b8e-111">如果按原样执行一个控制台应用程序替换为以下代码，你将看到的值**prop**字段设置为 5。</span><span class="sxs-lookup"><span data-stu-id="63b8e-111">If you execute a console application with the following code as it is, you will see that the value of the **prop** field is set to 5.</span></span> <span data-ttu-id="63b8e-112">如果未初始化**prop**在类字段或将其初始化以 null，并且运行这些代码，你将看到的值**prop**字段设置为 1。</span><span class="sxs-lookup"><span data-stu-id="63b8e-112">If you do not initialize the **prop** field in the class or initialize it to null and run the code, you will see that the value of the **prop** field is set to 1.</span></span>  
  
```  
using Microsoft.RuleEngine;  
namespace UseNullableAsm  
{  
    class Program  
    {  
        public class Class1  
        {  
            public int? prop = 1;  
            private int? prop2 = 4;  
            public int? GetProp2()  
            {  
                return prop2;  
            }  
        }  
  
        static void Main(string[] args)  
        {  
            //Create the class binding for the Class1 class  
            ClassBinding cbCls1 = new ClassBinding(typeof(Class1));  
  
            //Create the class member binding to the GetProp2 method of Cls1 class  
            ClassMemberBinding cmGetProp2 = new ClassMemberBinding("GetProp2", cbCls1);  
  
            //Create the class member binding to the to GET the value of prop  
            ClassMemberBinding cmGetProp = new ClassMemberBinding("prop", cbCls1);  
  
            //Create arguments for the prop1 field, which is prop1 + GetProp2()  
            UserFunction ufGetProp = new UserFunction(cmGetProp);  
            Add addArg = new Add(ufGetProp, new UserFunction(cmGetProp2));  
            ArgumentCollection al1 = new ArgumentCollection();  
            al1.Add(addArg);  
  
            //Set the value of prop to prop1 + cmGetPro2()  
            ClassMemberBinding cmProp = new ClassMemberBinding("prop", cbCls1, al1);  
  
            //Create a userfunction based on cmProp and add to the action collection  
            UserFunction ufProp = new UserFunction(cmProp);  
            ActionCollection ac = new ActionCollection();  
            ac.Add(ufProp);  
  
            //Create the condition list IF prop == 1  
            Equal eq = new Equal(ufGetProp, new Constant(1));  
  
            //Create the rule   
            // If (prop == 1)  
            // Then prop = prop + GetProp2()  
            Rule rl = new Rule("NullableTestRule", eq, ac);  
  
            //Create the condition list IF prop != 1  
            NotEqual neq = new NotEqual(ufGetProp, new Constant(1));  
  
            //Set the value of prop to prop to 1  
            Constant ct = new Constant(1);  
            ArgumentCollection al2 = new ArgumentCollection();  
            al2.Add(ct);  
  
            //Create class member binding to prop field with argument value 1  
            ClassMemberBinding cmSetProp = new ClassMemberBinding("prop", cbCls1, al2);  
  
            //Create a userfunction based on cmSetProp and add to the action collection  
            UserFunction ufSetProp = new UserFunction(cmSetProp);  
            ActionCollection ac2 = new ActionCollection();  
            ac2.Add(ufSetProp);  
  
            //Create the second rule   
            // If (prop != 1)  
            // Then prop = 1  
            Rule rl2 = new Rule("NullableTestRule2", neq, ac2);  
  
            //Create the policy and add both the rules to the policy  
            RuleSet rs = new RuleSet("NulableTestPolicy");  
            rs.Rules.Add(rl);  
            rs.Rules.Add(rl2);  
  
            //Create the .NET object fact  
            Class1 cls1Obj = new Class1();  
  
            //Print the value of the field prop before executing the policy  
            Console.WriteLine("Value of the prop field is " + cls1Obj.prop);  
  
            //Execute the policy  
            PolicyTester pt = new PolicyTester(rs);  
            pt.Execute(cls1Obj);  
  
            //Print the value of the field prop after executing the policy  
            Console.WriteLine("Value of the prop field is " + cls1Obj.prop);  
        }  
    }  
}  
```  
  
## <a name="using-nullable-types-in-database-bindings"></a><span data-ttu-id="63b8e-113">在数据库绑定中使用可以为 Null 的类型</span><span class="sxs-lookup"><span data-stu-id="63b8e-113">Using Nullable Types in Database Bindings</span></span>  
 <span data-ttu-id="63b8e-114">此外可以在数据库的绑定中使用可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="63b8e-114">You can also use nullable types in database bindings.</span></span> <span data-ttu-id="63b8e-115">下面的示例代码段演示如何在数据库绑定中使用可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="63b8e-115">The following sample code fragment shows you how to use a nullable type in database bindings.</span></span>  
  
```  
DataColumnBinding dcBinding = new DataColumnBinding(“col”, typeof(int?), dbBinding);  
```  
  
 <span data-ttu-id="63b8e-116">假设你有具有检查的值的条件的规则的数据库列以查看是否等于 3。</span><span class="sxs-lookup"><span data-stu-id="63b8e-116">Suppose you have a rule with a condition that checks the value of a database column to see if equals 3.</span></span> <span data-ttu-id="63b8e-117">如果列的值为 null，表达式的计算结果为 false。</span><span class="sxs-lookup"><span data-stu-id="63b8e-117">If the value of the column is null, the expression evaluates to false.</span></span> <span data-ttu-id="63b8e-118">它不会导致异常。</span><span class="sxs-lookup"><span data-stu-id="63b8e-118">It does not cause an exception.</span></span>  
  
## <a name="using-nullable-types-in-xml-bindings"></a><span data-ttu-id="63b8e-119">在 XML 绑定中使用可以为 Null 的类型</span><span class="sxs-lookup"><span data-stu-id="63b8e-119">Using Nullable Types in XML Bindings</span></span>  
 <span data-ttu-id="63b8e-120">同样，你可以在 XML 的绑定中使用可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="63b8e-120">Similarly, you can use nullable types in XML bindings.</span></span> <span data-ttu-id="63b8e-121">下面的示例代码段演示如何在 XML 绑定中使用可以为 null 的类型。</span><span class="sxs-lookup"><span data-stu-id="63b8e-121">The following sample code fragment shows how to use a nullable type in XML bindings.</span></span>  
  
```  
XMLDocumentFieldBinding xfb1 = new XMLDocumentFieldBinding(typeof(int?),"ID",xdb);  
```