---
title: 消息表示为.NET 类 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, expressions
- orchestrations, filters
ms.assetid: cdbea200-552e-4734-a370-2f93da07ea81
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a01e0c5834e117a16541f8dee45218285f05e0f4
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531179"
---
# <a name="messages-represented-as-net-classes"></a>表示为.NET 类的消息
此方法首先需要创建一个定义消息类型的.NET 类。 此类必须具有默认构造函数或使用它的业务流程将不进行编译。 这样的类的一个简单示例如下所示。  
  
```  
using System;  
using Microsoft.XLANGs.BaseTypes;  
Using PropertyNamespace;  
  
namespace NetClass  
{  
   [Serializable]  
   public class MsgClass  
   {  
      public MsgClass()  
      {  
         StrField = "OK";  
         IntField = 1;  
         ShortField = 1;  
      }  
  
      [PropertyNamespace.ShortPropertyName]  
      public Int16 ShortField;  
  
      [PropertyAttribute(typeof(PropertyNamespace.StringPropertyName)]  
      [DistinguishedFieldAttribute()]  
      public String StrField;  
  
      [DistinguishedFieldAttribute()]  
      public int IntField;  
   }  
}  
```  
  
 在上述示例中，ShortField 是 PropertyNamespace.ShortPropertyName 类型的属性和属性的基础类型必须为 Int16 是 ShortField 类型。 StrField 是可分辨的字段和是 PropertyNamespace.StringPropertyName 类型的属性和属性的基础类型必须为 string 是 StrField 类型的类型。 通常 PropertyNamespace.StringPropertyName 和 propertynamespace.shortpropertyname 都将创建 BizTalk 架构编辑器通过为架构属性，并且需要引用的程序集，其中包含的架构属性在你C#项目。  
  
> [!NOTE]
>  在C#编程语言，属性名称的 Attribute 结尾是可选的因此可以省略 Attribute 结尾并改为使用 DistinguishedField 或 Property。 例如，  
  
```  
[Property(typeof(PropertyNamespace.StringPropertyName))]  
[DistinguishedField]  
public string StrField;  
```  
  
 定义消息类型后，它是非常方便地编写代码将创建此类型的新消息的业务流程中。 内**构造消息**形状，可编写简单表达式来创建新的消息**MsgClass**键入上面所示，然后将值分配给经过属性化，Distinguished 的字段字段 （如果你想要覆盖默认值）。 注意，MyMsg 为业务流程消息变量，其类型为 NetClass.MsgClass。  
  
```  
MyMsg = new NetClass.MsgClass();  
MyMsg.StrField = "Changed Value";  
MyMsg.IntField = 15;  
```  
  
## <a name="see-also"></a>请参阅  
 [表示为 XSD 架构的消息](../core/messages-represented-as-xsd-schemas.md)   
 [表示为 XLANGMessage 的消息](../core/messages-represented-as-xlangmessage.md)   
 [在用户代码中构造消息](../core/constructing-messages-in-user-code.md)