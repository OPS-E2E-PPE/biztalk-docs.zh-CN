---
title: 如何使用表达式创建对象和调用对象方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, parameters
- Expression shape [Orchestration Designer], calling objects
- Expression shape [Orchestration Designer], parameters
- Expression shape [Orchestration Designer], passing messages
- orchestrations, methods
- Expression shape [Orchestration Designer], calling methods
- orchestrations, objects
- Expression shape [Orchestration Designer], warning
- Use Default Constructor property
- .NET member invocation
ms.assetid: b6af67eb-8ba5-4c95-9b63-26ebb6617af0
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: adf0be16b7fa0fc78788386159672ce94823bbcc
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383443"
---
# <a name="how-to-use-expressions-to-create-objects-and-call-object-methods"></a><span data-ttu-id="2275b-102">如何使用表达式创建对象和调用对象方法</span><span class="sxs-lookup"><span data-stu-id="2275b-102">How to Use Expressions to Create Objects and Call Object Methods</span></span>
<span data-ttu-id="2275b-103">您可能需要使用表达式来创建对象或调用方法。</span><span class="sxs-lookup"><span data-stu-id="2275b-103">You might need to use expressions to create objects or invoke methods.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="2275b-104">创建对象</span><span class="sxs-lookup"><span data-stu-id="2275b-104">Creating objects</span></span>  
 <span data-ttu-id="2275b-105">若要创建具有是一个.NET 类的类型的变量，构造中的对象**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="2275b-105">To create a variable that has a type which is a .NET class, you construct an object in the **Expression** shape.</span></span> <span data-ttu-id="2275b-106">.NET 类变量的属性包括构造函数。</span><span class="sxs-lookup"><span data-stu-id="2275b-106">The properties of your .NET class variable include a constructor.</span></span> <span data-ttu-id="2275b-107">如果使用默认构造函数，只需声明该变量直接就像任何其他变量，如一个 bool 类型或 int。</span><span class="sxs-lookup"><span data-stu-id="2275b-107">If you use the default constructor, you simply declare the variable directly as you would any other variable, like one of type bool or int.</span></span>  
  
 <span data-ttu-id="2275b-108">如果你使用采用参数的构造函数，使用关键字**新**后, 跟对象类和中括号的任何参数：</span><span class="sxs-lookup"><span data-stu-id="2275b-108">If you use a constructor that takes parameters, you use the keyword **new**, followed by the object class and any parameters in parentheses:</span></span>  
  
```  
new MyClass(myParam1, myParam2)  
```  
  
> [!CAUTION]
>  <span data-ttu-id="2275b-109">**使用默认构造器**属性执行操作，事实上，某些对象具有构造函数可能不会显示。</span><span class="sxs-lookup"><span data-stu-id="2275b-109">The **Use Default Constructor** property might not be displayed for some objects that do, in fact, have constructors.</span></span> <span data-ttu-id="2275b-110">在这种情况下，将自动使用默认构造函数，如果你尝试使用其他构造函数将引发错误。</span><span class="sxs-lookup"><span data-stu-id="2275b-110">In this case, the default constructor will be used automatically, and an error will be raised if you attempt to use a different constructor.</span></span>  
  
## <a name="invoking-methods"></a><span data-ttu-id="2275b-111">调用方法</span><span class="sxs-lookup"><span data-stu-id="2275b-111">Invoking methods</span></span>  
 <span data-ttu-id="2275b-112">若要调用.NET 类对象上的方法，您将一个句点和方法的名称追加到跟在括号中的所有参数的对象引用：</span><span class="sxs-lookup"><span data-stu-id="2275b-112">To invoke a method on a .NET class object, you append a period and the name of the method to the object reference, followed by any parameters in parentheses:</span></span>  
  
```  
MyObject.MyMethod (param1)  
```  
  
## <a name="passing-and-using-messages-as-parameters"></a><span data-ttu-id="2275b-113">传递，并且使用消息作为参数</span><span class="sxs-lookup"><span data-stu-id="2275b-113">Passing and using messages as parameters</span></span>  
 <span data-ttu-id="2275b-114">若要一条消息作为参数传递到方法调用.NET 类上，您首先在定义类，该项目中添加对 Microsoft.XLANGs.BaseTypes.dll 的引用，，然后使用类型 XLANGMessage 方法签名中。</span><span class="sxs-lookup"><span data-stu-id="2275b-114">To pass a message as a parameter to a method call on a .NET class, you first add a reference to Microsoft.XLANGs.BaseTypes.dll in the project that defines the class, and then use the type XLANGMessage in the method signature.</span></span>  
  
 <span data-ttu-id="2275b-115">引用多部分消息类型，可通过使用类型 XLANGPart 来访问消息的各个部分：</span><span class="sxs-lookup"><span data-stu-id="2275b-115">Referencing the multi-part message type enables you to access the various parts of the message by using the type XLANGPart:</span></span>  
  
