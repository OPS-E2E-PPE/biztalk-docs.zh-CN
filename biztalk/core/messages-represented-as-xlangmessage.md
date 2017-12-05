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
# <a name="messages-represented-as-xlangmessage"></a><span data-ttu-id="a2c58-102">表示为 XLANGMessage 的消息</span><span class="sxs-lookup"><span data-stu-id="a2c58-102">Messages Represented as XLANGMessage</span></span>
<span data-ttu-id="a2c58-103">**XLANGMessage**对象表示的声明与 XLANG 服务的消息实例。</span><span class="sxs-lookup"><span data-stu-id="a2c58-103">An **XLANGMessage** object represents a message instance declared with an XLANG service.</span></span> <span data-ttu-id="a2c58-104">通过在方法调用中将对某一消息的引用作为参数传递，获取此对象。</span><span class="sxs-lookup"><span data-stu-id="a2c58-104">This object is obtained by passing a reference to a message as a parameter in a method invocation.</span></span> <span data-ttu-id="a2c58-105">**XLANGPart**对象表示 XLANG 服务内的消息实例中包含的消息部分。</span><span class="sxs-lookup"><span data-stu-id="a2c58-105">An **XLANGPart** object represents a message part contained in a message instance within an XLANG service.</span></span> <span data-ttu-id="a2c58-106">此对象获取通过其中接收的参数类型在方法调用中传递一部分引用**XLANGPart**或通过枚举在传递的引用上**XLANGMessage**。</span><span class="sxs-lookup"><span data-stu-id="a2c58-106">This object is obtained either by passing a part reference in a method invocation where the receiving parameter type is **XLANGPart** or by enumerating on a passed reference of **XLANGMessage**.</span></span>  
  
 <span data-ttu-id="a2c58-107">可以传递给某个用户组件的业务流程消息变量，并将其作为接收**XLANGMessage**对象。</span><span class="sxs-lookup"><span data-stu-id="a2c58-107">An orchestration message variable may be passed to a user component and received as an **XLANGMessage** object.</span></span> <span data-ttu-id="a2c58-108">**XLANGMessage**对象允许访问部件和访问消息属性。用户可能"保存" **XLANGMessage** ，因此可将其生存期内超出声明的范围。</span><span class="sxs-lookup"><span data-stu-id="a2c58-108">The **XLANGMessage** object allows accessing the parts and accessing message properties.The user may "hold on" to an **XLANGMessage** and thereby extend its lifetime beyond the declared scope.</span></span> <span data-ttu-id="a2c58-109">随后， **XLANGMessage**可以从方法返回并分配给业务流程中的消息变量。</span><span class="sxs-lookup"><span data-stu-id="a2c58-109">Subsequently, an **XLANGMessage** may be retuned from a method and assigned to a message variable in an orchestration.</span></span>  
  
## <a name="constructing-an-xlangmessage"></a><span data-ttu-id="a2c58-110">构造 XLANGMessage</span><span class="sxs-lookup"><span data-stu-id="a2c58-110">Constructing an XLANGMessage</span></span>  
 <span data-ttu-id="a2c58-111">在构造时**XLANGMessage**与流、 流类型必须实现**IStreamFactory**也是**MemoryStream**。</span><span class="sxs-lookup"><span data-stu-id="a2c58-111">When constructing an **XLANGMessage** with a stream, the stream type must either implement **IStreamFactory** or be a **MemoryStream**.</span></span> <span data-ttu-id="a2c58-112">下面的代码示例显示如何构造**XLANGMessage**:</span><span class="sxs-lookup"><span data-stu-id="a2c58-112">The following code sample shows how to construct an **XLANGMessage**:</span></span>  
  
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
  
 <span data-ttu-id="a2c58-113">可能有时候，您想要创建新的消息而不转换源消息。</span><span class="sxs-lookup"><span data-stu-id="a2c58-113">There may be times when you want to create a new message without transforming a source message.</span></span> <span data-ttu-id="a2c58-114">你可以执行此操作通过使用类型的变量的**System.Xml.XmlDocument**和加载或否则构造合适的内容。</span><span class="sxs-lookup"><span data-stu-id="a2c58-114">You can do this by using a variable of type **System.Xml.XmlDocument** and loading or otherwise constructing appropriate content.</span></span> <span data-ttu-id="a2c58-115">在下面的示例中，加载 XML 从字符串使用**LoadXml**方法**XmlDocument**:</span><span class="sxs-lookup"><span data-stu-id="a2c58-115">In the following example, XML is loaded from a string by using the **LoadXml** method of **XmlDocument**:</span></span>  
  
