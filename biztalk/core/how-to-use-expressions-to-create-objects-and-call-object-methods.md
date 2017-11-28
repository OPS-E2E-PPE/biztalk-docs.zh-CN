---
title: "如何使用表达式来创建对象并调用对象方法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
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
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b56cfa46098569863106485fef204f72b23a4ef5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expressions-to-create-objects-and-call-object-methods"></a><span data-ttu-id="c26f2-102">如何使用表达式创建对象和调用对象方法</span><span class="sxs-lookup"><span data-stu-id="c26f2-102">How to Use Expressions to Create Objects and Call Object Methods</span></span>
<span data-ttu-id="c26f2-103">您可能会需要使用表达式来创建对象或调用方法。</span><span class="sxs-lookup"><span data-stu-id="c26f2-103">You might need to use expressions to create objects or invoke methods.</span></span>  
  
## <a name="creating-objects"></a><span data-ttu-id="c26f2-104">创建对象</span><span class="sxs-lookup"><span data-stu-id="c26f2-104">Creating objects</span></span>  
 <span data-ttu-id="c26f2-105">若要创建具有是一个.NET 类的类型的变量，你构造中的某个对象**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="c26f2-105">To create a variable that has a type which is a .NET class, you construct an object in the **Expression** shape.</span></span> <span data-ttu-id="c26f2-106">.NET 类变量的属性包括构造函数。</span><span class="sxs-lookup"><span data-stu-id="c26f2-106">The properties of your .NET class variable include a constructor.</span></span> <span data-ttu-id="c26f2-107">如果使用默认构造函数，则只需直接声明该变量即可，就像声明任何其他变量（如 bool 类型或 int 类型）一样。</span><span class="sxs-lookup"><span data-stu-id="c26f2-107">If you use the default constructor, you simply declare the variable directly as you would any other variable, like one of type bool or int.</span></span>  
  
 <span data-ttu-id="c26f2-108">如果你使用的构造函数的参数，则使用关键字**新**后, 跟对象类和任何参数在括号中：</span><span class="sxs-lookup"><span data-stu-id="c26f2-108">If you use a constructor that takes parameters, you use the keyword **new**, followed by the object class and any parameters in parentheses:</span></span>  
  
```  
new MyClass(myParam1, myParam2)  
```  
  
> [!CAUTION]
>  <span data-ttu-id="c26f2-109">**使用默认构造函数**属性执行操作，事实上，某些对象具有构造函数可能不会显示。</span><span class="sxs-lookup"><span data-stu-id="c26f2-109">The **Use Default Constructor** property might not be displayed for some objects that do, in fact, have constructors.</span></span> <span data-ttu-id="c26f2-110">在这种情况下，将自动使用默认构造函数。如果试图使用其他构造函数，则将会产生错误。</span><span class="sxs-lookup"><span data-stu-id="c26f2-110">In this case, the default constructor will be used automatically, and an error will be raised if you attempt to use a different constructor.</span></span>  
  
## <a name="invoking-methods"></a><span data-ttu-id="c26f2-111">调用方法</span><span class="sxs-lookup"><span data-stu-id="c26f2-111">Invoking methods</span></span>  
 <span data-ttu-id="c26f2-112">若要对 .NET 类对象调用方法，则需要向对象引用中附加一个句点和方法名称，后跟所有参数（括在括号中）：</span><span class="sxs-lookup"><span data-stu-id="c26f2-112">To invoke a method on a .NET class object, you append a period and the name of the method to the object reference, followed by any parameters in parentheses:</span></span>  
  
```  
MyObject.MyMethod (param1)  
```  
  
## <a name="passing-and-using-messages-as-parameters"></a><span data-ttu-id="c26f2-113">将消息作为参数进行传递和使用</span><span class="sxs-lookup"><span data-stu-id="c26f2-113">Passing and using messages as parameters</span></span>  
 <span data-ttu-id="c26f2-114">若要将消息作为参数传递给对 .NET 类调用的方法，请首先在定义该类的项目中添加对 Microsoft.XLANGs.BaseTypes.dll 的引用，然后在方法签名中使用类型 XLANGMessage。</span><span class="sxs-lookup"><span data-stu-id="c26f2-114">To pass a message as a parameter to a method call on a .NET class, you first add a reference to Microsoft.XLANGs.BaseTypes.dll in the project that defines the class, and then use the type XLANGMessage in the method signature.</span></span>  
  
 <span data-ttu-id="c26f2-115">通过引用多部分消息类型，您可以使用类型 XLANGPart 来访问消息的各个部分：</span><span class="sxs-lookup"><span data-stu-id="c26f2-115">Referencing the multi-part message type enables you to access the various parts of the message by using the type XLANGPart:</span></span>  
  
