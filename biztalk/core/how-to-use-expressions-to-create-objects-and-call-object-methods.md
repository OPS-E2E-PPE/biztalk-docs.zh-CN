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
# <a name="how-to-use-expressions-to-create-objects-and-call-object-methods"></a>如何使用表达式创建对象和调用对象方法
您可能需要使用表达式来创建对象或调用方法。  
  
## <a name="creating-objects"></a>创建对象  
 若要创建具有是一个.NET 类的类型的变量，构造中的对象**表达式**形状。 .NET 类变量的属性包括构造函数。 如果使用默认构造函数，只需声明该变量直接就像任何其他变量，如一个 bool 类型或 int。  
  
 如果你使用采用参数的构造函数，使用关键字**新**后, 跟对象类和中括号的任何参数：  
  
```  
new MyClass(myParam1, myParam2)  
```  
  
> [!CAUTION]
>  **使用默认构造器**属性执行操作，事实上，某些对象具有构造函数可能不会显示。 在这种情况下，将自动使用默认构造函数，如果你尝试使用其他构造函数将引发错误。  
  
## <a name="invoking-methods"></a>调用方法  
 若要调用.NET 类对象上的方法，您将一个句点和方法的名称追加到跟在括号中的所有参数的对象引用：  
  
```  
MyObject.MyMethod (param1)  
```  
  
## <a name="passing-and-using-messages-as-parameters"></a>传递，并且使用消息作为参数  
 若要一条消息作为参数传递到方法调用.NET 类上，您首先在定义类，该项目中添加对 Microsoft.XLANGs.BaseTypes.dll 的引用，，然后使用类型 XLANGMessage 方法签名中。  
  
 引用多部分消息类型，可通过使用类型 XLANGPart 来访问消息的各个部分：  
  
```  
MyMethod(XLANGMessage myMsg)  
{  
XLANGPart myPart = myMsg["Part1"];  
XmlDocument xmlDoc = (XmlDocument) myPart.RetrieveAs(typeof(XmlDocument));  
}  
```  
  
 对于调用本身，您可以像任何其他参数只需提供到消息的名称：  
  
```  
MyObject.MyMethod(myMessage)  
```  
  
 此外可以作为类型 XLANGPart 来传递消息部分。  
  
## <a name="net-member-invocation"></a>.NET 成员调用  
 您可以访问公共成员除外直接访问消息部分的成员。 若要直接访问消息部分必须将其升级为可分辨字段的成员。  
  
## <a name="comcom-component-invocation"></a>COM / COM + 组件调用  
 XLANGs 生成C#代码。 所有用户声明的 XLANGs 变量在都生成的C#变量。 除在原子事务的情况下，没有特殊行为。 当服务组件 (即，实现的类的实例**System.EnterpriseServices.ServicedComponent**)，只有在原子作用域中声明则 XLANGs 会生成和使用真正的 DTC COM + 事务。  
  
 如果为左值引用变量 （也就是说，它将写入到） 在原子作用域，但被声明在外部作用域，该变量克隆以支持回滚。 但是，一个对象 (如**XmlDocument**) 可以修改在.NET 函数调用时传递为 in 参数，并因此，xlangs 将正在写入到该对象，它将不回滚正确。 在这种情况下解决方法是将此类对象作为 ref 参数传递。  
  
 底线是组件的行为与在其他C#程序。  
  
## <a name="see-also"></a>请参阅  
 [关于 BizTalk 消息上下文属性](../core/about-biztalk-message-context-properties.md)