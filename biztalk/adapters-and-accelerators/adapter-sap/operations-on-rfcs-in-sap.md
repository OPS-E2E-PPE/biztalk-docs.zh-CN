---
title: "SAP 中的 Rfc 上的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- adapters, operations on RFCs
- adapters, operations on IDOCs
- RFC, receiving inbound RFC calls from an SAP system
- RFCs, invoking RFCs on an SAP system
- adapters, operations on BAPIs
- RFC client
- adapters, operations on tRFCs
- RFC server
ms.assetid: ca1b7b00-a9cf-41bc-b87c-2e7ce8cff65c
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cd4ebbb33e9f9791589a3ef271412c8ae20090f5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-rfcs-in-sap"></a><span data-ttu-id="1ef08-102">SAP 中的 Rfc 上的操作</span><span class="sxs-lookup"><span data-stu-id="1ef08-102">Operations on RFCs in SAP</span></span>
<span data-ttu-id="1ef08-103">你可以使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]同时作为 RFC 客户端和 RFC 服务器。</span><span class="sxs-lookup"><span data-stu-id="1ef08-103">You can use the[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] both as an RFC client and as an RFC server.</span></span> <span data-ttu-id="1ef08-104">在 RFC 客户端的情况下，你的应用程序时，将调用 Rfc SAP 系统上通过上调用 RFC 操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1ef08-104">In RFC client scenarios, your application invokes RFCs on the SAP system by invoking RFC operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="1ef08-105">在 RFC 服务器方案中 SAP 系统时，将调用 Rfc 上[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，这样，就反过来，作为对你的应用程序的操作可调用 RFC。</span><span class="sxs-lookup"><span data-stu-id="1ef08-105">In RFC server scenarios the SAP system invokes RFCs on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], which, in turn, invokes the RFC as an operation on your application.</span></span>  
  
## <a name="rfc-operations"></a><span data-ttu-id="1ef08-106">RFC 操作</span><span class="sxs-lookup"><span data-stu-id="1ef08-106">RFC Operations</span></span>  
 <span data-ttu-id="1ef08-107">Rfc 作为 RFC 元数据类别节点下的操作进行展示按名称[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1ef08-107">RFCs are surfaced by name as operations under the RFC metadata category node by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="1ef08-108">(你可以浏览或搜索在 Rfc **RFC**节点使用时[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。)</span><span class="sxs-lookup"><span data-stu-id="1ef08-108">(You can browse or search for RFCs under the **RFC** node when you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)</span></span>  
  
 <span data-ttu-id="1ef08-109">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可能显示为其它能够从 SAP 系统中检索元数据这些 Rfc。</span><span class="sxs-lookup"><span data-stu-id="1ef08-109">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can surface only those RFCs for which it can retrieve metadata from the SAP system.</span></span> <span data-ttu-id="1ef08-110">适配器使用 RFC SDK 检索此元数据，因此它不能呈现包含 RFC SDK 不支持的数据类型的参数的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="1ef08-110">The adapter uses the RFC SDK to retrieve this metadata, so it cannot surface RFCs that contain parameters with data types that are not supported by the RFC SDK.</span></span> <span data-ttu-id="1ef08-111">例如，该适配器不能出现包含 ITAB II 类型结构或表的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="1ef08-111">For example, the adapter cannot surface RFCs that contain ITAB II type structures or tables.</span></span>  
  
 <span data-ttu-id="1ef08-112">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]在 Rfc 上支持以下：</span><span class="sxs-lookup"><span data-stu-id="1ef08-112">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following on RFCs:</span></span>  
  
-   <span data-ttu-id="1ef08-113">导入参数</span><span class="sxs-lookup"><span data-stu-id="1ef08-113">IMPORT parameters</span></span>  
  
-   <span data-ttu-id="1ef08-114">导出参数</span><span class="sxs-lookup"><span data-stu-id="1ef08-114">EXPORT parameters</span></span>  
  
-   <span data-ttu-id="1ef08-115">更改参数</span><span class="sxs-lookup"><span data-stu-id="1ef08-115">CHANGING parameters</span></span>  
  
 <span data-ttu-id="1ef08-116">有关消息结构和用于 Rfc 适配器的 SOAP 操作的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef08-116">For more information about the message structures and SOAP actions used for RFCs by the adapter, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
