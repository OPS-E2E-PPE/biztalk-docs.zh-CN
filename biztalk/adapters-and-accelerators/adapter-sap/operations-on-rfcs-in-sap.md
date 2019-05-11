---
title: 在 SAP 中的 Rfc 的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
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
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5370ec67511088b070568218320e0d015cfd25f5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373169"
---
# <a name="operations-on-rfcs-in-sap"></a><span data-ttu-id="39994-102">在 SAP 中的 Rfc 的操作</span><span class="sxs-lookup"><span data-stu-id="39994-102">Operations on RFCs in SAP</span></span>
<span data-ttu-id="39994-103">可以使用[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]作为 RFC 客户端和 RFC 服务器。</span><span class="sxs-lookup"><span data-stu-id="39994-103">You can use the[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] both as an RFC client and as an RFC server.</span></span> <span data-ttu-id="39994-104">在 RFC 客户端方案中，你的应用程序调用 Rfc SAP 系统上通过在调用 RFC 操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="39994-104">In RFC client scenarios, your application invokes RFCs on the SAP system by invoking RFC operations on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="39994-105">在 RFC 服务器方案中将 SAP 系统调用 Rfc 上[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]，其中，反过来，以在应用程序上操作的方式调用 RFC。</span><span class="sxs-lookup"><span data-stu-id="39994-105">In RFC server scenarios the SAP system invokes RFCs on the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)], which, in turn, invokes the RFC as an operation on your application.</span></span>  
  
## <a name="rfc-operations"></a><span data-ttu-id="39994-106">RFC 操作</span><span class="sxs-lookup"><span data-stu-id="39994-106">RFC Operations</span></span>  
 <span data-ttu-id="39994-107">Rfc 按名称显示为通过的 RFC 的元数据类别节点下的操作[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="39994-107">RFCs are surfaced by name as operations under the RFC metadata category node by the [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="39994-108">(您可以浏览或搜索在 Rfc **RFC**当你使用的节点[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]或[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。)</span><span class="sxs-lookup"><span data-stu-id="39994-108">(You can browse or search for RFCs under the **RFC** node when you use the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] or the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].)</span></span>  
  
 <span data-ttu-id="39994-109">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] ，可能会出现，它可以从 SAP 系统中检索元数据这些 Rfc。</span><span class="sxs-lookup"><span data-stu-id="39994-109">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can surface only those RFCs for which it can retrieve metadata from the SAP system.</span></span> <span data-ttu-id="39994-110">适配器使用 RFC SDK 来检索此元数据，因此它不能呈现包含 RFC SDK 不支持的数据类型的参数的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="39994-110">The adapter uses the RFC SDK to retrieve this metadata, so it cannot surface RFCs that contain parameters with data types that are not supported by the RFC SDK.</span></span> <span data-ttu-id="39994-111">例如，适配器不能出现包含 ITAB II 类型结构或表的 Rfc。</span><span class="sxs-lookup"><span data-stu-id="39994-111">For example, the adapter cannot surface RFCs that contain ITAB II type structures or tables.</span></span>  
  
 <span data-ttu-id="39994-112">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Rfc 上支持以下各项：</span><span class="sxs-lookup"><span data-stu-id="39994-112">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] supports the following on RFCs:</span></span>  
  
- <span data-ttu-id="39994-113">导入参数</span><span class="sxs-lookup"><span data-stu-id="39994-113">IMPORT parameters</span></span>  
  
- <span data-ttu-id="39994-114">导出参数</span><span class="sxs-lookup"><span data-stu-id="39994-114">EXPORT parameters</span></span>  
  
- <span data-ttu-id="39994-115">更改参数</span><span class="sxs-lookup"><span data-stu-id="39994-115">CHANGING parameters</span></span>  
  
  <span data-ttu-id="39994-116">有关消息结构和适配器为 Rfc 使用的 SOAP 操作的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="39994-116">For more information about the message structures and SOAP actions used for RFCs by the adapter, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
## <a name="invoking-rfcs-on-an-sap-system"></a><span data-ttu-id="39994-117">SAP 系统上调用 Rfc</span><span class="sxs-lookup"><span data-stu-id="39994-117">Invoking RFCs on an SAP System</span></span>  
 <span data-ttu-id="39994-118">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] Rfc 显示为单独的操作，SAP 系统上采用 RFC 的名称。</span><span class="sxs-lookup"><span data-stu-id="39994-118">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] surfaces RFCs as individual operations that take the name of the RFC on the SAP system.</span></span> <span data-ttu-id="39994-119">若要调用 RFC SAP 系统上的，您调用在适配器上适当命名的 RFC 操作。</span><span class="sxs-lookup"><span data-stu-id="39994-119">To invoke an RFC on the SAP system, you invoke the appropriately named RFC operation on the adapter.</span></span>  
  
 <span data-ttu-id="39994-120">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="39994-120">For more information about:</span></span>  
  