```  
MyMethod(XLANGMessage myMsg)  
{  
XLANGPart myPart = myMsg["Part1"];  
XmlDocument xmlDoc = (XmlDocument) myPart.RetrieveAs(typeof(XmlDocument));  
}  
```  
  
 <span data-ttu-id="2275b-116">对于调用本身，您可以像任何其他参数只需提供到消息的名称：</span><span class="sxs-lookup"><span data-stu-id="2275b-116">In the call itself, you simply supply the name of the message as you would any other parameter:</span></span>  
  
```  
MyObject.MyMethod(myMessage)  
```  
  
 <span data-ttu-id="2275b-117">此外可以作为类型 XLANGPart 来传递消息部分。</span><span class="sxs-lookup"><span data-stu-id="2275b-117">You can also pass a message part as type XLANGPart.</span></span>  
  
## <a name="net-member-invocation"></a><span data-ttu-id="2275b-118">.NET 成员调用</span><span class="sxs-lookup"><span data-stu-id="2275b-118">.NET member invocation</span></span>  
 <span data-ttu-id="2275b-119">您可以访问公共成员除外直接访问消息部分的成员。</span><span class="sxs-lookup"><span data-stu-id="2275b-119">You can access public members except in the case of direct access to members of a message part.</span></span> <span data-ttu-id="2275b-120">若要直接访问消息部分必须将其升级为可分辨字段的成员。</span><span class="sxs-lookup"><span data-stu-id="2275b-120">To directly access a member of a message part it must be promoted as a distinguished field.</span></span>  
  
## <a name="comcom-component-invocation"></a><span data-ttu-id="2275b-121">COM / COM + 组件调用</span><span class="sxs-lookup"><span data-stu-id="2275b-121">COM/COM+ component invocation</span></span>  
 <span data-ttu-id="2275b-122">XLANGs 生成C#代码。</span><span class="sxs-lookup"><span data-stu-id="2275b-122">XLANGs generates C# code.</span></span> <span data-ttu-id="2275b-123">所有用户声明的 XLANGs 变量在都生成的C#变量。</span><span class="sxs-lookup"><span data-stu-id="2275b-123">All user-declared XLANGs variables are generated as C# variables.</span></span> <span data-ttu-id="2275b-124">除在原子事务的情况下，没有特殊行为。</span><span class="sxs-lookup"><span data-stu-id="2275b-124">There is no special behavior except in the case of atomic transactions.</span></span> <span data-ttu-id="2275b-125">当服务组件 (即，实现的类的实例**System.EnterpriseServices.ServicedComponent**)，只有在原子作用域中声明则 XLANGs 会生成和使用真正的 DTC COM + 事务。</span><span class="sxs-lookup"><span data-stu-id="2275b-125">When a serviced component (that is, an instance of a class that implements **System.EnterpriseServices.ServicedComponent**) is declared in an atomic scope, then and only then does XLANGs generate and use a real DTC COM+ transaction.</span></span>  
  
 <span data-ttu-id="2275b-126">如果为左值引用变量 （也就是说，它将写入到） 在原子作用域，但被声明在外部作用域，该变量克隆以支持回滚。</span><span class="sxs-lookup"><span data-stu-id="2275b-126">If a variable is referenced as an L-value (that is, it is written to) in the atomic scope, but is declared in an outer scope, the variable is cloned to support rollback.</span></span> <span data-ttu-id="2275b-127">但是，一个对象 (如**XmlDocument**) 可以修改在.NET 函数调用时传递为 in 参数，并因此，xlangs 将正在写入到该对象，它将不回滚正确。</span><span class="sxs-lookup"><span data-stu-id="2275b-127">However, an object (such as an **XmlDocument**) can be modified inside a .NET function call when passed as an in-parameter, and thus XLANGs will miss that the object is being written to and it will not roll back correctly.</span></span> <span data-ttu-id="2275b-128">在这种情况下解决方法是将此类对象作为 ref 参数传递。</span><span class="sxs-lookup"><span data-stu-id="2275b-128">The workaround in this case is to pass such objects as ref parameters.</span></span>  
  
 <span data-ttu-id="2275b-129">底线是组件的行为与在其他C#程序。</span><span class="sxs-lookup"><span data-stu-id="2275b-129">The bottom line is that components should behave as they do in other C# programs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2275b-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="2275b-130">See Also</span></span>  
 [<span data-ttu-id="2275b-131">关于 BizTalk 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="2275b-131">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)