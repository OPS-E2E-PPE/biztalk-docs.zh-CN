---
title: 如何将业务流程映射到 Web 服务 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, Web services
- BizTalk Web Services Publishing Wizard, naming conventions
- Web services, orchestrations
- orchestrations, naming conventions
- Web services, naming conventions
ms.assetid: e6a58978-c81c-49f3-9428-9bff60f1ded7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f624c94a22efbfa56ae533ff9bfdbf3276776f8a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998582"
---
# <a name="how-to-map-orchestrations-to-web-services"></a><span data-ttu-id="c8c4d-102">如何将业务流程映射到 Web 服务</span><span class="sxs-lookup"><span data-stu-id="c8c4d-102">How to Map Orchestrations to Web Services</span></span>
<span data-ttu-id="c8c4d-103">业务流程可以有多个接收端口。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-103">An orchestration can have multiple receive ports.</span></span> <span data-ttu-id="c8c4d-104">使用 BizTalk Web Services 发布向导，选择接收端口，以发布为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-104">Using the BizTalk Web Services Publishing Wizard, you select receive ports to publish as Web services.</span></span> <span data-ttu-id="c8c4d-105">该向导将为每个接收端口创建一个 Web Services（.asmx 文件）。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-105">The wizard creates one Web service (.asmx file) for each receive port.</span></span> <span data-ttu-id="c8c4d-106">如果它们是相同的接收端口类型，该向导还可以创建一个 Web 服务进行的所有接收端口 (单向或请求/响应)。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-106">The wizard can also create one Web service for all of the receive ports if they are the same receive port type (one-way or request/response).</span></span> <span data-ttu-id="c8c4d-107">操作变得函数调用。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-107">Operations become function calls.</span></span> <span data-ttu-id="c8c4d-108">接收端口中的每个操作将成为一个 Web 方法。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-108">Each operation in the receive port becomes a Web method.</span></span> <span data-ttu-id="c8c4d-109">请求操作变得输入的参数。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-109">Request operations become input parameters.</span></span> <span data-ttu-id="c8c4d-110">响应操作变得返回类型。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-110">Response operations become return types.</span></span>  
  
 <span data-ttu-id="c8c4d-111">如果请求和响应操作相同的 Web 消息类型，输入的参数将成为**ref**且返回类型为**void**。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-111">If the request and response operations are the same Web message type, the input parameter becomes a **ref** and the return type is **void**.</span></span> <span data-ttu-id="c8c4d-112">ASP.NET Web 客户端可以通过合并相同类型的 in 参数和 out 参数更改 Web 方法签名。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-112">ASP.NET Web clients may change the Web method signature by combining the in and out parameters of the same type.</span></span> <span data-ttu-id="c8c4d-113">例如，ASP.NET Web 客户端可能会更改 BizTalk Web 方法从**myService （字符串一部分） 的字符串**到**void myService （ref 字符串一部分）**。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-113">For example, an ASP.NET Web client may change a BizTalk Web method from **string myService(string part)** to **void myService(ref string part)**.</span></span>  
  
 <span data-ttu-id="c8c4d-114">这些操作消息类型定义 Web 方法的签名。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-114">The operation message types define the Web method signatures.</span></span> <span data-ttu-id="c8c4d-115">每个消息类型部分是 Web 方法中的一个参数。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-115">Each message type part is a parameter in the Web method.</span></span>  
  
## <a name="message-type-part-names-and-target-namespaces"></a><span data-ttu-id="c8c4d-116">消息类型部分组成的名称和目标命名空间</span><span class="sxs-lookup"><span data-stu-id="c8c4d-116">Message type part names and target namespaces</span></span>  
 <span data-ttu-id="c8c4d-117">文档架构和用户定义类**XmlRootAttribute**指定是消息类型部分，用于定义目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-117">Document schemas and user defined classes with **XmlRootAttribute** specified are message type parts that have defined target namespaces.</span></span> <span data-ttu-id="c8c4d-118">EDI 架构，而无需用户定义的类**XmlRootAttribute**指定，和内置类型，如**System.String**是消息类型部分，而无需定义的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-118">EDI schemas, user-defined classes without **XmlRootAttribute** specified, and built-in types, such as **System.String** are message type parts without defined target namespaces.</span></span>  
  
