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
# <a name="how-to-use-expressions-to-create-objects-and-call-object-methods"></a>如何使用表达式创建对象和调用对象方法
您可能会需要使用表达式来创建对象或调用方法。  
  
## <a name="creating-objects"></a>创建对象  
 若要创建具有是一个.NET 类的类型的变量，你构造中的某个对象**表达式**形状。 .NET 类变量的属性包括构造函数。 如果使用默认构造函数，则只需直接声明该变量即可，就像声明任何其他变量（如 bool 类型或 int 类型）一样。  
  
 如果你使用的构造函数的参数，则使用关键字**新**后, 跟对象类和任何参数在括号中：  
  
```  
new MyClass(myParam1, myParam2)  
```  
  
> [!CAUTION]
>  **使用默认构造函数**属性执行操作，事实上，某些对象具有构造函数可能不会显示。 在这种情况下，将自动使用默认构造函数。如果试图使用其他构造函数，则将会产生错误。  
  
## <a name="invoking-methods"></a>调用方法  
 若要对 .NET 类对象调用方法，则需要向对象引用中附加一个句点和方法名称，后跟所有参数（括在括号中）：  
  
```  
MyObject.MyMethod (param1)  
```  
  
## <a name="passing-and-using-messages-as-parameters"></a>将消息作为参数进行传递和使用  
 若要将消息作为参数传递给对 .NET 类调用的方法，请首先在定义该类的项目中添加对 Microsoft.XLANGs.BaseTypes.dll 的引用，然后在方法签名中使用类型 XLANGMessage。  
  
 通过引用多部分消息类型，您可以使用类型 XLANGPart 来访问消息的各个部分：  
  
```  
MyMethod(XLANGMessage myMsg)  
{  
XLANGPart myPart = myMsg["Part1"];  
XmlDocument xmlDoc = (XmlDocument) myPart.RetrieveAs(typeof(XmlDocument));  
}  
```  
  
 对于调用本身，您只需提供消息的名称，就像使用任何其他参数一样：  
  
```  
MyObject.MyMethod(myMessage)  
```  
  
 您还可以将消息部分作为类型 XLANGPart 来传递。  
  
## <a name="net-member-invocation"></a>.NET 成员调用  
 可以访问公共成员，但直接访问消息部分的成员除外。 若要直接访问消息部分的成员，必须将其升级为可分辨字段。  
  
## <a name="comcom-component-invocation"></a>COM/COM+ 组件调用  
 XLANGs 生成 C# 代码。 所有用户声明的 XLANGs 变量都作为 C# 变量生成。 除了原子事务外，不存在其他特殊行为。 时维护的组件 (即，实现类的实例**System.EnterpriseServices.ServicedComponent**) 然后并仅声明在原子作用域，则不 XLANGs 生成和使用实际的 DTC COM + 事务。  
  
 如果某一变量在原子作用域中作为 L 值（即，它被写入）引用，但在外部作用域中声明，则将克隆该变量以支持回滚。 但是，一个对象 (如**XmlDocument**) 可以修改调用内部的.NET 函数作为参数传递时中的并因此 XLANGs 将丢失该对象正在写入到和它将不回滚正确。 此情况下的解决方法就是将此类对象作为 ref 参数传递。  
  
 起码组件在行为上应与在其他 C# 程序中的行为一样。  
  
## <a name="see-also"></a>另请参阅  
 [有关 BizTalk 消息上下文属性](../core/about-biztalk-message-context-properties.md)