```  
MyMethod(XLANGMessage myMsg)  
{  
XLANGPart myPart = myMsg["Part1"];  
XmlDocument xmlDoc = (XmlDocument) myPart.RetrieveAs(typeof(XmlDocument));  
}  
```  
  
 <span data-ttu-id="c26f2-116">对于调用本身，您只需提供消息的名称，就像使用任何其他参数一样：</span><span class="sxs-lookup"><span data-stu-id="c26f2-116">In the call itself, you simply supply the name of the message as you would any other parameter:</span></span>  
  
```  
MyObject.MyMethod(myMessage)  
```  
  
 <span data-ttu-id="c26f2-117">您还可以将消息部分作为类型 XLANGPart 来传递。</span><span class="sxs-lookup"><span data-stu-id="c26f2-117">You can also pass a message part as type XLANGPart.</span></span>  
  
## <a name="net-member-invocation"></a><span data-ttu-id="c26f2-118">.NET 成员调用</span><span class="sxs-lookup"><span data-stu-id="c26f2-118">.NET member invocation</span></span>  
 <span data-ttu-id="c26f2-119">可以访问公共成员，但直接访问消息部分的成员除外。</span><span class="sxs-lookup"><span data-stu-id="c26f2-119">You can access public members except in the case of direct access to members of a message part.</span></span> <span data-ttu-id="c26f2-120">若要直接访问消息部分的成员，必须将其升级为可分辨字段。</span><span class="sxs-lookup"><span data-stu-id="c26f2-120">To directly access a member of a message part it must be promoted as a distinguished field.</span></span>  
  
## <a name="comcom-component-invocation"></a><span data-ttu-id="c26f2-121">COM/COM+ 组件调用</span><span class="sxs-lookup"><span data-stu-id="c26f2-121">COM/COM+ component invocation</span></span>  
 <span data-ttu-id="c26f2-122">XLANGs 生成 C# 代码。</span><span class="sxs-lookup"><span data-stu-id="c26f2-122">XLANGs generates C# code.</span></span> <span data-ttu-id="c26f2-123">所有用户声明的 XLANGs 变量都作为 C# 变量生成。</span><span class="sxs-lookup"><span data-stu-id="c26f2-123">All user-declared XLANGs variables are generated as C# variables.</span></span> <span data-ttu-id="c26f2-124">除了原子事务外，不存在其他特殊行为。</span><span class="sxs-lookup"><span data-stu-id="c26f2-124">There is no special behavior except in the case of atomic transactions.</span></span> <span data-ttu-id="c26f2-125">时维护的组件 (即，实现类的实例**System.EnterpriseServices.ServicedComponent**) 然后并仅声明在原子作用域，则不 XLANGs 生成和使用实际的 DTC COM + 事务。</span><span class="sxs-lookup"><span data-stu-id="c26f2-125">When a serviced component (that is, an instance of a class that implements **System.EnterpriseServices.ServicedComponent**) is declared in an atomic scope, then and only then does XLANGs generate and use a real DTC COM+ transaction.</span></span>  
  
 <span data-ttu-id="c26f2-126">如果某一变量在原子作用域中作为 L 值（即，它被写入）引用，但在外部作用域中声明，则将克隆该变量以支持回滚。</span><span class="sxs-lookup"><span data-stu-id="c26f2-126">If a variable is referenced as an L-value (that is, it is written to) in the atomic scope, but is declared in an outer scope, the variable is cloned to support rollback.</span></span> <span data-ttu-id="c26f2-127">但是，一个对象 (如**XmlDocument**) 可以修改调用内部的.NET 函数作为参数传递时中的并因此 XLANGs 将丢失该对象正在写入到和它将不回滚正确。</span><span class="sxs-lookup"><span data-stu-id="c26f2-127">However, an object (such as an **XmlDocument**) can be modified inside a .NET function call when passed as an in-parameter, and thus XLANGs will miss that the object is being written to and it will not roll back correctly.</span></span> <span data-ttu-id="c26f2-128">此情况下的解决方法就是将此类对象作为 ref 参数传递。</span><span class="sxs-lookup"><span data-stu-id="c26f2-128">The workaround in this case is to pass such objects as ref parameters.</span></span>  
  
 <span data-ttu-id="c26f2-129">起码组件在行为上应与在其他 C# 程序中的行为一样。</span><span class="sxs-lookup"><span data-stu-id="c26f2-129">The bottom line is that components should behave as they do in other C# programs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c26f2-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c26f2-130">See Also</span></span>  
 [<span data-ttu-id="c26f2-131">有关 BizTalk 消息上下文属性</span><span class="sxs-lookup"><span data-stu-id="c26f2-131">About BizTalk Message Context Properties</span></span>](../core/about-biztalk-message-context-properties.md)