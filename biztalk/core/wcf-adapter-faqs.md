---
title: "WCF 适配器常见问题 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ce5b2889-0a90-4fd0-8069-03e5636b61b6
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4aa110a5d3e7d983df7a672f71ac762c01fb0d09
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-adapter-faqs"></a><span data-ttu-id="98bd1-102">WCF 适配器常见问题解答</span><span class="sxs-lookup"><span data-stu-id="98bd1-102">WCF Adapter FAQs</span></span>
> [!NOTE]
>  <span data-ttu-id="98bd1-103">若要下载一份这些常见问题，请转到[http://go.microsoft.com/fwlink/?LinkId=144765](http://go.microsoft.com/fwlink/?LinkId=144765)。</span><span class="sxs-lookup"><span data-stu-id="98bd1-103">To download a copy of these FAQs, go to the [http://go.microsoft.com/fwlink/?LinkId=144765](http://go.microsoft.com/fwlink/?LinkId=144765).</span></span>  
>   
>  <span data-ttu-id="98bd1-104">有关适配器的详细信息，请转到[BizTalk Server 中的适配器](http://go.microsoft.com/fwlink/?LinkId=196669)MSDN 上的页。</span><span class="sxs-lookup"><span data-stu-id="98bd1-104">For more information about adapters, go to the [Adapters in BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=196669) page on MSDN.</span></span>  
  
 <span data-ttu-id="98bd1-105">本部分包括下列 Windows Communication Foundation (WCF) 适配器常见问题：</span><span class="sxs-lookup"><span data-stu-id="98bd1-105">The following Windows Communication Foundation (WCF) adapter FAQs are included in this section:</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="98bd1-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="98bd1-106">In This Section</span></span>  
  
-   <span data-ttu-id="98bd1-107">[WCF 适配器常见问题： 常规概念](../core/wcf-adapter-faq-general-conceptual.md)-常见问题的一般性质以及为概念性 WCF 适配器主题。</span><span class="sxs-lookup"><span data-stu-id="98bd1-107">[WCF Adapter FAQ: General Conceptual](../core/wcf-adapter-faq-general-conceptual.md) - Frequently asked questions of a general nature as well as conceptual WCF adapter topics.</span></span>  
  
-   <span data-ttu-id="98bd1-108">[WCF 适配器常见问题： 消息流和映射](../core/wcf-adapter-faq-message-flow-and-mapping.md)-消息入和移出 BizTalk Server 使用 WCF 适配器的流动方式有关的常见问题。</span><span class="sxs-lookup"><span data-stu-id="98bd1-108">[WCF Adapter FAQ: Message Flow and Mapping](../core/wcf-adapter-faq-message-flow-and-mapping.md) - Frequently asked questions about how a message flows in and out of BizTalk Server using the WCF adapters.</span></span>  
  
-   <span data-ttu-id="98bd1-109">[WCF 适配器常见问题： 开发库](../core/wcf-adapter-faq-development-libraries.md)-开发 BizTalk 适配器时要使用哪些库有关的常见问题。</span><span class="sxs-lookup"><span data-stu-id="98bd1-109">[WCF Adapter FAQ: Development Libraries](../core/wcf-adapter-faq-development-libraries.md) - Frequently asked questions about which libraries to use when developing BizTalk adapters.</span></span>  
  
-   <span data-ttu-id="98bd1-110">[WCF 适配器常见问题： 使用 WCF 服务](../core/wcf-adapter-faq-using-wcf-services.md)-有关如何访问 WCF 服务、 自定义绑定和自定义行为与 WCF 适配器的常见问题。</span><span class="sxs-lookup"><span data-stu-id="98bd1-110">[WCF Adapter FAQ: Using WCF Services](../core/wcf-adapter-faq-using-wcf-services.md) - Frequently asked questions about how to access WCF services, custom bindings, and custom behaviors with the WCF adapters.</span></span>  
  
-   <span data-ttu-id="98bd1-111">[WCF 适配器常见问题： WCF 终结点](../core/wcf-adapter-faq-wcf-endpoints.md)的服务终结点、 元数据，以及如何发布使用 WCF 适配器的 WCF 终结点有关的常见问题。</span><span class="sxs-lookup"><span data-stu-id="98bd1-111">[WCF Adapter FAQ: WCF Endpoints](../core/wcf-adapter-faq-wcf-endpoints.md) - Frequently asked questions about service endpoints, metadata, and how to publish WCF endpoints with the WCF adapters.</span></span>  
  
-   <span data-ttu-id="98bd1-112">[WCF 适配器常见问题： 服务体系结构](../core/wcf-adapter-faq-service-architecture.md)-有关如何选择 BizTalk 管道或 WCF 行为，并要选择的编码类型的常见问题。</span><span class="sxs-lookup"><span data-stu-id="98bd1-112">[WCF Adapter FAQ: Service Architecture](../core/wcf-adapter-faq-service-architecture.md) - Frequently asked questions about how to choose a BizTalk pipeline or a WCF behavior, and the types of encoding to select.</span></span>  
  
-   <span data-ttu-id="98bd1-113">[WCF 适配器常见问题： WCF 错误处理](../core/wcf-adapter-faq-wcf-error-handling.md)-有关如何处理 WCF 适配器的过程中处理 SOAP 错误和错误的常见问题。</span><span class="sxs-lookup"><span data-stu-id="98bd1-113">[WCF Adapter FAQ: WCF Error Handling](../core/wcf-adapter-faq-wcf-error-handling.md) - Frequently asked questions about how to handle SOAP faults and errors during processing of the WCF adapters.</span></span>