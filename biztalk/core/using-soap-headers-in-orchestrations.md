---
title: 在业务流程中使用 SOAP 标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SOAP headers, orchestrations
- SOAP headers, code samples
- SOAP headers, creating
- SOAP headers, properties
- Web services, SOAP headers
- orchestrations, SOAP headers
- creating, SOAP headers
ms.assetid: 4754dd23-386b-4093-8ea4-4da6b4d9279c
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cce21530c975356b811378f437cddaf8eb64612d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65321772"
---
# <a name="using-soap-headers-in-orchestrations"></a><span data-ttu-id="c7626-102">在业务流程中使用 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="c7626-102">Using SOAP Headers in Orchestrations</span></span>
<span data-ttu-id="c7626-103">业务流程使用属性架构来定义 SOAP 标头上下文属性。</span><span class="sxs-lookup"><span data-stu-id="c7626-103">Orchestrations use property schemas to define SOAP header context properties.</span></span> <span data-ttu-id="c7626-104">使用 BizTalk 编辑器可以设置 SOAP 标头上下文属性。</span><span class="sxs-lookup"><span data-stu-id="c7626-104">You use the BizTalk Editor to set SOAP header context properties.</span></span>  
  
## <a name="defining-soap-header-context-properties-with-property-schemas"></a><span data-ttu-id="c7626-105">使用属性架构定义 SOAP 标头上下文属性</span><span class="sxs-lookup"><span data-stu-id="c7626-105">Defining SOAP header context properties with property schemas</span></span>  
 <span data-ttu-id="c7626-106">若要在业务流程中使用已定义的 SOAP 标头上下文属性，您需要一个属性架构。</span><span class="sxs-lookup"><span data-stu-id="c7626-106">You need a property schema to use defined SOAP header context properties in orchestrations.</span></span> <span data-ttu-id="c7626-107">属性架构必须具有的目标命名空间**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**，和**Property Schema Base**属性设置为**MessageContextPropertyBase**。</span><span class="sxs-lookup"><span data-stu-id="c7626-107">The property schema must have the target namespace of **http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**, and the **Property Schema Base** property set to **MessageContextPropertyBase**.</span></span> <span data-ttu-id="c7626-108">属性架构中的每个根元素名称必须与已定义的 SOAP 标头的根元素名称匹配。</span><span class="sxs-lookup"><span data-stu-id="c7626-108">Each root element name in the property schema must match the root element name in the defined SOAP header.</span></span> <span data-ttu-id="c7626-109">然后，可以使用属性架构的命名空间和属性名称设置上下文属性的值。</span><span class="sxs-lookup"><span data-stu-id="c7626-109">You can then set values for the context properties using the namespace of the property schema and the property name.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7626-110">属性架构的命名空间是不同于目标架构的命名空间 (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**)。</span><span class="sxs-lookup"><span data-stu-id="c7626-110">The namespace of the property schema is different from the namespace of the target schema (**http://schemas.microsoft.com/BizTalk/2003/SOAPHeader**).</span></span> <span data-ttu-id="c7626-111">命名空间可以是任何字符串；但是，它通常默认为项目的名称。</span><span class="sxs-lookup"><span data-stu-id="c7626-111">Your namespace can be any string; however, it usually defaults to the name of the project.</span></span>  
  
 <span data-ttu-id="c7626-112">下面的代码演示分配属性架构命名空间的 SOAP 标头上下文属性**SOAPHeader**属性名称为**OrigDest**:</span><span class="sxs-lookup"><span data-stu-id="c7626-112">The following code shows assigning a SOAP header context property where the property schema namespace is **SOAPHeader** with a property name of **OrigDest**:</span></span>  
  
```  
requestMessageInstance(SOAPHeader.OrigDest) = stringVar;  
```  
  
 <span data-ttu-id="c7626-113">有关属性架构和上下文属性的详细信息，请参阅[属性架构](../core/property-schemas.md)。</span><span class="sxs-lookup"><span data-stu-id="c7626-113">For more information about property schemas and context properties, see [Property Schemas](../core/property-schemas.md).</span></span>  
  
## <a name="using-biztalk-editor-to-set-soap-header-context-properties"></a><span data-ttu-id="c7626-114">使用 BizTalk 编辑器设置 SOAP 标头上下文属性</span><span class="sxs-lookup"><span data-stu-id="c7626-114">Using BizTalk Editor to set SOAP header context properties</span></span>  
 <span data-ttu-id="c7626-115">对于业务流程，SOAP 标头上下文属性均设置为包含 XML 数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="c7626-115">For orchestrations, the SOAP header context properties are set to strings that contain XML data.</span></span> <span data-ttu-id="c7626-116">设置使用中的 BizTalk 表达式编辑器这些字符串**消息分配**或**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="c7626-116">You set these strings using the BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span>  
  
 <span data-ttu-id="c7626-117">下面的示例演示设置该上下文属性的字符串：</span><span class="sxs-lookup"><span data-stu-id="c7626-117">The following example shows the string setting the context property:</span></span>  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = "<?xml version=\"1.0\"?>  
<OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\">  
<Origination>Home</Origination>  
<Destination>Work</Destination>  
</OrigDest>"  
```  
  
## <a name="using-biztalk-editor-to-create-an-instance-of-a-soap-header-root-element"></a><span data-ttu-id="c7626-118">使用 BizTalk 编辑器创建 SOAP 标头根元素的实例</span><span class="sxs-lookup"><span data-stu-id="c7626-118">Using BizTalk Editor to create an instance of a SOAP header root element</span></span>  
 <span data-ttu-id="c7626-119">将 SOAP 标头设置为正确的字符串可能并不容易。</span><span class="sxs-lookup"><span data-stu-id="c7626-119">Setting the SOAP header to the correct string can be difficult.</span></span> <span data-ttu-id="c7626-120">添加对 BizTalk 项目的 Web 引用时，所有复杂的 Web 消息部分都将作为根元素添加到 Reference.xsd。</span><span class="sxs-lookup"><span data-stu-id="c7626-120">When adding a Web reference to a BizTalk project, all complex Web message parts are added to Reference.xsd as root elements.</span></span> <span data-ttu-id="c7626-121">Reference.xsd 还包含每个已定义的 SOAP 标头的根元素。</span><span class="sxs-lookup"><span data-stu-id="c7626-121">Reference.xsd also contains root elements for each defined SOAP header.</span></span> <span data-ttu-id="c7626-122">为确保使用正确的字符串设置 SOAP 标头，应使用 BizTalk 编辑器为 Reference.xsd 创建 SOAP 标头根元素的实例。</span><span class="sxs-lookup"><span data-stu-id="c7626-122">To ensure that you set the SOAP header with the correct string, you should use BizTalk Editor to create an instance of the SOAP header root element for Reference.xsd.</span></span> <span data-ttu-id="c7626-123">您可以直接使用生成的实例数据，或使用包含实际数据的实例数据。</span><span class="sxs-lookup"><span data-stu-id="c7626-123">You can use the generated instance data directly or the instance data to contain your real data.</span></span>  
  
 <span data-ttu-id="c7626-124">有关使用 BizTalk 编辑器生成实例数据的详细信息，请参阅[如何生成实例消息](../core/how-to-generate-instance-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="c7626-124">For more information about using the BizTalk Editor to generate instance data, see [How to Generate Instance Messages](../core/how-to-generate-instance-messages.md).</span></span>  
  
## <a name="creating-an-xmldocument-to-set-context-properties"></a><span data-ttu-id="c7626-125">创建用于设置上下文属性的 XmlDocument</span><span class="sxs-lookup"><span data-stu-id="c7626-125">Creating an XmlDocument to set context properties</span></span>  
 <span data-ttu-id="c7626-126">你可以通过创建设置上下文属性**XmlDocument**和写入的字符串值**XmlDocument**到上下文属性。</span><span class="sxs-lookup"><span data-stu-id="c7626-126">You can set context properties by creating an **XmlDocument** and writing the string value of the **XmlDocument** to the context property.</span></span> <span data-ttu-id="c7626-127">声明类型的变量的**XMLDocument**并将 XML 数据分配。</span><span class="sxs-lookup"><span data-stu-id="c7626-127">You declare a variable of type **XMLDocument** and assign the XML data.</span></span>  
  
 <span data-ttu-id="c7626-128">下面的示例演示设置声明类型的变量的**XMLDocument**并将 XML 数据分配：</span><span class="sxs-lookup"><span data-stu-id="c7626-128">The following example shows setting a declaring a variable of type **XMLDocument** and assign the XML data:</span></span>  
  
```  
xmlDoc.LoadXml("<?xml version=\"1.0\"?><OrigDest xmlns=\"http://SOAPHeaderSchemas.OrigDestSOAPHeader\"><Origination>Home</Origination><Destination>Work</Destination></OrigDest>");  
```  
  
 <span data-ttu-id="c7626-129">下面的示例显示了如何设置上下文属性：</span><span class="sxs-lookup"><span data-stu-id="c7626-129">The following example shows setting the context property:</span></span>  
  
```  
RequestMessageInstance(SOAPHeader.OrigDest) = xmlDoc.OuterXml;  
```  
  
 <span data-ttu-id="c7626-130">有关使用 BizTalk 表达式编辑器的详细信息，请参阅[表达式的要求和限制](../core/requirements-and-limitations-for-expressions.md)。</span><span class="sxs-lookup"><span data-stu-id="c7626-130">For more information about using BizTalk Expression Editor, see [Requirements and Limitations for Expressions](../core/requirements-and-limitations-for-expressions.md).</span></span> <span data-ttu-id="c7626-131">有关调用.NET 类的详细信息，请参阅[在用户代码中构造消息](../core/constructing-messages-in-user-code.md)。</span><span class="sxs-lookup"><span data-stu-id="c7626-131">For more information about calling .NET classes, see [Constructing Messages in User Code](../core/constructing-messages-in-user-code.md).</span></span>  
  
## <a name="creating-soap-headers-for-a-soap-request"></a><span data-ttu-id="c7626-132">为 SOAP 请求创建 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="c7626-132">Creating SOAP headers for a SOAP request</span></span>  
 <span data-ttu-id="c7626-133">为 SOAP 请求创建 SOAP 标头时，必须确保您已正确创建 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="c7626-133">When you create SOAP headers for the SOAP request, you must ensure that you have correctly created the SOAP headers.</span></span> <span data-ttu-id="c7626-134">SOAP 适配器不验证 SOAP 标头上下文属性的内容。</span><span class="sxs-lookup"><span data-stu-id="c7626-134">The SOAP adapter does not verify the contents of the SOAP header context properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7626-135">如果 SOAP 标头不正确，则 BizTalk 就不能将 SOAP 请求发送到 Web Services。</span><span class="sxs-lookup"><span data-stu-id="c7626-135">If the SOAP header is incorrect, BizTalk cannot send the SOAP request to the Web service.</span></span>  
  
 <span data-ttu-id="c7626-136">BizTalk 返回给 Web Services 的 SOAP 响应也可能包含 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="c7626-136">The SOAP response that BizTalk returns to the Web service may also contain SOAP headers.</span></span> <span data-ttu-id="c7626-137">只有 SOAP 标头为已定义的 SOAP 标头时才可以访问这些 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="c7626-137">You can only access these SOAP headers if they are defined SOAP headers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c7626-138">已使用的 Web Services 仅支持已定义的 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="c7626-138">Consumed Web services support only defined SOAP headers.</span></span>  
  
 <span data-ttu-id="c7626-139">有关定义的 SOAP 标头的详细信息，请参阅[使用 SOAP 标头](../core/using-soap-headers.md)。</span><span class="sxs-lookup"><span data-stu-id="c7626-139">For more information about defined SOAP headers, see [Using SOAP Headers](../core/using-soap-headers.md).</span></span> <span data-ttu-id="c7626-140">响应 SOAP 标头使用与请求 SOAP 标头相同的语法设置为上下文属性。</span><span class="sxs-lookup"><span data-stu-id="c7626-140">The response SOAP headers are set to context properties using the same syntax as the request SOAP headers.</span></span>  
  
 <span data-ttu-id="c7626-141">下面的代码显示了如何访问响应 SOAP 标头：</span><span class="sxs-lookup"><span data-stu-id="c7626-141">The following code shows how to access the response SOAP headers:</span></span>  
  
```  
stringVar = ResponseMessageInstance(SOAPHeader.OrigDest);  
```  
  
 <span data-ttu-id="c7626-142">上下文属性中包含的值是包含 XML 数据的字符串。</span><span class="sxs-lookup"><span data-stu-id="c7626-142">The values contained in the context properties are strings containing XML data.</span></span> <span data-ttu-id="c7626-143">设置使用 BizTalk 表达式编辑器，在这些字符串**消息分配**或**表达式**形状。</span><span class="sxs-lookup"><span data-stu-id="c7626-143">You set these strings using BizTalk Expression Editor in a **Message Assignment** or **Expression** shape.</span></span> <span data-ttu-id="c7626-144">加载中的字符串**XmlDocument**并使用 XPath 查询来访问特定字段。</span><span class="sxs-lookup"><span data-stu-id="c7626-144">You load the string in an **XmlDocument** and use XPath queries to access specific fields.</span></span>  
  
 <span data-ttu-id="c7626-145">有关创建 BizTalk 表达式编辑器中的 XML 文档的详细信息，请参阅[XLANG-s 语言](../core/xlang-s-language.md)。</span><span class="sxs-lookup"><span data-stu-id="c7626-145">For more information about creating XML documents in BizTalk Expression Editor, see [XLANG-s Language](../core/xlang-s-language.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7626-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7626-146">See Also</span></span>  
 <span data-ttu-id="c7626-147">[XLANG-s 语言](../core/xlang-s-language.md) </span><span class="sxs-lookup"><span data-stu-id="c7626-147">[XLANG-s Language](../core/xlang-s-language.md) </span></span>  
 [<span data-ttu-id="c7626-148">与使用的 Web 服务的 SOAP 标头</span><span class="sxs-lookup"><span data-stu-id="c7626-148">SOAP Headers with Consumed Web Services</span></span>](../core/soap-headers-with-consumed-web-services.md)