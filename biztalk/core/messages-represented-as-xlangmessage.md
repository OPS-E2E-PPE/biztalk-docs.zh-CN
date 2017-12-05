---
title: "消息表示为 XLANGMessage |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aadca870-2f93-4be3-8733-a0cd3815add7
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 345c0bbc2eae3289976738d25e76a8a377f86ea7
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2017
---
# <a name="messages-represented-as-xlangmessage"></a>表示为 XLANGMessage 的消息
**XLANGMessage**对象表示的声明与 XLANG 服务的消息实例。 通过在方法调用中将对某一消息的引用作为参数传递，获取此对象。 **XLANGPart**对象表示 XLANG 服务内的消息实例中包含的消息部分。 此对象获取通过其中接收的参数类型在方法调用中传递一部分引用**XLANGPart**或通过枚举在传递的引用上**XLANGMessage**。  
  
 可以传递给某个用户组件的业务流程消息变量，并将其作为接收**XLANGMessage**对象。 **XLANGMessage**对象允许访问部件和访问消息属性。用户可能"保存" **XLANGMessage** ，因此可将其生存期内超出声明的范围。 随后， **XLANGMessage**可以从方法返回并分配给业务流程中的消息变量。  
  
## <a name="constructing-an-xlangmessage"></a>构造 XLANGMessage  
 在构造时**XLANGMessage**与流、 流类型必须实现**IStreamFactory**也是**MemoryStream**。 下面的代码示例显示如何构造**XLANGMessage**:  
  
```  
public class FileStreamFactory : IStreamFactory  
{  
    string _fname;  
  
    public FileStreamFactory(string fname)  
    {  
        _fname = fname;  
    }  
  
    public Stream CreateStream()  
    {  
        return new FileStream  
        (  
            _fname,  
            FileMode.Open,  
            FileAccess.Read,  
            FileShare.Read  
        );  
    }  
}  
  
public static void AssignStreamFactoryToPart(XLANGMessage msg)  
{  
    IStreamFactory sf = new FileStreamFactory( @”c:\data.xml” );  
    msg[0].LoadFrom( sf );  
}  
```  
  
 可能有时候，您想要创建新的消息而不转换源消息。 你可以执行此操作通过使用类型的变量的**System.Xml.XmlDocument**和加载或否则构造合适的内容。 在下面的示例中，加载 XML 从字符串使用**LoadXml**方法**XmlDocument**:  
  
```  
XmlVariable.LoadXml("<ns0:Root PONumber="047745351122111" xmlns:ns0="http://BTSHTTPSend.SimpleSchema"><MyChildRecord SubAttr1="Simple Attribute " /></ns0:Root>");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
 下面的示例通过使用从文件加载 XML**负载**方法**XmlDocument**:  
  
```  
XmlVariable.Load("C:\MyData.xml");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
> [!NOTE]
>  如果你想要构造更大的消息，使用上一节中所示的流式处理方法之一，或请考虑使用**转换**中业务流程设计器形状。  
  
## <a name="considerations-when-using-xlangmessage-and-xlangpart"></a>使用 XLANGMessage 和 XLANGPart 时的注意事项  
 使用时**XLANGMessage**和**XLANGPart**在用户代码中，请考虑以下：  
  
-   不要将传递作为消息部分**XLANGPart**自变量或返回类型的值**XLANGPart**。 应传递**XLANGPart**作为部件的类型。 例如：  
  
    ```  
    Message String msg;  
    Class.Test(msg);  
    // or you can do the following  
    Messagetype mt  
    {  
         String part;  
    };  
    Message mt msg;  
    Class.Test(msg,part);  
  
    ```  
  
     你还可以传递消息本身作为**XLANGMessage**并用**XLANGMessage**下标运算符来访问的函数调用中的部分。 但是，不应置于**XLANGPart**其生存期超出函数调用的生存期集合中。 相反，你应该将置于**XLANGMessage**集合中。 例如：  
  
    ```  
    Void Test(XLANGMessage xlm)  
    {  
         try  
         {  
          XLANGPart xlp = xlm[0];  
          String sval = (String) xlp.RetrieveAs(typeof(string));  
         }  
         finally  
         {  
          Xlm.Dispose();  
         }  
    }  
    ```  
  
-   未定义为一个业务流程参数**XLANGMessage**或**XLANGPart**。 如果您想要传递某一消息，则使用某一消息类型参数来传递该消息。 如果您想要传递某一部分，则改为传递该消息，然后使用该部分。 如果您只是想要部分值，则使用部分类型传递该部分。  
  
-   不返回**XLANGMessage**方法调用的参数。 如果返回**XLANGMessage**传入的参数，然后你不能调用**释放**方法对方法调用中的参数，它直观地违反了生存期假设和它还引发异常。 传递通过一条消息时**XLANGMessage**对于用户代码的参数，你将引用到的特殊的上下文，通常没有与其引用的消息的消息。 此上下文的生存期就是业务流程实例的生存期。 其原因在于，BizTalk Server 不知道用户代码是否将占有消息。  
  
     在业务流程实例退出时，在该实例中创建的任何消息都不再有效，因此，此类集合的生存期应短于或等于实例的生存期。 但是，如果你想要将消息已传递时释放在循环中的消息引用**XLANGMessage**具有作为业务流程实例相同的生存期，则可以调用的自变量**XLANGMessage.Dispose**以释放该引用。 此外，如果在用户代码方法中， **XLANGMessage**仅本地使用参数和参数的生存期包含在于函数调用中，你还可以调用**XLANGMessage.Dispose**来释放对根上下文的引用并重新授予相应的消息，则会正常生存期行为。 例如：  
  
    ```  
    void Test(XLANGMessage xlm)  
    {  
         try  
         {  
          //XLANGMessage is only used locally  
         }  
         finally  
         {  
          xlm.Dispose();  
         }  
    }  
    ```  
  
     如果你将 xlm 放在一个集合，则此类本身必须具有**释放**进行清理的方法。 例如：  
  
    ```  
    Public class A  
    {  
         Hashtable h = new Hashtable();  
         Public Test(XLANGMessage xlm)  
         {  
          h[xlm] = 1;  
         }  
         //You can have more methods here  
         Public Dispose()  
         {  
          foreach (XLANGMessage xlm in h.Keys)  
           Xlm.Dispose();  
         }  
    }  
    ```  
  
     你应该调用**A.Dispose**完成之后使用的集合**XLANGMessages**。  
  
## <a name="see-also"></a>另请参阅  
 [表示为 XSD 架构的消息](../core/messages-represented-as-xsd-schemas.md)   
 [.NET 类表示的消息](../core/messages-represented-as-net-classes.md)   
 [在用户代码中构造消息](../core/constructing-messages-in-user-code.md)