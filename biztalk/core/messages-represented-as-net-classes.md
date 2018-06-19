---
title: .NET 类表示消息 |Microsoft 文档
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
ms.openlocfilehash: 16f0ea95f02de6e9fda411fa0183569dc0779033
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22263389"
---
# <a name="messages-represented-as-net-classes"></a><span data-ttu-id="64acf-102">表示为 .NET 类的消息</span><span class="sxs-lookup"><span data-stu-id="64acf-102">Messages Represented as .NET Classes</span></span>
<span data-ttu-id="64acf-103">此方法首先需要创建一个定义消息类型的 .NET 类。</span><span class="sxs-lookup"><span data-stu-id="64acf-103">This approach first involves creating a .NET class that defines your message type.</span></span> <span data-ttu-id="64acf-104">该类必须具有默认构造函数，否则，使用它的业务流程将无法编译。</span><span class="sxs-lookup"><span data-stu-id="64acf-104">The class must have a default constructor or the orchestration using it will not compile.</span></span> <span data-ttu-id="64acf-105">下面是这个类的简单示例。</span><span class="sxs-lookup"><span data-stu-id="64acf-105">A simple example of such a class is shown here.</span></span>  
  
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
  
 <span data-ttu-id="64acf-106">在上面的示例中，ShortField 是 PropertyNamespace.ShortPropertyName 类型的属性，该属性的基础类型必须为 Int16，Int16 是 ShortField 类型。</span><span class="sxs-lookup"><span data-stu-id="64acf-106">In the above example, ShortField would be a property of type PropertyNamespace.ShortPropertyName and the underlying type of the property would have to be Int16 which is the type of ShortField.</span></span> <span data-ttu-id="64acf-107">StrField 既是可分辨字段，又是 PropertyNamespace.StringPropertyName 类型的属性，该属性的基础类型必须为 String 类型，String 是 StrField 类型。</span><span class="sxs-lookup"><span data-stu-id="64acf-107">StrField would be both a distinguished field and a property of type PropertyNamespace.StringPropertyName and the underlying type of the property would have to be type of String which is the type of StrField.</span></span> <span data-ttu-id="64acf-108">通常，PropertyNamespace.StringPropertyName 和 PropertyNamespace.ShortPropertyName 都是通过 BizTalk 架构编辑器作为架构属性创建的，并且您需要引用在 C# 项目中包含架构属性的程序集。</span><span class="sxs-lookup"><span data-stu-id="64acf-108">Normally both PropertyNamespace.StringPropertyName and PropertyNamespace.ShortPropertyName would be created through the BizTalk Schema Editor as schema properties, and you need to reference the assembly which contains the schema properties in your C# project.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="64acf-109">在 C# 编程语言中，属性名的 Attribute 结尾是可选的，因此您可以省略 Attribute 结尾，使用 DistinguishedField 或 Property。</span><span class="sxs-lookup"><span data-stu-id="64acf-109">In C# programming language, the Attribute ending of an attribute name is optional, so you can omit the Attribute ending and use DistinguishedField or Property instead.</span></span> <span data-ttu-id="64acf-110">例如：</span><span class="sxs-lookup"><span data-stu-id="64acf-110">For example,</span></span>  
  
```  
[Property(typeof(PropertyNamespace.StringPropertyName))]  
[DistinguishedField]  
public string StrField;  
```  
  
 <span data-ttu-id="64acf-111">定义消息类型后，可以很容易地在业务流程中编写代码，以创建此类型的新消息。</span><span class="sxs-lookup"><span data-stu-id="64acf-111">Once the message type is defined, it is very easy to write code in the orchestration that will create a new message of this type.</span></span> <span data-ttu-id="64acf-112">在**构造消息**形状，编写简单的表达式创建的新消息**MsgClass**键入，以上所示，然后将值分配给字段的特性化为 Distinguished字段 （如果你想要覆盖默认值）。</span><span class="sxs-lookup"><span data-stu-id="64acf-112">Within a **Construct Message** shape, you write simple expressions to create a new message of the **MsgClass** type shown above, and then assign values to the fields which are attributed as Distinguished Fields (if you wish to override the default values).</span></span> <span data-ttu-id="64acf-113">注意，MyMsg 为业务流程消息变量，其类型为 NetClass.MsgClass。</span><span class="sxs-lookup"><span data-stu-id="64acf-113">Note that MyMsg is an orchestration message variable whose type is NetClass.MsgClass.</span></span>  
  
```  
MyMsg = new NetClass.MsgClass();  
MyMsg.StrField = "Changed Value";  
MyMsg.IntField = 15;  
```  
  
## <a name="see-also"></a><span data-ttu-id="64acf-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="64acf-114">See Also</span></span>  
 <span data-ttu-id="64acf-115">[表示为 XSD 架构的消息](../core/messages-represented-as-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="64acf-115">[Messages Represented as XSD Schemas](../core/messages-represented-as-xsd-schemas.md) </span></span>  
 <span data-ttu-id="64acf-116">[表示为 XLANGMessage 的消息](../core/messages-represented-as-xlangmessage.md) </span><span class="sxs-lookup"><span data-stu-id="64acf-116">[Messages Represented as XLANGMessage](../core/messages-represented-as-xlangmessage.md) </span></span>  
 [<span data-ttu-id="64acf-117">构造在用户代码中的消息</span><span class="sxs-lookup"><span data-stu-id="64acf-117">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)