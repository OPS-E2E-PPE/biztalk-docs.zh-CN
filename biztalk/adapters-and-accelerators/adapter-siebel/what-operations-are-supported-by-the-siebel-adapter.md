---
title: Siebel 适配器支持哪些操作 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, performing by using the adapter
ms.assetid: 800cf44b-357f-4850-8878-f49ceb549adf
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40bfb247ff0f3af2abeec584c5fd079f392cd18e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="what-operations-are-supported-by-the-siebel-adapter"></a><span data-ttu-id="ab467-102">Siebel 适配器支持何种操作</span><span class="sxs-lookup"><span data-stu-id="ab467-102">What operations are supported by the Siebel adapter</span></span>
<span data-ttu-id="ab467-103">适配器客户端可以通过以下任一方法来执行 Siebel 系统上的操作：</span><span class="sxs-lookup"><span data-stu-id="ab467-103">Adapter clients can perform operations on the Siebel system by either:</span></span>  
  
-   <span data-ttu-id="ab467-104">创建 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="ab467-104">Creating BizTalk projects.</span></span>  
  
-   <span data-ttu-id="ab467-105">使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="ab467-105">Using the WCF channel model.</span></span>  
  
-   <span data-ttu-id="ab467-106">使用 WCF 服务模型。</span><span class="sxs-lookup"><span data-stu-id="ab467-106">Using the WCF service model.</span></span>  
  
 <span data-ttu-id="ab467-107">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开应用程序可以调用它并且它可以反过来，调用应用程序的操作。</span><span class="sxs-lookup"><span data-stu-id="ab467-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="ab467-108">这些操作都是通过在通道上发送 SOAP 消息中调用。</span><span class="sxs-lookup"><span data-stu-id="ab467-108">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="ab467-109">如果需要响应，它将通过相同的通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="ab467-109">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="ab467-110">有关消息结构和每个操作与关联的 SOAP 操作的信息，请参阅[消息和消息架构用于 Siebel eBusiness Applications 的 BizTalk Adapter](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="ab467-110">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span></span>  
  
 <span data-ttu-id="ab467-111">本部分提供有关 Siebel 系统使用支持的操作的信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ab467-111">This section provides information about the operations supported on the Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ab467-112">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持从 Siebel 系统接收的入站的调用。</span><span class="sxs-lookup"><span data-stu-id="ab467-112">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not support receiving inbound calls from a Siebel system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ab467-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="ab467-113">In This Section</span></span>  
  
-   [<span data-ttu-id="ab467-114">在 Siebel 的业务组件上的操作</span><span class="sxs-lookup"><span data-stu-id="ab467-114">Operations on Business Components in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)  
  
-   [<span data-ttu-id="ab467-115">对 Siebel 中的业务服务的操作</span><span class="sxs-lookup"><span data-stu-id="ab467-115">Operations on Business Services in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/operations-on-business-services-in-siebel.md)  
  
## <a name="see-also"></a><span data-ttu-id="ab467-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ab467-116">See Also</span></span>  
 [<span data-ttu-id="ab467-117">为 Siebel eBusiness 应用程序的 BizTalk Adapter 概述</span><span class="sxs-lookup"><span data-stu-id="ab467-117">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)