```  
XmlVariable.LoadXml("<ns0:Root PONumber="047745351122111" xmlns:ns0="http://BTSHTTPSend.SimpleSchema"><MyChildRecord SubAttr1="Simple Attribute " /></ns0:Root>");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
 <span data-ttu-id="a2c58-116">下面的示例通过使用从文件加载 XML**负载**方法**XmlDocument**:</span><span class="sxs-lookup"><span data-stu-id="a2c58-116">The following example loads XML from a file by using the **Load** method of **XmlDocument**:</span></span>  
  
```  
XmlVariable.Load("C:\MyData.xml");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="a2c58-117">如果你想要构造更大的消息，使用上一节中所示的流式处理方法之一，或请考虑使用**转换**中业务流程设计器形状。</span><span class="sxs-lookup"><span data-stu-id="a2c58-117">If you want to construct larger messages, use one of the streaming methods demonstrated in the previous section or consider using the **Transform** shape in Orchestration Designer.</span></span>  
  
## <a name="considerations-when-using-xlangmessage-and-xlangpart"></a><span data-ttu-id="a2c58-118">使用 XLANGMessage 和 XLANGPart 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="a2c58-118">Considerations When Using XLANGMessage and XLANGPart</span></span>  
 <span data-ttu-id="a2c58-119">使用时**XLANGMessage**和**XLANGPart**在用户代码中，请考虑以下：</span><span class="sxs-lookup"><span data-stu-id="a2c58-119">When using **XLANGMessage** and **XLANGPart** in user code, consider the following:</span></span>  
  
-   <span data-ttu-id="a2c58-120">不要将传递作为消息部分**XLANGPart**自变量或返回类型的值**XLANGPart**。</span><span class="sxs-lookup"><span data-stu-id="a2c58-120">Do not pass a message part as an **XLANGPart** argument or return a value of type **XLANGPart**.</span></span> <span data-ttu-id="a2c58-121">应传递**XLANGPart**作为部件的类型。</span><span class="sxs-lookup"><span data-stu-id="a2c58-121">You should pass **XLANGPart** as the type of the part.</span></span> <span data-ttu-id="a2c58-122">例如：</span><span class="sxs-lookup"><span data-stu-id="a2c58-122">For example:</span></span>  
  
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
  
     <span data-ttu-id="a2c58-123">你还可以传递消息本身作为**XLANGMessage**并用**XLANGMessage**下标运算符来访问的函数调用中的部分。</span><span class="sxs-lookup"><span data-stu-id="a2c58-123">You can also pass the message itself as an **XLANGMessage** and use the **XLANGMessage** subscript operators to access the part inside the function call.</span></span> <span data-ttu-id="a2c58-124">但是，不应置于**XLANGPart**其生存期超出函数调用的生存期集合中。</span><span class="sxs-lookup"><span data-stu-id="a2c58-124">However, you should not put an **XLANGPart** in a collection whose lifetime extends past the lifetime of the function call.</span></span> <span data-ttu-id="a2c58-125">相反，你应该将置于**XLANGMessage**集合中。</span><span class="sxs-lookup"><span data-stu-id="a2c58-125">Instead, you should put the **XLANGMessage** in the collection.</span></span> <span data-ttu-id="a2c58-126">例如：</span><span class="sxs-lookup"><span data-stu-id="a2c58-126">For example:</span></span>  
  
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
  
-   <span data-ttu-id="a2c58-127">未定义为一个业务流程参数**XLANGMessage**或**XLANGPart**。</span><span class="sxs-lookup"><span data-stu-id="a2c58-127">Do not define an orchestration parameter as **XLANGMessage** or **XLANGPart**.</span></span> <span data-ttu-id="a2c58-128">如果您想要传递某一消息，则使用某一消息类型参数来传递该消息。</span><span class="sxs-lookup"><span data-stu-id="a2c58-128">If you want to pass a message, then use a message type parameter to pass the message.</span></span> <span data-ttu-id="a2c58-129">如果您想要传递某一部分，则改为传递该消息，然后使用该部分。</span><span class="sxs-lookup"><span data-stu-id="a2c58-129">If you want to pass a part, then pass the message instead and then use the part.</span></span> <span data-ttu-id="a2c58-130">如果您只是想要部分值，则使用部分类型传递该部分。</span><span class="sxs-lookup"><span data-stu-id="a2c58-130">If you only want the part value, then use the part type to pass the part.</span></span>  
  
