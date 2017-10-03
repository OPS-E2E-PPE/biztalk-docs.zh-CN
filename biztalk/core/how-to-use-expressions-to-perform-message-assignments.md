---
title: "如何使用表达式来执行消息分配 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- messages, distinquished fields
- orchestrations, expressions
- messages, manipulating
- messages, assigning messages
- messages, expressions
- messages, message parts
- orchestrations, messages
- messages, components
ms.assetid: 9989caf5-012c-4fc4-b5d8-981ca9a69f43
caps.latest.revision: "19"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8f423e1b797cfff95bae1d9b1dd862d28210cd26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-expressions-to-perform-message-assignments"></a>如何使用表达式来执行消息分配
可以在业务流程中使用表达式来以各种方式对消息进行操作。  
  
## <a name="referring-to-message-fields"></a>引用消息字段  
 也可以通过将字段名称，如下所示追加到消息名称引用到一条消息中的可分辨字段：  
  
```  
MyMsg.Amount  
```  
  
 在此示例中，MyMsg 是消息，Amount 是已标识为 MyMsg 所基于的消息类型的可分辨字段的字段。  
  
## <a name="assigning-to-messages-and-message-parts"></a>将分配给消息和消息部分  
 你可以直接向另一条消息或到消息部分的消息部分指定一条消息：  
  
```  
MyMsg=IncomingMsg;  
MyMsg.Invoice=IncomingMsg.Invoice;  
```  
  
 在此示例中，Invoice 是基于架构的消息部分。  
  
 如果你想要修改已构造一条消息的属性 — 例如收到一条消息 — 你必须通过将第一个分配到一个构造消息形状上，在第二个构造一条新消息和修改的属性中的新消息相同的构造消息形状。  
  
> [!NOTE]
>  不能引用或分配给诸如 MyMsg.Invoice.MyField 之类的消息字段，除非已升级这些字段。只能引用或分配给整个消息、消息部分、升级的消息属性或可分辨字段。  
  
## <a name="adding-message-parts"></a>添加消息部分  
 你可以附加将部件添加到现有的多部分消息使用**XLANGs.BaseTypes.XLANGMessage.AddPart**方法。 为此，请执行以下操作：  
  
-   创建 C# 项目并添加对引用**Microsoft.XLANGs.BaseTypes**。  
  
-   实现类似于以下的公共类：  
  
    ```  
    public class MyAddPartHelper  
    {  
         public static void AddPart(XLANGMessage msg, object part, String partName)  
         {  
              msg.AddPart(part, partName);  
         }  
    }  
    ```  
  
     有三个重载的方法**Microsoft.XLANGs.BaseTypes.AddPart**:  
  
    ```  
    public void AddPart(object part, String partName);  
    public void AddPart(XLANGPart part);  
    public void AddPart(XLANGPart part, String partName);  
    ```  
  
-   在 BizTalk 项目中，添加对公共类并调用的引用**AddPart**方法从**表达式**调整您的业务流程中，如下所示：  
  
    ```  
    MyAddPartHelper.AddPart(myMessage, myStringObject, “StringObject1”);  
    ```  
  
> [!NOTE]
>  不能将非序列化对象或自定义的格式化对象作为消息部分添加。 必须添加使用的其他部分之前初始化所有静态部分**AddPart**方法。 仅可在某个消息的消息构造语句中将任意部分添加到此消息中。 不支持在消息构造语句之外添加其他部分。  
  
## <a name="retrieving-message-parts"></a>检索消息部分  
 可以通过使用从现有的多部分消息中检索消息部分**RetrieveAs**方法从**Microsoft.XLANGs.BaseTypes**。 为此，请执行以下操作：  
  
-   创建 C# 项目并添加对引用**Microsoft.XLANGs.BaseTypes**。  
  
-   实现类似于以下的公共类：  
  
    ```  
    Public class MyAddPartHelper  
    {  
         public static Object GetPart(XLANGMessage msg, string sName, Type t)  
         {  
              XLANGPart p =  msg[sName];  
              return p.RetrieveAs(t);  
         }  
         public static Object GetPart(XLANGMessage msg, int partIndex, Type t)  
         {  
               XLANGPart p = msg[partIndex];  
               return p.RetrieveAs(t);  
          }  
    }  
    ```  
  
    > [!NOTE]
    >  **RetrieveAs**方法按名称、 索引支持检索消息部分。  
  
-   在 BizTalk 项目中，添加对公共类并调用的引用**GetPart**方法从**表达式**调整您的业务流程中，如下所示：  
  
    ```  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, "StringObject1" , typeof(System.String));  
    //sPart is a type of System.String  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, 1, typeof(System.String));  
    //Retriving the message part with index = 1  
    ```  
  
## <a name="message-part-context-property-access"></a>消息部分上下文属性访问  
 消息部分具有与消息上下文分开的上下文。 设置时，可以构造消息通过架构编辑器的一部分上下文属性**属性架构基**到关联的元素的属性**PartContextPropertyBase。**  
  
 访问是类似于消息属性，通过等表达式：  
  
```  
Msg.PartName(myPartContextProperty)  
```  
  
 例如：  
  
```  
Str=Msg.PartName(myPartContextProperty); //assumes myPartContextProperty is of type string  
```  
  
## <a name="xlangmessage-context-property-access"></a>XLANGMessage 上下文属性访问  
 如果你想要访问消息属性从**XLANGMessage**接口从代码中，可以将消息传递的类型参数**Microsoft.XLANGs.BaseTypes.XLANGMessage**到方法从表达式形状，然后使用**Microsoft.XLANGs.BaseTypes.XLANGMessage**方法**SetPropertyValue**和**GetPropertyValue**以实现此。 为此，请执行以下操作：  
  
-   创建 C# 项目并添加对引用**Microsoft.XLANGs.BaseTypes**和**Microsoft.BizTalk.GlobalPropertySchemas**。  
  
-   访问使用类似于代码的上下文属性下面：  
  
    ```  
    MyMsg.GetPropertyValue(typeof(BTS.MessageID));  
    MyMsg.SetPropertyValue(typeof(MIME.IsMultipartRelated), true);  
    ```  
  
> [!NOTE]
>  如果您希望获得或设置自己的自定义上下文属性，则需要在 C# 项目中添加对于属性架构项目的引用或添加对于包含属性架构的程序集的引用。  
  
## <a name="assigning-to-message-properties"></a>将分配给消息属性  
 你可以将值分配给消息属性：  
  
```  
MyMessage(MySchemaNamespace.MyProperty)=True;  
```  
  
 在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，可以引用多部分消息的 MIME 属性，并对该属性进行赋值：  
  
```  
Message_Out.MessagePart_1(MIME.FileName)="document.doc";  
```  
  
> [!NOTE]
>  BizTalk 消息由消息上下文和消息部分组成。 首先必须初始化消息部分，然后才能获取或设置任何消息上下文属性；否则，您将在 XLANG 编译时期间收到错误。  
  
## <a name="see-also"></a>另请参阅  
 [在业务流程中使用消息](../core/using-messages-in-orchestrations.md)   
 [构造在用户代码中的消息](../core/constructing-messages-in-user-code.md)   