-   <span data-ttu-id="39994-121">调用 RFC 使用 BizTalk Server 中，请参阅[通过使用 BizTalk Server 调用 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="39994-121">Invoking an RFC using BizTalk Server, see [Invoke RFCs by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="39994-122">调用 RFC 使用 WCF 服务模型，请参阅[调用中使用 WCF 服务模型的 SAP 的 Rfc](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="39994-122">Invoking an RFC using the WCF service model, see [Invoke RFCs in SAP using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/invoke-rfcs-in-sap-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="39994-123">调用 RFC 使用 WCF 通道模型，请参阅[通过使用 WCF 通道模型 SAP 系统的调用操作](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="39994-123">Invoking an RFC using the WCF channel model, see [Invoke Operations on the SAP System by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/invoke-operations-on-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="receiving-inbound-rfc-calls-from-an-sap-system"></a><span data-ttu-id="39994-124">接收来自 SAP 系统的入站的 RFC 调用</span><span class="sxs-lookup"><span data-stu-id="39994-124">Receiving Inbound RFC Calls from an SAP System</span></span>  
 <span data-ttu-id="39994-125">很可能适用于 SAP 充当客户端并调用外部 RFC 服务器上的函数模块。</span><span class="sxs-lookup"><span data-stu-id="39994-125">It is possible for SAP to act as a client and invoke function modules on an external RFC server.</span></span> <span data-ttu-id="39994-126">此功能可以：</span><span class="sxs-lookup"><span data-stu-id="39994-126">This functionality enables:</span></span>  
  
- <span data-ttu-id="39994-127">若要将通知推送到外部系统，而无需外部系统无需通知通过调用 Rfc 连续轮询 SAP 的 SAP。</span><span class="sxs-lookup"><span data-stu-id="39994-127">SAP to push notifications to external systems without the external systems having to continuously poll SAP for notifications by calling RFCs.</span></span>  
  
- <span data-ttu-id="39994-128">SAP 系统外部的业务逻辑的实现。</span><span class="sxs-lookup"><span data-stu-id="39994-128">The implementation of business logic outside the SAP system.</span></span> <span data-ttu-id="39994-129">然后，SAP 系统可以对 RFC 服务器调用外部程序。</span><span class="sxs-lookup"><span data-stu-id="39994-129">The SAP system can then call the external program on the RFC server.</span></span>  
  
  <span data-ttu-id="39994-130">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]可以充当一个 RFC 服务器用于从 SAP 系统接收此类的入站的 RFC 调用。</span><span class="sxs-lookup"><span data-stu-id="39994-130">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can act as an RFC server to receive such inbound RFC calls from the SAP system.</span></span> <span data-ttu-id="39994-131">当适配器接收来自 SAP RFC 调用时，它调用 RFC 操作对应用程序。</span><span class="sxs-lookup"><span data-stu-id="39994-131">When the adapter receives an RFC call from SAP, it invokes that RFC operation on your application.</span></span>  
  
  <span data-ttu-id="39994-132">为使适配器为 RFC 服务器执行：</span><span class="sxs-lookup"><span data-stu-id="39994-132">For the adapter to perform as an RFC server:</span></span>  
  
- <span data-ttu-id="39994-133">RFC 必须声明上的 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="39994-133">The RFC must be declared on the SAP system.</span></span> <span data-ttu-id="39994-134">这是因此适配器可以检索描述从 SAP 系统的 RFC 的元数据。</span><span class="sxs-lookup"><span data-stu-id="39994-134">This is so the adapter can retrieve metadata that describes the RFC from the SAP system.</span></span> <span data-ttu-id="39994-135">在你的应用程序中实际实现 RFC。</span><span class="sxs-lookup"><span data-stu-id="39994-135">The RFC is actually implemented in your application.</span></span>  
  
- <span data-ttu-id="39994-136">适配器必须注册 SAP 网关上的 RFC 目标。</span><span class="sxs-lookup"><span data-stu-id="39994-136">The adapter must register with an RFC destination on an SAP gateway.</span></span> <span data-ttu-id="39994-137">注册基于逻辑名称称为程序 id。</span><span class="sxs-lookup"><span data-stu-id="39994-137">The registration is based on a logical name called a program ID.</span></span> <span data-ttu-id="39994-138">提供的连接 URI 指定的程序 ID，SAP 网关和 SAP 此注册的服务器中的参数。</span><span class="sxs-lookup"><span data-stu-id="39994-138">You supply parameters in the connection URI to specify the PROGRAM ID, SAP gateway, and SAP server for this registration.</span></span>  
  
  <span data-ttu-id="39994-139">下面的示例显示了调用通过程序 ID，MYDEST RFC 所需的 ABAP 代码。</span><span class="sxs-lookup"><span data-stu-id="39994-139">The following example shows the ABAP code required to invoke an RFC through the PROGRAM ID, MYDEST.</span></span>  
  
```  
CALL FUNCTION ‘ABC’ DESTINATION ‘MYDEST’  
```  
  
 <span data-ttu-id="39994-140">有关详细信息：</span><span class="sxs-lookup"><span data-stu-id="39994-140">For more information about:</span></span>  
  
-   <span data-ttu-id="39994-141">接收 RFC 服务器调用使用 BizTalk Server 中，请参阅[通过使用 BizTalk Server 接收的入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md)。</span><span class="sxs-lookup"><span data-stu-id="39994-141">Receiving an RFC server call using BizTalk Server, see [Receive Inbound RFC Calls by Using BizTalk Server](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-from-sap-using-biztalk-server.md).</span></span>  
  
-   <span data-ttu-id="39994-142">接收 RFC 服务器调用使用 WCF 服务模型，请参阅[SAP 使用 WCF 服务模型中接收的入站 RFC 调用](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md)。</span><span class="sxs-lookup"><span data-stu-id="39994-142">Receiving an RFC server call using the WCF service model, see [Receive  Inbound RFC Calls in SAP using the WCF Service Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-rfc-calls-in-sap-using-the-wcf-service-model.md).</span></span>  
  
-   <span data-ttu-id="39994-143">接收 RFC 服务器调用使用 WCF 通道模型，请参阅[接收从使用 WCF 通道模型 SAP 系统的入站操作](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md)。</span><span class="sxs-lookup"><span data-stu-id="39994-143">Receiving an RFC server call using the WCF channel model, see [Receive Inbound Operations from the SAP System by Using the WCF Channel Model](../../adapters-and-accelerators/adapter-sap/receive-inbound-operations-from-the-sap-system-using-the-wcf-channel-model.md).</span></span>  
  
## <a name="special-rfc-operations"></a><span data-ttu-id="39994-144">特殊 RFC 操作</span><span class="sxs-lookup"><span data-stu-id="39994-144">Special RFC Operations</span></span>  
 <span data-ttu-id="39994-145">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]还可以执行某些特殊的 RFC 操作上的 SAP 系统。</span><span class="sxs-lookup"><span data-stu-id="39994-145">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] can also perform certain special RFC operations on the SAP system.</span></span> <span data-ttu-id="39994-146">一个此类操作，RfcGetAttributes。</span><span class="sxs-lookup"><span data-stu-id="39994-146">One such operation is RfcGetAttributes.</span></span>  
  
- <span data-ttu-id="39994-147">**RfcGetAttributes**。</span><span class="sxs-lookup"><span data-stu-id="39994-147">**RfcGetAttributes**.</span></span> <span data-ttu-id="39994-148">[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]此操作用于获取有关 RFC 连接参数，例如系统 ID、 合作伙伴的代码页和语言的信息。</span><span class="sxs-lookup"><span data-stu-id="39994-148">The [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)] uses this operation to get information about the RFC connection parameters such as system ID, partner code page, and language.</span></span> <span data-ttu-id="39994-149">此操作不可用的情况下**RFC**节点时使用[!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]和[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="39994-149">This operation is available under the **RFC** node when using the [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] and [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)].</span></span>  
  
  <span data-ttu-id="39994-150">有关消息结构和 SOAP 操作的调用上的 SAP 系统的某个 RfcGetAttributes 操作的详细信息，请参阅[RFC 操作的消息架构](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="39994-150">For more information about message structure and SOAP action for invoking an RfcGetAttributes operation on the SAP system, see [Message Schemas for RFC Operations](../../adapters-and-accelerators/adapter-sap/message-schemas-for-rfc-operations.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39994-151">请参阅</span><span class="sxs-lookup"><span data-stu-id="39994-151">See Also</span></span>  
 <span data-ttu-id="39994-152">[哪些操作可以是执行使用适配器？](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span><span class="sxs-lookup"><span data-stu-id="39994-152">[What Operations Can be Performed Using the Adapter?](https://msdn.microsoft.com/library/cc185219(v=bts.10).aspx)</span></span>