## <a name="invoking-rfcs-on-an-sap-system"></a><span data-ttu-id="1ef08-117">调用上的 SAP 系统的 Rfc</span><span class="sxs-lookup"><span data-stu-id="1ef08-117">Invoking RFCs on an SAP System</span></span>  
 <span data-ttu-id="1ef08-118">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]显示为 SAP 系统对其执行的 RFC 名称的各个操作的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="1ef08-118">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces RFCs as individual operations that take the name of the RFC on the SAP system.</span></span> <span data-ttu-id="1ef08-119">若要调用 RFC SAP 系统上的，你调用该适配器上的相应命名的 RFC 操作。</span><span class="sxs-lookup"><span data-stu-id="1ef08-119">To invoke an RFC on the SAP system, you invoke the appropriately named RFC operation on the adapter.</span></span>  
  
 <span data-ttu-id="1ef08-120">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="1ef08-120">For more information about:</span></span>  
  
-   <span data-ttu-id="1ef08-121">调用 RFC 使用 BizTalk Server 中，请参阅[使用 BizTalk server 调用 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef08-121">Invoking an RFC using BizTalk Server, see [Invoke RFCs by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="1ef08-122">调用 RFC 使用 WCF 服务模型时，请参阅[调用中使用 WCF 服务模型的 SAP 的 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef08-122">Invoking an RFC using the WCF service model, see [Invoke RFCs in SAP using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="1ef08-123">调用 RFC 使用 WCF 通道模型，请参阅[调用通过使用 WCF 通道模型 SAP 系统的操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef08-123">Invoking an RFC using the WCF channel model, see [Invoke Operations on the SAP System by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="receiving-inbound-rfc-calls-from-an-sap-system"></a><span data-ttu-id="1ef08-124">从 SAP 系统的接收入站的 RFC 调用</span><span class="sxs-lookup"><span data-stu-id="1ef08-124">Receiving Inbound RFC Calls from an SAP System</span></span>  
 <span data-ttu-id="1ef08-125">很可能适用于 SAP 充当客户端并调用外部 RFC 服务器上的函数模块。</span><span class="sxs-lookup"><span data-stu-id="1ef08-125">It is possible for SAP to act as a client and invoke function modules on an external RFC server.</span></span> <span data-ttu-id="1ef08-126">借助此功能：</span><span class="sxs-lookup"><span data-stu-id="1ef08-126">This functionality enables:</span></span>  
  
-   <span data-ttu-id="1ef08-127">SAP 以将通知推送到外部系统，而无需外部的系统无需持续轮询 SAP 通知通过调用 Rfc。</span><span class="sxs-lookup"><span data-stu-id="1ef08-127">SAP to push notifications to external systems without the external systems having to continuously poll SAP for notifications by calling RFCs.</span></span>  
  
-   <span data-ttu-id="1ef08-128">在 SAP 系统范围之外的业务逻辑的实现。</span><span class="sxs-lookup"><span data-stu-id="1ef08-128">The implementation of business logic outside the SAP system.</span></span> <span data-ttu-id="1ef08-129">然后，SAP 系统可以在 RFC 服务器上调用外部程序。</span><span class="sxs-lookup"><span data-stu-id="1ef08-129">The SAP system can then call the external program on the RFC server.</span></span>  
  
 <span data-ttu-id="1ef08-130">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以用作 RFC 服务器从 SAP 系统接收此类的入站的 RFC 调用。</span><span class="sxs-lookup"><span data-stu-id="1ef08-130">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can act as an RFC server to receive such inbound RFC calls from the SAP system.</span></span> <span data-ttu-id="1ef08-131">当适配器在 SAP 中收到的 RFC 调用时，将调用该 RFC 操作对应用程序。</span><span class="sxs-lookup"><span data-stu-id="1ef08-131">When the adapter receives an RFC call from SAP, it invokes that RFC operation on your application.</span></span>  
  
 <span data-ttu-id="1ef08-132">作为 RFC 服务器运行的适配器：</span><span class="sxs-lookup"><span data-stu-id="1ef08-132">For the adapter to perform as an RFC server:</span></span>  
  
-   <span data-ttu-id="1ef08-133">RFC 必须声明 SAP 系统上。</span><span class="sxs-lookup"><span data-stu-id="1ef08-133">The RFC must be declared on the SAP system.</span></span> <span data-ttu-id="1ef08-134">这是因此该适配器可以检索元数据描述从 SAP 系统的 RFC。</span><span class="sxs-lookup"><span data-stu-id="1ef08-134">This is so the adapter can retrieve metadata that describes the RFC from the SAP system.</span></span> <span data-ttu-id="1ef08-135">RFC 实际是在你的应用程序中实现的。</span><span class="sxs-lookup"><span data-stu-id="1ef08-135">The RFC is actually implemented in your application.</span></span>  
  
-   <span data-ttu-id="1ef08-136">适配器必须注册上的 SAP 网关的 RFC 目标。</span><span class="sxs-lookup"><span data-stu-id="1ef08-136">The adapter must register with an RFC destination on an SAP gateway.</span></span> <span data-ttu-id="1ef08-137">注册基于逻辑名称称为程序 id。</span><span class="sxs-lookup"><span data-stu-id="1ef08-137">The registration is based on a logical name called a program ID.</span></span> <span data-ttu-id="1ef08-138">提供连接 URI 指定的程序 ID，SAP 网关和 SAP 此注册的服务器中的参数。</span><span class="sxs-lookup"><span data-stu-id="1ef08-138">You supply parameters in the connection URI to specify the PROGRAM ID, SAP gateway, and SAP server for this registration.</span></span>  
  
 <span data-ttu-id="1ef08-139">下面的示例显示调用通过程序 ID，MYDEST RFC 所必需的 ABAP 代码。</span><span class="sxs-lookup"><span data-stu-id="1ef08-139">The following example shows the ABAP code required to invoke an RFC through the PROGRAM ID, MYDEST.</span></span>  
  
```  
CALL FUNCTION ‘ABC’ DESTINATION ‘MYDEST’  
```  
  
 <span data-ttu-id="1ef08-140">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="1ef08-140">For more information about:</span></span>  
  
-   <span data-ttu-id="1ef08-141">接收的 RFC 服务器调用使用 BizTalk Server 中，请参阅[使用 BizTalk server 接收入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef08-141">Receiving an RFC server call using BizTalk Server, see [Receive Inbound RFC Calls by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="1ef08-142">接收的 RFC 服务器调用使用 WCF 服务模型时，请参阅[SAP 使用 WCF 服务模型中接收入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef08-142">Receiving an RFC server call using the WCF service model, see [Receive  Inbound RFC Calls in SAP using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="1ef08-143">接收的 RFC 服务器调用使用 WCF 通道模型，请参阅[接收从使用 WCF 通道模型 SAP 系统的入站操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef08-143">Receiving an RFC server call using the WCF channel model, see [Receive Inbound Operations from the SAP System by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="special-rfc-operations"></a><span data-ttu-id="1ef08-144">特殊 RFC 操作</span><span class="sxs-lookup"><span data-stu-id="1ef08-144">Special RFC Operations</span></span>  
 <span data-ttu-id="1ef08-145">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还可以执行某些特殊的 RFC 操作 SAP 系统上。</span><span class="sxs-lookup"><span data-stu-id="1ef08-145">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can also perform certain special RFC operations on the SAP system.</span></span> <span data-ttu-id="1ef08-146">此类的一个操作是 RfcGetAttributes。</span><span class="sxs-lookup"><span data-stu-id="1ef08-146">One such operation is RfcGetAttributes.</span></span>  
  
-   <span data-ttu-id="1ef08-147">**RfcGetAttributes**。</span><span class="sxs-lookup"><span data-stu-id="1ef08-147">**RfcGetAttributes**.</span></span> <span data-ttu-id="1ef08-148">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]使用此操作以获取有关 RFC 连接参数，如系统 ID、 合作伙伴代码页和语言的信息。</span><span class="sxs-lookup"><span data-stu-id="1ef08-148">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses this operation to get information about the RFC connection parameters such as system ID, partner code page, and language.</span></span> <span data-ttu-id="1ef08-149">此操作才可用下**RFC**节点时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1ef08-149">This operation is available under the **RFC** node when using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
 <span data-ttu-id="1ef08-150">有关消息结构和调用对 SAP 系统的 RfcGetAttributes 操作的 SOAP 操作的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="1ef08-150">For more information about message structure and SOAP action for invoking an RfcGetAttributes operation on the SAP system, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef08-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ef08-151">See Also</span></span>  
 <span data-ttu-id="1ef08-152">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="1ef08-152">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>