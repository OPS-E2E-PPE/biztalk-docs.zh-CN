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
# <a name="how-to-use-expressions-to-perform-message-assignments"></a><span data-ttu-id="0e526-102">如何使用表达式来执行消息分配</span><span class="sxs-lookup"><span data-stu-id="0e526-102">How to Use Expressions to Perform Message Assignments</span></span>
<span data-ttu-id="0e526-103">表达式可用于在业务流程中处理以各种方式的消息。</span><span class="sxs-lookup"><span data-stu-id="0e526-103">You can use expressions to manipulate messages in various ways in your orchestration.</span></span>  
  
## <a name="referring-to-message-fields"></a><span data-ttu-id="0e526-104">消息字段引用</span><span class="sxs-lookup"><span data-stu-id="0e526-104">Referring to message fields</span></span>  
 <span data-ttu-id="0e526-105">可以按如下所示将字段名称附加到消息名称引用的一条消息中的可分辨字段：</span><span class="sxs-lookup"><span data-stu-id="0e526-105">You can refer to a distinguished field in a message by appending the field name to the message name as follows:</span></span>  
  
```  
MyMsg.Amount  
```  
  
 <span data-ttu-id="0e526-106">在此示例中，MyMsg 是消息，并量是已标识为消息类型的可分辨字段，MyMsg 所基于的字段。</span><span class="sxs-lookup"><span data-stu-id="0e526-106">In this example, MyMsg is the message, and Amount is a field that has been identified as a distinguished field for the message type that MyMsg is based on.</span></span>  
  
## <a name="assigning-to-messages-and-message-parts"></a><span data-ttu-id="0e526-107">将分配给消息和消息部分</span><span class="sxs-lookup"><span data-stu-id="0e526-107">Assigning to messages and message parts</span></span>  
 <span data-ttu-id="0e526-108">您可以直接向另一条消息或消息部分的消息部分分配一条消息：</span><span class="sxs-lookup"><span data-stu-id="0e526-108">You can assign a message directly to another message, or a message part to a message part:</span></span>  
  
```  
MyMsg=IncomingMsg;  
MyMsg.Invoice=IncomingMsg.Invoice;  
```  
  
 <span data-ttu-id="0e526-109">在此示例中，Invoice 是基于架构的消息部分。</span><span class="sxs-lookup"><span data-stu-id="0e526-109">In this example, Invoice is a message part based on a schema.</span></span>  
  
 <span data-ttu-id="0e526-110">如果你想要修改已构造的消息的属性，例如已收到的消息，必须通过将第一个分配到第二个构造消息形状中构造新消息并修改的属性中的新消息在同一构造消息形状。</span><span class="sxs-lookup"><span data-stu-id="0e526-110">If you want to modify a property on a message that has already been constructed—such as a message that has been received—you must construct a new message by assigning the first to the second in a Construct Message shape, and modify the property on the new message within the same Construct Message shape.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e526-111">不能引用或分配给消息字段，诸如 mymsg.invoice.myfield 之类，除非已升级这些;你只可以引用或分配给整个消息、 消息部分、 升级的消息属性或可分辨的字段。</span><span class="sxs-lookup"><span data-stu-id="0e526-111">You cannot refer or assign to message fields, such as MyMsg.Invoice.MyField, unless they have been promoted; you can only refer or assign to entire messages, message parts, promoted message properties, or distinguished fields.</span></span>  
  
## <a name="adding-message-parts"></a><span data-ttu-id="0e526-112">添加消息部分</span><span class="sxs-lookup"><span data-stu-id="0e526-112">Adding message parts</span></span>  
 <span data-ttu-id="0e526-113">可以通过使用现有的多部分消息中添加其他部分**XLANGs.BaseTypes.XLANGMessage.AddPart**方法。</span><span class="sxs-lookup"><span data-stu-id="0e526-113">You can add additional parts to an existing multipart message by using the **XLANGs.BaseTypes.XLANGMessage.AddPart** method.</span></span> <span data-ttu-id="0e526-114">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0e526-114">To do so, do the following:</span></span>  
  
-   <span data-ttu-id="0e526-115">创建C#项目，并添加对的引用**Microsoft.XLANGs.BaseTypes**。</span><span class="sxs-lookup"><span data-stu-id="0e526-115">Create a C# project and add a reference to **Microsoft.XLANGs.BaseTypes**.</span></span>  
  
-   <span data-ttu-id="0e526-116">实现类似于下面的公共类：</span><span class="sxs-lookup"><span data-stu-id="0e526-116">Implement a public class similar to the following:</span></span>  
  
    ```  
    public class MyAddPartHelper  
    {  
         public static void AddPart(XLANGMessage msg, object part, String partName)  
         {  
              msg.AddPart(part, partName);  
         }  
    }  
    ```  
  
     <span data-ttu-id="0e526-117">有三个重载的方法**microsoft.xlangs.basetypes.addpart 具有**:</span><span class="sxs-lookup"><span data-stu-id="0e526-117">There are three overloaded methods for **Microsoft.XLANGs.BaseTypes.AddPart**:</span></span>  
  
    ```  
    public void AddPart(object part, String partName);  
    public void AddPart(XLANGPart part);  
    public void AddPart(XLANGPart part, String partName);  
    ```  
  