|<span data-ttu-id="c8c4d-119">如果消息类型部分名称</span><span class="sxs-lookup"><span data-stu-id="c8c4d-119">If the message type part name has a</span></span>|<span data-ttu-id="c8c4d-120">使用参数名称</span><span class="sxs-lookup"><span data-stu-id="c8c4d-120">Parameter Name Used</span></span>|  
|-----------------------------------------|-------------------------|  
|<span data-ttu-id="c8c4d-121">定义的目标命名空间</span><span class="sxs-lookup"><span data-stu-id="c8c4d-121">Defined target namespace</span></span>|<span data-ttu-id="c8c4d-122">根元素名称</span><span class="sxs-lookup"><span data-stu-id="c8c4d-122">Root element name</span></span>|  
|<span data-ttu-id="c8c4d-123">没有定义的目标命名空间</span><span class="sxs-lookup"><span data-stu-id="c8c4d-123">No defined target namespace</span></span>|<span data-ttu-id="c8c4d-124">消息类型部分名称</span><span class="sxs-lookup"><span data-stu-id="c8c4d-124">Message type part name</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="c8c4d-125">当多部分消息类型用于响应消息时，BizTalk Web Services 发布向导的返回值使用第一个消息部分和剩余的消息部分使用为输出参数。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-125">When a multipart message type is used for the response message, the BizTalk Web Services Publishing Wizard uses the first message part for the return value and the remaining message parts are used as out parameters.</span></span>  
  
## <a name="orchestrations-with-multiple-operations"></a><span data-ttu-id="c8c4d-126">使用多个操作的业务流程</span><span class="sxs-lookup"><span data-stu-id="c8c4d-126">Orchestrations with multiple operations</span></span>  
 <span data-ttu-id="c8c4d-127">如果您的业务流程具有多个操作，则应设计您的业务流程有一个接收端口而不是多个接收端口。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-127">If your orchestration has multiple operations, you should design your orchestrations to have one receive port instead of several receive ports.</span></span> <span data-ttu-id="c8c4d-128">此设计可阻止 BizTalk Web Services 发布向导创建多个 Web 服务 (.asmx) 文件，并仅适用于所有操作都具有相同的调用模式时，所有单向操作或请求-响应的所有操作。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-128">This design prevents the BizTalk Web Services Publishing Wizard from creating multiple Web service (.asmx) files and only works when all the operations have the same calling pattern—all one-way operations or all request-response operations.</span></span> <span data-ttu-id="c8c4d-129">一个接收端口不能包含单向和请求/响应操作。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-129">A single receive port cannot contain both one-way and request/response operations.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8c4d-130">BizTalk Web Services 发布向导显示公共接收端口。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-130">The BizTalk Web Services Publishing Wizard displays public receive ports.</span></span> <span data-ttu-id="c8c4d-131">公共接收端口是具有公用类型修饰符的端口类型。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-131">Public receive ports are port types with a public type modifier.</span></span> <span data-ttu-id="c8c4d-132">可以将只有公有端口发布为 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-132">You can publish only public ports as a Web service.</span></span> <span data-ttu-id="c8c4d-133">默认端口类型是“内部”。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-133">The default port type is internal.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c8c4d-134">如果在接收端口已定义为单向，则 Web 方法响应类型为**void**和到 Web 客户端返回任何信息。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-134">If your receive port is defined as one-way, the Web method response type is **void** and no information is returned to the Web client.</span></span> <span data-ttu-id="c8c4d-135">由 SOAP 适配器或业务流程引发的异常不会返回到 Web 客户端。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-135">Exceptions thrown by the SOAP adapter or an orchestration are not returned to the Web client.</span></span>  
  