-   <span data-ttu-id="a2c58-131">不返回**XLANGMessage**方法调用的参数。</span><span class="sxs-lookup"><span data-stu-id="a2c58-131">Do not return an **XLANGMessage** parameter for a method call.</span></span> <span data-ttu-id="a2c58-132">如果返回**XLANGMessage**传入的参数，然后你不能调用**释放**方法对方法调用中的参数，它直观地违反了生存期假设和它还引发异常。</span><span class="sxs-lookup"><span data-stu-id="a2c58-132">If you return an **XLANGMessage** parameter that is passed in, and then you cannot call the **Dispose** method on the parameter inside the method call, it intuitively violates lifetime assumptions and it also throws an exception.</span></span> <span data-ttu-id="a2c58-133">传递通过一条消息时**XLANGMessage**对于用户代码的参数，你将引用到的特殊的上下文，通常没有与其引用的消息的消息。</span><span class="sxs-lookup"><span data-stu-id="a2c58-133">When passing a message through an **XLANGMessage** parameter to user code, you reference the message to a special context that does not normally have messages referenced to it.</span></span> <span data-ttu-id="a2c58-134">此上下文的生存期就是业务流程实例的生存期。</span><span class="sxs-lookup"><span data-stu-id="a2c58-134">The lifetime of this context is the lifetime of the orchestration instance.</span></span> <span data-ttu-id="a2c58-135">其原因在于，BizTalk Server 不知道用户代码是否将占有消息。</span><span class="sxs-lookup"><span data-stu-id="a2c58-135">This is because BizTalk Server does not know whether the user code will hold onto the message.</span></span>  
  
     <span data-ttu-id="a2c58-136">在业务流程实例退出时，在该实例中创建的任何消息都不再有效，因此，此类集合的生存期应短于或等于实例的生存期。</span><span class="sxs-lookup"><span data-stu-id="a2c58-136">When an orchestration instance exits, any messages created in that instance are no longer valid, so the lifetime of such a collection should be less than or equal to that of the instance lifetime.</span></span> <span data-ttu-id="a2c58-137">但是，如果你想要将消息已传递时释放在循环中的消息引用**XLANGMessage**具有作为业务流程实例相同的生存期，则可以调用的自变量**XLANGMessage.Dispose**以释放该引用。</span><span class="sxs-lookup"><span data-stu-id="a2c58-137">However, if you want to release a message reference in a loop when the message was passed through an **XLANGMessage** argument that has the same lifetime as the orchestration instance, then you can call **XLANGMessage.Dispose** to free up the reference.</span></span> <span data-ttu-id="a2c58-138">此外，如果在用户代码方法中， **XLANGMessage**仅本地使用参数和参数的生存期包含在于函数调用中，你还可以调用**XLANGMessage.Dispose**来释放对根上下文的引用并重新授予相应的消息，则会正常生存期行为。</span><span class="sxs-lookup"><span data-stu-id="a2c58-138">Moreover, if inside the user code method, the **XLANGMessage** parameter is only used locally and the lifetime of the parameter is contained in that of the function call, you can also call **XLANGMessage.Dispose** to free up the reference to the root context and give the corresponding message back the normal lifetime behavior.</span></span> <span data-ttu-id="a2c58-139">例如：</span><span class="sxs-lookup"><span data-stu-id="a2c58-139">For example:</span></span>  
  
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
  
     <span data-ttu-id="a2c58-140">如果你将 xlm 放在一个集合，则此类本身必须具有**释放**进行清理的方法。</span><span class="sxs-lookup"><span data-stu-id="a2c58-140">If you place the xlm in a collection, then the class itself must have a **Dispose** method for cleanup.</span></span> <span data-ttu-id="a2c58-141">例如：</span><span class="sxs-lookup"><span data-stu-id="a2c58-141">For example:</span></span>  
  
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
  
     <span data-ttu-id="a2c58-142">你应该调用**A.Dispose**完成之后使用的集合**XLANGMessages**。</span><span class="sxs-lookup"><span data-stu-id="a2c58-142">You would call **A.Dispose** when you are finished with the collection of **XLANGMessages**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2c58-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a2c58-143">See Also</span></span>  
 <span data-ttu-id="a2c58-144">[表示为 XSD 架构的消息](../core/messages-represented-as-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="a2c58-144">[Messages Represented as XSD Schemas](../core/messages-represented-as-xsd-schemas.md) </span></span>  
 <span data-ttu-id="a2c58-145">[.NET 类表示的消息](../core/messages-represented-as-net-classes.md) </span><span class="sxs-lookup"><span data-stu-id="a2c58-145">[Messages Represented as .NET Classes](../core/messages-represented-as-net-classes.md) </span></span>  
 [<span data-ttu-id="a2c58-146">在用户代码中构造消息</span><span class="sxs-lookup"><span data-stu-id="a2c58-146">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)