-   <span data-ttu-id="0e526-118">在 BizTalk 项目中，添加对公共类和调用的引用**AddPart**方法从**表达式**形状在业务流程中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e526-118">In your BizTalk project, add a reference to the public class and call the **AddPart** method from the **Expression** shape in your orchestration as follows:</span></span>  
  
    ```  
    MyAddPartHelper.AddPart(myMessage, myStringObject, “StringObject1”);  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="0e526-119">不能用作消息部分添加非可序列化对象或自定义格式化的对象。</span><span class="sxs-lookup"><span data-stu-id="0e526-119">You cannot add non-serializable objects or custom formatted objects as message parts.</span></span> <span data-ttu-id="0e526-120">添加使用的其他部分之前，必须初始化所有静态部分**AddPart**方法。</span><span class="sxs-lookup"><span data-stu-id="0e526-120">All static parts must be initialized before adding additional parts using the **AddPart** method.</span></span> <span data-ttu-id="0e526-121">您可以添加任意部分仅在其消息内消息构造语句。</span><span class="sxs-lookup"><span data-stu-id="0e526-121">You can add arbitrary parts to a message only inside its message construct statement.</span></span> <span data-ttu-id="0e526-122">不支持添加消息之外的其他部分构造语句。</span><span class="sxs-lookup"><span data-stu-id="0e526-122">Adding additional parts outside of the message construct statement is not supported.</span></span>  
  
## <a name="retrieving-message-parts"></a><span data-ttu-id="0e526-123">检索消息部分</span><span class="sxs-lookup"><span data-stu-id="0e526-123">Retrieving message parts</span></span>  
 <span data-ttu-id="0e526-124">可以通过使用从现有的多部分消息中检索消息部分**RetrieveAs**方法从**Microsoft.XLANGs.BaseTypes**。</span><span class="sxs-lookup"><span data-stu-id="0e526-124">You can retrieve a message part from an existing multipart message by using the **RetrieveAs** method from **Microsoft.XLANGs.BaseTypes**.</span></span> <span data-ttu-id="0e526-125">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0e526-125">To do so, do the following:</span></span>  
  
-   <span data-ttu-id="0e526-126">创建C#项目，并添加对的引用**Microsoft.XLANGs.BaseTypes**。</span><span class="sxs-lookup"><span data-stu-id="0e526-126">Create a C# project and add a reference to **Microsoft.XLANGs.BaseTypes**.</span></span>  
  
-   <span data-ttu-id="0e526-127">实现类似于下面的公共类：</span><span class="sxs-lookup"><span data-stu-id="0e526-127">Implement a public class similar to the following:</span></span>  
  
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
    >  <span data-ttu-id="0e526-128">**RetrieveAs**方法支持检索消息部分，按名称和索引。</span><span class="sxs-lookup"><span data-stu-id="0e526-128">The **RetrieveAs** method supports retrieving message parts by name and by index.</span></span>  
  
-   <span data-ttu-id="0e526-129">在 BizTalk 项目中，添加对公共类和调用的引用**GetPart**方法从**表达式**形状在业务流程中，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0e526-129">In your BizTalk project, add a reference to the public class and call the **GetPart** method from the **Expression** shape in your orchestration as follows:</span></span>  
  
    ```  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, "StringObject1" , typeof(System.String));  
    //sPart is a type of System.String  
    sPart = (System.String) MyAddPartHelper.GetPart(msg, 1, typeof(System.String));  
    //Retriving the message part with index = 1  
    ```  
  
## <a name="message-part-context-property-access"></a><span data-ttu-id="0e526-130">消息部分上下文属性访问</span><span class="sxs-lookup"><span data-stu-id="0e526-130">Message part context property access</span></span>  
 <span data-ttu-id="0e526-131">消息部分都有独立于消息上下文的上下文。</span><span class="sxs-lookup"><span data-stu-id="0e526-131">A message part has context separate from the message context.</span></span> <span data-ttu-id="0e526-132">在设置时，可以构造消息部分上下文属性通过架构编辑器**Property Schema Base**到关联的元素属性的**PartContextPropertyBase。**</span><span class="sxs-lookup"><span data-stu-id="0e526-132">You can construct message part context properties through the schema editor when you set the **Property Schema Base** property for the associated element to **PartContextPropertyBase.**</span></span>  
  
 <span data-ttu-id="0e526-133">访问是类似于消息属性，通过之类的表达式：</span><span class="sxs-lookup"><span data-stu-id="0e526-133">The access is similar to message properties, through an expression like:</span></span>  
  
```  
Msg.PartName(myPartContextProperty)  
```  
  
 <span data-ttu-id="0e526-134">例如：</span><span class="sxs-lookup"><span data-stu-id="0e526-134">For example:</span></span>  
  
```  
Str=Msg.PartName(myPartContextProperty); //assumes myPartContextProperty is of type string  
```  
  
## <a name="xlangmessage-context-property-access"></a><span data-ttu-id="0e526-135">XLANGMessage 上下文属性访问</span><span class="sxs-lookup"><span data-stu-id="0e526-135">XLANGMessage context property access</span></span>  
 <span data-ttu-id="0e526-136">如果你想要访问消息属性**XLANGMessage**接口从你的代码，可以将消息传递类型的参数**Microsoft.XLANGs.BaseTypes.XLANGMessage**方法从表达式形状，然后使用**Microsoft.XLANGs.BaseTypes.XLANGMessage**方法**SetPropertyValue**并**GetPropertyValue**实现此。</span><span class="sxs-lookup"><span data-stu-id="0e526-136">If you would like to access message properties from the **XLANGMessage** interface from your code, you can pass the message as a parameter of type **Microsoft.XLANGs.BaseTypes.XLANGMessage** to a method from an Expression shape, and then use the **Microsoft.XLANGs.BaseTypes.XLANGMessage** methods **SetPropertyValue** and **GetPropertyValue** to achieve this.</span></span> <span data-ttu-id="0e526-137">为此，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0e526-137">To do so, do the following:</span></span>  
  
-   <span data-ttu-id="0e526-138">创建C#项目，并添加对的引用**Microsoft.XLANGs.BaseTypes**并**Microsoft.BizTalk.GlobalPropertySchemas**。</span><span class="sxs-lookup"><span data-stu-id="0e526-138">Create a C# project and add a reference to **Microsoft.XLANGs.BaseTypes** and **Microsoft.BizTalk.GlobalPropertySchemas**.</span></span>  
  
-   <span data-ttu-id="0e526-139">访问使用类似于代码的上下文属性如下：</span><span class="sxs-lookup"><span data-stu-id="0e526-139">Access the context property using the code similar to the below:</span></span>  
  
    ```  
    MyMsg.GetPropertyValue(typeof(BTS.MessageID));  
    MyMsg.SetPropertyValue(typeof(MIME.IsMultipartRelated), true);  
    ```  
  
> [!NOTE]
>  <span data-ttu-id="0e526-140">如果你想要获取或设置您自己的自定义上下文属性，则需要添加到属性架构项目的引用或添加对程序集的引用包含中的属性架构在C#项目。</span><span class="sxs-lookup"><span data-stu-id="0e526-140">If you would like to get or set your own custom context properties, you need to add a reference to your property schema project or add a reference to the assembly contains the property schemas in your C# project.</span></span>  
  
## <a name="assigning-to-message-properties"></a><span data-ttu-id="0e526-141">将分配给消息属性</span><span class="sxs-lookup"><span data-stu-id="0e526-141">Assigning to message properties</span></span>  
 <span data-ttu-id="0e526-142">可以将值分配到的消息属性：</span><span class="sxs-lookup"><span data-stu-id="0e526-142">You can assign a value to a message property:</span></span>  
  
```  
MyMessage(MySchemaNamespace.MyProperty)=True;  
```  
  
 <span data-ttu-id="0e526-143">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]可以引用并将值分配给多部分消息的 MIME 属性：</span><span class="sxs-lookup"><span data-stu-id="0e526-143">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] you can refer to and assign values to the MIME properties of a multi-part message:</span></span>  
  
```  
Message_Out.MessagePart_1(MIME.FileName)="document.doc";  
```  
  
> [!NOTE]
>  <span data-ttu-id="0e526-144">BizTalk 消息由消息上下文和消息部分组成。</span><span class="sxs-lookup"><span data-stu-id="0e526-144">A BizTalk message consists of message context and message parts.</span></span> <span data-ttu-id="0e526-145">可以获取或设置任何消息上下文属性; 之前，必须先初始化消息部分否则，将在 XLANG 编译时期间收到错误。</span><span class="sxs-lookup"><span data-stu-id="0e526-145">You must first initialize the message parts before you can get or set any message context property; otherwise, you will receive error during the XLANG compile time.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e526-146">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e526-146">See Also</span></span>  
 <span data-ttu-id="0e526-147">[业务流程中使用的消息](../core/using-messages-in-orchestrations.md) </span><span class="sxs-lookup"><span data-stu-id="0e526-147">[Using Messages in Orchestrations](../core/using-messages-in-orchestrations.md) </span></span>  
 [<span data-ttu-id="0e526-148">在用户代码中构造消息</span><span class="sxs-lookup"><span data-stu-id="0e526-148">Constructing Messages in User Code</span></span>](../core/constructing-messages-in-user-code.md)   