## <a name="web-services-naming-conventions-for-published-orchestrations"></a><span data-ttu-id="c8c4d-136">已发布业务流程的 Web Services 命名约定</span><span class="sxs-lookup"><span data-stu-id="c8c4d-136">Web services naming conventions for published orchestrations</span></span>  
 <span data-ttu-id="c8c4d-137">BizTalk Web Services 发布向导生成 Web 服务 (.asmx) 文件名称基于业务流程命名空间，然后是下划线 (*) 后, 跟类型名称，然后是下划线 (\\*)，并后跟的接收端口的名称。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-137">The BizTalk Web Services Publishing Wizard generates Web service (.asmx) file names based on the orchestrations namespace, followed by an underscore (*), followed by the type name, followed by an underscore (\\*), and followed by the name of the receive port.</span></span> <span data-ttu-id="c8c4d-138">下划线 (\_) 替换任何包含句点的部分。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-138">An underscore (\_) replaces any of the parts that contain periods.</span></span> <span data-ttu-id="c8c4d-139">Web 服务的名称始终具有附加的端口名称。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-139">The name of the Web service always has the port name appended.</span></span>  
  
 <span data-ttu-id="c8c4d-140">下表显示了如何为 BizTalk Web Services 发布向导生成 Web 服务名称。</span><span class="sxs-lookup"><span data-stu-id="c8c4d-140">The following table shows how the BizTalk Web Services Publishing Wizard generates Web service names.</span></span>  
  
|<span data-ttu-id="c8c4d-141">使用 Web 端口的业务流程</span><span class="sxs-lookup"><span data-stu-id="c8c4d-141">Orchestration(s) with Web port(s)</span></span>|<span data-ttu-id="c8c4d-142">生成的 Web 服务名称</span><span class="sxs-lookup"><span data-stu-id="c8c4d-142">Generated Web service name</span></span>|  
|-------------------------------------------|--------------------------------|  
|<span data-ttu-id="c8c4d-143">只有一个 Web 端口的一个业务流程</span><span class="sxs-lookup"><span data-stu-id="c8c4d-143">One orchestration with one Web port</span></span>|<span data-ttu-id="c8c4d-144">orchestration1_port1.asmx</span><span class="sxs-lookup"><span data-stu-id="c8c4d-144">orchestration1_port1.asmx</span></span>|  
|<span data-ttu-id="c8c4d-145">具有两个 Web 端口的一个业务流程</span><span class="sxs-lookup"><span data-stu-id="c8c4d-145">One orchestration with two Web ports</span></span>|<span data-ttu-id="c8c4d-146">orchestration1_port1.asmx 和 orchestration1_port2.asmx</span><span class="sxs-lookup"><span data-stu-id="c8c4d-146">orchestration1_port1.asmx and orchestration1_port2.asmx</span></span>|  
|<span data-ttu-id="c8c4d-147">两个业务流程使用一个 Web 端口每个</span><span class="sxs-lookup"><span data-stu-id="c8c4d-147">Two orchestrations with one Web port each</span></span>|<span data-ttu-id="c8c4d-148">orchestration1_port1.asmx 和 orchestration2_port2.asmx</span><span class="sxs-lookup"><span data-stu-id="c8c4d-148">orchestration1_port1.asmx and orchestration2_port2.asmx</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c8c4d-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8c4d-149">See Also</span></span>  
 <span data-ttu-id="c8c4d-150">[业务流程发布为 Web 服务](../core/publishing-an-orchestration-as-a-web-service.md) </span><span class="sxs-lookup"><span data-stu-id="c8c4d-150">[Publishing an Orchestration as a Web Service](../core/publishing-an-orchestration-as-a-web-service.md) </span></span>  
 [<span data-ttu-id="c8c4d-151">如何使用 BizTalk Web Services 发布向导业务流程发布为 Web 服务</span><span class="sxs-lookup"><span data-stu-id="c8c4d-151">How to Use the BizTalk Web Services Publishing Wizard to Publish an Orchestration as a Web Service</span></span>](../core/publish-orchestration-as-web-service--biztalk-web-services-publishing-wizard.md)