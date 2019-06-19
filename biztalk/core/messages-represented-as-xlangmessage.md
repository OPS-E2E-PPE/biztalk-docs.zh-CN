---
title: 表示为 XLANGMessage 的消息 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: aadca870-2f93-4be3-8733-a0cd3815add7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bad45a2bfae38cd38a50ae513f6c2fb336dce42d
ms.sourcegitcommit: bab8f4abca27edc45f9f4601ada6f3fc6a2b87cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2019
ms.locfileid: "67189097"
---
# <a name="messages-represented-as-xlangmessage"></a>表示为 XLANGMessage 的消息
**XLANGMessage**对象都表示用 XLANG 服务声明的消息实例。 通过将一条消息的引用作为方法调用中的参数传递，获取此对象。 **XLANGPart**对象表示在 XLANG 服务的消息实例中包含的消息部分。 获取此对象通过其中接收的参数类型在方法调用中传递部分引用**XLANGPart**或通过在传递的引用上枚举**XLANGMessage**。  
  
 业务流程消息变量可能会传递给某个用户组件和作为接收**XLANGMessage**对象。 **XLANGMessage**对象允许访问部件和访问消息属性。用户可能会"占有"到**XLANGMessage** ，从而扩展其生存期超过声明的范围。 随后， **XLANGMessage**可能从方法返回并分配给在业务流程中的消息变量。  
  
## <a name="constructing-an-xlangmessage"></a>构造 XLANGMessage  
 构造时**XLANGMessage**与流、 流类型必须实现**IStreamFactory**也是**MemoryStream**。 下面的代码示例显示如何构造**XLANGMessage**:  
  
```csharp
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
  
 可能存在你想要创建新的消息而不转换源消息。 您可以执行此操作使用的类型的变量**System.Xml.XmlDocument**并加载或构造适当的内容。 在以下示例中，加载 XML 字符串中使用**LoadXml**方法**XmlDocument**:  
  
```csharp
XmlVariable.LoadXml("<ns0:Root PONumber="047745351122111" xmlns:ns0="http://BTSHTTPSend.SimpleSchema"><MyChildRecord SubAttr1="Simple Attribute " /></ns0:Root>");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
 下面的示例通过从文件加载 XML**负载**方法**XmlDocument**:  
  
```csharp
XmlVariable.Load("C:\MyData.xml");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
> [!NOTE]
>  如果你想要构造更大的消息，使用在上一部分中阐释的流方法之一，或考虑使用**转换**形状在业务流程设计器中的。  
  
## <a name="considerations-when-using-xlangmessage-and-xlangpart"></a>使用 XLANGMessage 和 XLANGPart 时的注意事项  
 使用时**XLANGMessage**并**XLANGPart**在用户代码中，请考虑以下：  
  
-   不将消息部分作为**XLANGPart**自变量或返回类型的值**XLANGPart**。 应传递**XLANGPart**作为部件的类型。 例如：  
  
    ```csharp
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
  
     你还可以传递消息本身作为**XLANGMessage**并用**XLANGMessage**下标运算符来访问函数调用中的部分。 但是，不应放**XLANGPart**其生命周期持续时间的函数调用的生存期集合中。 相反，应将放**XLANGMessage**集合中。 例如：  
  
    ```csharp
    void Test(XLANGMessage xlm)
    {
         try
         {
             XLANGPart xlp = xlm[0];
             string sval = (string)xlp.RetrieveAs(typeof(string));
         }
         finally
         {
             xlm.Dispose();
         }
    }
    ```  
  
-   未定义为将业务流程参数**XLANGMessage**或**XLANGPart**。 如果你想要将传递一条消息，然后使用消息类型参数来传递该消息。 如果你想要传递某一部分，然后改为传入消息，然后使用该部件。 如果只想部分值，然后使用部分类型传递该部分。  
  
-   不会返回**XLANGMessage**方法调用的参数。 如果返回**XLANGMessage**参数传入，并且您不能调用**Dispose**方法内对该参数在方法调用，它显然违反生存期假设并且还引发异常。 当将通过消息传递**XLANGMessage**到用户代码的参数，则引用通常没有向其引用的消息的特殊上下文的消息。 此上下文的生存期就是业务流程实例的生存期。 这是因为 BizTalk Server 不知道用户代码将占有消息。  
  
     业务流程实例退出时，该实例中创建的任何消息将不再有效，因此，此类集合的生存期应小于或等于该实例的生存期。 但是，如果你想要通过传递消息时释放循环中的消息引用**XLANGMessage**具有相同的生存期与业务流程实例，则可以调用的参数**XLANGMessage.Dispose**以释放该引用。 此外，在用户代码方法中，如果**XLANGMessage**参数仅在本地使用，并且，函数调用中，您还可以调用包含参数的生存期**XLANGMessage.Dispose**释放对根上下文的引用，并为相应的消息返回提供通常的生存期。 例如：  
  
    ```csharp
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
  
     如果您将 xlm 放置在一个集合，则类本身必须具有**Dispose**清理方法。 例如：  
  
    ```csharp
    public class A
    {
         Hashtable h = new Hashtable();
         public void Test(XLANGMessage xlm)
         {
             h[xlm] = 1;
         }
         //You can have more methods here
         public void Dispose()
         {
             foreach (XLANGMessage xlm in h.Keys)
             {
                 xlm.Dispose();
             }
         }
    }
    ```  
  
     将调用**应该**完成后使用的集合**XLANGMessages**。  
  
## <a name="see-also"></a>请参阅  
 [表示为 XSD 架构的消息](../core/messages-represented-as-xsd-schemas.md)   
 [表示为.NET 类的消息](../core/messages-represented-as-net-classes.md)   
 [在用户代码中构造消息](../core/constructing-messages-in-user-code.md)
