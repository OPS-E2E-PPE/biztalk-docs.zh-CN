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
# <a name="messages-represented-as-xlangmessage"></a><span data-ttu-id="0f688-102">表示为 XLANGMessage 的消息</span><span class="sxs-lookup"><span data-stu-id="0f688-102">Messages Represented as XLANGMessage</span></span>
<span data-ttu-id="0f688-103">**XLANGMessage**对象都表示用 XLANG 服务声明的消息实例。</span><span class="sxs-lookup"><span data-stu-id="0f688-103">An **XLANGMessage** object represents a message instance declared with an XLANG service.</span></span> <span data-ttu-id="0f688-104">通过将一条消息的引用作为方法调用中的参数传递，获取此对象。</span><span class="sxs-lookup"><span data-stu-id="0f688-104">This object is obtained by passing a reference to a message as a parameter in a method invocation.</span></span> <span data-ttu-id="0f688-105">**XLANGPart**对象表示在 XLANG 服务的消息实例中包含的消息部分。</span><span class="sxs-lookup"><span data-stu-id="0f688-105">An **XLANGPart** object represents a message part contained in a message instance within an XLANG service.</span></span> <span data-ttu-id="0f688-106">获取此对象通过其中接收的参数类型在方法调用中传递部分引用**XLANGPart**或通过在传递的引用上枚举**XLANGMessage**。</span><span class="sxs-lookup"><span data-stu-id="0f688-106">This object is obtained either by passing a part reference in a method invocation where the receiving parameter type is **XLANGPart** or by enumerating on a passed reference of **XLANGMessage**.</span></span>  
  
 <span data-ttu-id="0f688-107">业务流程消息变量可能会传递给某个用户组件和作为接收**XLANGMessage**对象。</span><span class="sxs-lookup"><span data-stu-id="0f688-107">An orchestration message variable may be passed to a user component and received as an **XLANGMessage** object.</span></span> <span data-ttu-id="0f688-108">**XLANGMessage**对象允许访问部件和访问消息属性。用户可能会"占有"到**XLANGMessage** ，从而扩展其生存期超过声明的范围。</span><span class="sxs-lookup"><span data-stu-id="0f688-108">The **XLANGMessage** object allows accessing the parts and accessing message properties.The user may "hold on" to an **XLANGMessage** and thereby extend its lifetime beyond the declared scope.</span></span> <span data-ttu-id="0f688-109">随后， **XLANGMessage**可能从方法返回并分配给在业务流程中的消息变量。</span><span class="sxs-lookup"><span data-stu-id="0f688-109">Subsequently, an **XLANGMessage** may be returned from a method and assigned to a message variable in an orchestration.</span></span>  
  
## <a name="constructing-an-xlangmessage"></a><span data-ttu-id="0f688-110">构造 XLANGMessage</span><span class="sxs-lookup"><span data-stu-id="0f688-110">Constructing an XLANGMessage</span></span>  
 <span data-ttu-id="0f688-111">构造时**XLANGMessage**与流、 流类型必须实现**IStreamFactory**也是**MemoryStream**。</span><span class="sxs-lookup"><span data-stu-id="0f688-111">When constructing an **XLANGMessage** with a stream, the stream type must either implement **IStreamFactory** or be a **MemoryStream**.</span></span> <span data-ttu-id="0f688-112">下面的代码示例显示如何构造**XLANGMessage**:</span><span class="sxs-lookup"><span data-stu-id="0f688-112">The following code sample shows how to construct an **XLANGMessage**:</span></span>  
  
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
  
 <span data-ttu-id="0f688-113">可能存在你想要创建新的消息而不转换源消息。</span><span class="sxs-lookup"><span data-stu-id="0f688-113">There may be times when you want to create a new message without transforming a source message.</span></span> <span data-ttu-id="0f688-114">您可以执行此操作使用的类型的变量**System.Xml.XmlDocument**并加载或构造适当的内容。</span><span class="sxs-lookup"><span data-stu-id="0f688-114">You can do this by using a variable of type **System.Xml.XmlDocument** and loading or otherwise constructing appropriate content.</span></span> <span data-ttu-id="0f688-115">在以下示例中，加载 XML 字符串中使用**LoadXml**方法**XmlDocument**:</span><span class="sxs-lookup"><span data-stu-id="0f688-115">In the following example, XML is loaded from a string by using the **LoadXml** method of **XmlDocument**:</span></span>  
  
