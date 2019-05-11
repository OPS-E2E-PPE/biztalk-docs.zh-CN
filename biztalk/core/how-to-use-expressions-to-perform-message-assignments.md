---
title: 如何使用表达式来执行消息分配 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: acadf37a102cedb9ddc902b4ca854d5e8458fa7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333447"
---
# <a name="how-to-use-expressions-to-perform-message-assignments"></a>如何使用表达式来执行消息分配
表达式可用于在业务流程中处理以各种方式的消息。  
  
## <a name="referring-to-message-fields"></a>消息字段引用  
 可以按如下所示将字段名称附加到消息名称引用的一条消息中的可分辨字段：  
  
```  
MyMsg.Amount  
```  
  
 在此示例中，MyMsg 是消息，并量是已标识为消息类型的可分辨字段，MyMsg 所基于的字段。  
  
## <a name="assigning-to-messages-and-message-parts"></a>将分配给消息和消息部分  
 您可以直接向另一条消息或消息部分的消息部分分配一条消息：  
  
```  
MyMsg=IncomingMsg;  
MyMsg.Invoice=IncomingMsg.Invoice;  
```  
  
 在此示例中，Invoice 是基于架构的消息部分。  
  
 如果你想要修改已构造的消息的属性，例如已收到的消息，必须通过将第一个分配到第二个构造消息形状中构造新消息并修改的属性中的新消息在同一构造消息形状。  
  
> [!NOTE]
>  不能引用或分配给消息字段，诸如 mymsg.invoice.myfield 之类，除非已升级这些;你只可以引用或分配给整个消息、 消息部分、 升级的消息属性或可分辨的字段。  
  
## <a name="adding-message-parts"></a>添加消息部分  
 可以通过使用现有的多部分消息中添加其他部分**XLANGs.BaseTypes.XLANGMessage.AddPart**方法。 为此，请执行以下操作：  
  
-   创建C#项目，并添加对的引用**Microsoft.XLANGs.BaseTypes**。  
  
-   实现类似于下面的公共类：  
  
    ```  
    public class MyAddPartHelper  
    {  
         public static void AddPart(XLANGMessage msg, object part, String partName)  
         {  
              msg.AddPart(part, partName);  
         }  
    }  
    ```  
  
     有三个重载的方法**microsoft.xlangs.basetypes.addpart 具有**:  
  
    ```  
    public void AddPart(object part, String partName);  
    public void AddPart(XLANGPart part);  
    public void AddPart(XLANGPart part, String partName);  
    ```  
  
-   在 BizTalk 项目中，添加对公共类和调用的引用**AddPart**方法从**表达式**形状在业务流程中，如下所示：  
  
    ```  
    MyAddPartHelper.AddPart(myMessage, myStringObject, “StringObject1”);  
    ```  
  
> [!NOTE]
>  不能用作消息部分添加非可序列化对象或自定义格式化的对象。 添加使用的其他部分之前，必须初始化所有静态部分**AddPart**方法。 您可以添加任意部分仅在其消息内消息构造语句。 不支持添加消息之外的其他部分构造语句。  
  
## <a name="retrieving-message-parts"></a>检索消息部分  
 可以通过使用从现有的多部分消息中检索消息部分**RetrieveAs**方法从**Microsoft.XLANGs.BaseTypes**。 为此，请执行以下操作：  
  
-   创建C#项目，并添加对的引用**Microsoft.XLANGs.BaseTypes**。  
  
-   实现类似于下面的公共类：  
  
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
    >  **RetrieveAs**方法支持检索消息部分，按名称和索引。  
  
-   在 BizTalk 项目中，添加对公共类和调用的引用**GetPart**方法从**表达式**形状在业务流程中，如下所示：  
  
    ```  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, "StringObject1" , typeof(System.String));  
    //sPart is a type of System.String  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, 1, typeof(System.String));  
    //Retriving the message part with index = 1  
    ```  
  
## <a name="message-part-context-property-access"></a>消息部分上下文属性访问  
 消息部分都有独立于消息上下文的上下文。 在设置时，可以构造消息部分上下文属性通过架构编辑器**Property Schema Base**到关联的元素属性的**PartContextPropertyBase。**  
  
 访问是类似于消息属性，通过之类的表达式：  
  
```  
Msg.PartName(myPartContextProperty)  
```  
  
 例如：  
  
```  
Str=Msg.PartName(myPartContextProperty); //assumes myPartContextProperty is of type string  
```  
  
## <a name="xlangmessage-context-property-access"></a>XLANGMessage 上下文属性访问  
 如果你想要访问消息属性**XLANGMessage**接口从你的代码，可以将消息传递类型的参数**Microsoft.XLANGs.BaseTypes.XLANGMessage**方法从表达式形状，然后使用**Microsoft.XLANGs.BaseTypes.XLANGMessage**方法**SetPropertyValue**并**GetPropertyValue**实现此。 为此，请执行以下操作：  
  
-   创建C#项目，并添加对的引用**Microsoft.XLANGs.BaseTypes**并**Microsoft.BizTalk.GlobalPropertySchemas**。  
  
-   访问使用类似于代码的上下文属性如下：  
  
    ```  
    MyMsg.GetPropertyValue(typeof(BTS.MessageID));  
    MyMsg.SetPropertyValue(typeof(MIME.IsMultipartRelated), true);  
    ```  
  
> [!NOTE]
>  如果你想要获取或设置您自己的自定义上下文属性，则需要添加到属性架构项目的引用或添加对程序集的引用包含中的属性架构在C#项目。  
  
## <a name="assigning-to-message-properties"></a>将分配给消息属性  
 可以将值分配到的消息属性：  
  
```  
MyMessage(MySchemaNamespace.MyProperty)=True;  
```  
  
 在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以引用并将值分配给多部分消息的 MIME 属性：  
  
```  
Message_Out.MessagePart_1(MIME.FileName)="document.doc";  
```  
  
> [!NOTE]
>  BizTalk 消息由消息上下文和消息部分组成。 可以获取或设置任何消息上下文属性; 之前，必须先初始化消息部分否则，将在 XLANG 编译时期间收到错误。  
  
## <a name="see-also"></a>请参阅  
 [业务流程中使用的消息](../core/using-messages-in-orchestrations.md)   
 [在用户代码中构造消息](../core/constructing-messages-in-user-code.md)   