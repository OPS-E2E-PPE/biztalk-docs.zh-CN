---
title: Siebel 适配器支持哪些操作 |Microsoft Docs
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
ms.openlocfilehash: f3f080cedb74210d02806681b6c9e20656d3d09e
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37004774"
---
# <a name="what-operations-are-supported-by-the-siebel-adapter"></a><span data-ttu-id="98ba0-102">Siebel 适配器支持哪些操作</span><span class="sxs-lookup"><span data-stu-id="98ba0-102">What operations are supported by the Siebel adapter</span></span>
<span data-ttu-id="98ba0-103">适配器客户端可以通过以下任一方法来执行 Siebel 系统的操作：</span><span class="sxs-lookup"><span data-stu-id="98ba0-103">Adapter clients can perform operations on the Siebel system by either:</span></span>  
  
- <span data-ttu-id="98ba0-104">创建 BizTalk 项目。</span><span class="sxs-lookup"><span data-stu-id="98ba0-104">Creating BizTalk projects.</span></span>  
  
- <span data-ttu-id="98ba0-105">使用 WCF 通道模型。</span><span class="sxs-lookup"><span data-stu-id="98ba0-105">Using the WCF channel model.</span></span>  
  
- <span data-ttu-id="98ba0-106">使用 WCF 服务模型。</span><span class="sxs-lookup"><span data-stu-id="98ba0-106">Using the WCF service model.</span></span>  
  
  <span data-ttu-id="98ba0-107">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]公开应用程序可以调用在其上并且可以反过来，调用应用程序上的操作。</span><span class="sxs-lookup"><span data-stu-id="98ba0-107">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] exposes operations that applications can invoke on it and that it can, in turn, invoke on applications.</span></span> <span data-ttu-id="98ba0-108">通过通道发送 SOAP 消息来调用这些操作。</span><span class="sxs-lookup"><span data-stu-id="98ba0-108">These operations are invoked by sending SOAP messages over a channel.</span></span> <span data-ttu-id="98ba0-109">如果响应是必需的它通过同一通道返回 SOAP 消息中。</span><span class="sxs-lookup"><span data-stu-id="98ba0-109">If a response is required, it is returned in a SOAP message over the same channel.</span></span> <span data-ttu-id="98ba0-110">有关消息结构和与每个操作关联的 SOAP 操作的信息，请参阅[消息和用于 Siebel eBusiness 应用程序的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)。</span><span class="sxs-lookup"><span data-stu-id="98ba0-110">For information about the message structure and the SOAP action associated with each operation, see [Messages and Message Schemas for BizTalk Adapter for Siebel eBusiness Applications](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md).</span></span>  
  
  <span data-ttu-id="98ba0-111">本部分提供有关 Siebel 系统使用支持的操作信息[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="98ba0-111">This section provides information about the operations supported on the Siebel system using the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98ba0-112">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不支持从 Siebel 系统接收的入站的调用。</span><span class="sxs-lookup"><span data-stu-id="98ba0-112">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not support receiving inbound calls from a Siebel system.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98ba0-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="98ba0-113">In This Section</span></span>  
  
-   [<span data-ttu-id="98ba0-114">在 Siebel 业务组件上的操作</span><span class="sxs-lookup"><span data-stu-id="98ba0-114">Operations on Business Components in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/operations-on-business-components-in-siebel.md)  
  
-   [<span data-ttu-id="98ba0-115">在 Siebel 业务服务上的操作</span><span class="sxs-lookup"><span data-stu-id="98ba0-115">Operations on Business Services in Siebel</span></span>](../../adapters-and-accelerators/adapter-siebel/operations-on-business-services-in-siebel.md)  
  
## <a name="see-also"></a><span data-ttu-id="98ba0-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="98ba0-116">See Also</span></span>  
 [<span data-ttu-id="98ba0-117">用于 Siebel eBusiness 应用程序的 BizTalk 适配器概述</span><span class="sxs-lookup"><span data-stu-id="98ba0-117">Overview of BizTalk Adapter for Siebel eBusiness Applications</span></span>](../../adapters-and-accelerators/adapter-siebel/overview-of-biztalk-adapter-for-siebel-ebusiness-applications.md)