```csharp
XmlVariable.LoadXml("<ns0:Root PONumber="047745351122111" xmlns:ns0="http://BTSHTTPSend.SimpleSchema"><MyChildRecord SubAttr1="Simple Attribute " /></ns0:Root>");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
 <span data-ttu-id="0f688-116">下面的示例通过从文件加载 XML**负载**方法**XmlDocument**:</span><span class="sxs-lookup"><span data-stu-id="0f688-116">The following example loads XML from a file by using the **Load** method of **XmlDocument**:</span></span>  
  
```csharp
XmlVariable.Load("C:\MyData.xml");  
XLANGMessage XmlMsg = XmlVariable;  
  
```  
  
> [!NOTE]
>  <span data-ttu-id="0f688-117">如果你想要构造更大的消息，使用在上一部分中阐释的流方法之一，或考虑使用**转换**形状在业务流程设计器中的。</span><span class="sxs-lookup"><span data-stu-id="0f688-117">If you want to construct larger messages, use one of the streaming methods demonstrated in the previous section or consider using the **Transform** shape in Orchestration Designer.</span></span>  
  
## <a name="considerations-when-using-xlangmessage-and-xlangpart"></a><span data-ttu-id="0f688-118">使用 XLANGMessage 和 XLANGPart 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="0f688-118">Considerations When Using XLANGMessage and XLANGPart</span></span>  
 <span data-ttu-id="0f688-119">使用时**XLANGMessage**并**XLANGPart**在用户代码中，请考虑以下：</span><span class="sxs-lookup"><span data-stu-id="0f688-119">When using **XLANGMessage** and **XLANGPart** in user code, consider the following:</span></span>  
  
-   <span data-ttu-id="0f688-120">不将消息部分作为**XLANGPart**自变量或返回类型的值**XLANGPart**。</span><span class="sxs-lookup"><span data-stu-id="0f688-120">Do not pass a message part as an **XLANGPart** argument or return a value of type **XLANGPart**.</span></span> <span data-ttu-id="0f688-121">应传递**XLANGPart**作为部件的类型。</span><span class="sxs-lookup"><span data-stu-id="0f688-121">You should pass **XLANGPart** as the type of the part.</span></span> <span data-ttu-id="0f688-122">例如：</span><span class="sxs-lookup"><span data-stu-id="0f688-122">For example:</span></span>  
  
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
  
     <span data-ttu-id="0f688-123">你还可以传递消息本身作为**XLANGMessage**并用**XLANGMessage**下标运算符来访问函数调用中的部分。</span><span class="sxs-lookup"><span data-stu-id="0f688-123">You can also pass the message itself as an **XLANGMessage** and use the **XLANGMessage** subscript operators to access the part inside the function call.</span></span> <span data-ttu-id="0f688-124">但是，不应放**XLANGPart**其生命周期持续时间的函数调用的生存期集合中。</span><span class="sxs-lookup"><span data-stu-id="0f688-124">However, you should not put an **XLANGPart** in a collection whose lifetime extends past the lifetime of the function call.</span></span> <span data-ttu-id="0f688-125">相反，应将放**XLANGMessage**集合中。</span><span class="sxs-lookup"><span data-stu-id="0f688-125">Instead, you should put the **XLANGMessage** in the collection.</span></span> <span data-ttu-id="0f688-126">例如：</span><span class="sxs-lookup"><span data-stu-id="0f688-126">For example:</span></span>  
  
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
  
-   <span data-ttu-id="0f688-127">未定义为将业务流程参数**XLANGMessage**或**XLANGPart**。</span><span class="sxs-lookup"><span data-stu-id="0f688-127">Do not define an orchestration parameter as **XLANGMessage** or **XLANGPart**.</span></span> <span data-ttu-id="0f688-128">如果你想要将传递一条消息，然后使用消息类型参数来传递该消息。</span><span class="sxs-lookup"><span data-stu-id="0f688-128">If you want to pass a message, then use a message type parameter to pass the message.</span></span> <span data-ttu-id="0f688-129">如果你想要传递某一部分，然后改为传入消息，然后使用该部件。</span><span class="sxs-lookup"><span data-stu-id="0f688-129">If you want to pass a part, then pass the message instead and then use the part.</span></span> <span data-ttu-id="0f688-130">如果只想部分值，然后使用部分类型传递该部分。</span><span class="sxs-lookup"><span data-stu-id="0f688-130">If you only want the part value, then use the part type to pass the part.</span></span>  
  
-   <span data-ttu-id="0f688-131">不会返回**XLANGMessage**方法调用的参数。</span><span class="sxs-lookup"><span data-stu-id="0f688-131">Do not return an **XLANGMessage** parameter for a method call.</span></span> <span data-ttu-id="0f688-132">如果返回**XLANGMessage**参数传入，并且您不能调用**Dispose**方法内对该参数在方法调用，它显然违反生存期假设并且还引发异常。</span><span class="sxs-lookup"><span data-stu-id="0f688-132">If you return an **XLANGMessage** parameter that is passed in, and then you cannot call the **Dispose** method on the parameter inside the method call, it intuitively violates lifetime assumptions and it also throws an exception.</span></span> <span data-ttu-id="0f688-133">当将通过消息传递**XLANGMessage**到用户代码的参数，则引用通常没有向其引用的消息的特殊上下文的消息。</span><span class="sxs-lookup"><span data-stu-id="0f688-133">When passing a message through an **XLANGMessage** parameter to user code, you reference the message to a special context that does not normally have messages referenced to it.</span></span> <span data-ttu-id="0f688-134">此上下文的生存期就是业务流程实例的生存期。</span><span class="sxs-lookup"><span data-stu-id="0f688-134">The lifetime of this context is the lifetime of the orchestration instance.</span></span> <span data-ttu-id="0f688-135">这是因为 BizTalk Server 不知道用户代码将占有消息。</span><span class="sxs-lookup"><span data-stu-id="0f688-135">This is because BizTalk Server does not know whether the user code will hold onto the message.</span></span>  
  
     <span data-ttu-id="0f688-136">业务流程实例退出时，该实例中创建的任何消息将不再有效，因此，此类集合的生存期应小于或等于该实例的生存期。</span><span class="sxs-lookup"><span data-stu-id="0f688-136">When an orchestration instance exits, any messages created in that instance are no longer valid, so the lifetime of such a collection should be less than or equal to that of the instance lifetime.</span></span> <span data-ttu-id="0f688-137">但是，如果你想要通过传递消息时释放循环中的消息引用**XLANGMessage**具有相同的生存期与业务流程实例，则可以调用的参数**XLANGMessage.Dispose**以释放该引用。</span><span class="sxs-lookup"><span data-stu-id="0f688-137">However, if you want to release a message reference in a loop when the message was passed through an **XLANGMessage** argument that has the same lifetime as the orchestration instance, then you can call **XLANGMessage.Dispose** to free up the reference.</span></span> <span data-ttu-id="0f688-138">此外，在用户代码方法中，如果**XLANGMessage**参数仅在本地使用，并且，函数调用中，您还可以调用包含参数的生存期**XLANGMessage.Dispose**释放对根上下文的引用，并为相应的消息返回提供通常的生存期。</span><span class="sxs-lookup"><span data-stu-id="0f688-138">Moreover, if inside the user code method, the **XLANGMessage** parameter is only used locally and the lifetime of the parameter is contained in that of the function call, you can also call **XLANGMessage.Dispose** to free up the reference to the root context and give the corresponding message back the normal lifetime behavior.</span></span> <span data-ttu-id="0f688-139">例如：</span><span class="sxs-lookup"><span data-stu-id="0f688-139">For example:</span></span>  
  
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
  
     <span data-ttu-id="0f688-140">如果您将 xlm 放置在一个集合，则类本身必须具有**Dispose**清理方法。</span><span class="sxs-lookup"><span data-stu-id="0f688-140">If you place the xlm in a collection, then the class itself must have a **Dispose** method for cleanup.</span></span> <span data-ttu-id="0f688-141">例如：</span><span class="sxs-lookup"><span data-stu-id="0f688-141">For example:</span></span>  
  
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
  
     <span data-ttu-id="0f688-142">将调用**应该**完成后使用的集合**XLANGMessages**。</span><span class="sxs-lookup"><span data-stu-id="0f688-142">You would call **A.Dispose** when you are finished with the collection of **XLANGMessages**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f688-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f688-143">See Also</span></span>  
 <span data-ttu-id="0f688-144">[表示为 XSD 架构的消息](../core/messages-represented-as-xsd-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="0f688-144">[Messages Represented as XSD Schemas](../core/messages-represented-as-xsd-schemas.md) </span></span>  
 <span data-ttu-id="0f688-145">[表示为.NET 类的消息](../core/messages-represented-as-net-classes.md) </span><span class="sxs-lookup"><span data-stu-id="0f688-145">[Messages Represented as .NET Classes](../core/messages-represented-as-net-classes.md) </span></span>  
 [<span data-ttu-id="0f688-146">在用户代码中构造消息</span><span class="sxs-lookup"><span data-stu-id="0f688-146">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)
