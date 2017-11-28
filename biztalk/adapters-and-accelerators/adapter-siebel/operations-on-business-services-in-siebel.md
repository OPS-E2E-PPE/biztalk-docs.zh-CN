---
title: "对 Siebel 中的业务服务的操作 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- operations, on business services
- business services, operations on
ms.assetid: 29a1a88c-8c7b-46f1-8faf-49ddd32ba2f0
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a1ffd133d76b1f8cae3f1732e48f817fe4fb26b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="operations-on-business-services-in-siebel"></a><span data-ttu-id="eb7fc-102">对 Siebel 中的业务服务的操作</span><span class="sxs-lookup"><span data-stu-id="eb7fc-102">Operations on Business Services in Siebel</span></span>
<span data-ttu-id="eb7fc-103">Siebel 业务服务是可以在 Siebel 中直接调用的业务方法的集合。</span><span class="sxs-lookup"><span data-stu-id="eb7fc-103">A Siebel business service is a collection of business methods that can be directly invoked in Siebel.</span></span> <span data-ttu-id="eb7fc-104">业务组件和业务对象关联到特定的数据和 Siebel 中的表，而业务服务调用的对象执行特定任务。</span><span class="sxs-lookup"><span data-stu-id="eb7fc-104">Whereas business components and business objects are associated to specific data and tables in Siebel, business services invoke the objects to perform specific tasks.</span></span>  
  
 <span data-ttu-id="eb7fc-105">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]呈现业务服务方法，因为操作名称和支持 IN、 OUT 和 INOUT 参数。</span><span class="sxs-lookup"><span data-stu-id="eb7fc-105">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the business service methods as operation names and supports IN, OUT, and INOUT parameters.</span></span> <span data-ttu-id="eb7fc-106">例如，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]曲面**ATPRunCheck**作为操作的方法。</span><span class="sxs-lookup"><span data-stu-id="eb7fc-106">For example, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the **ATPRunCheck** method as an operation.</span></span> <span data-ttu-id="eb7fc-107">此方法属于**ATP**业务服务。</span><span class="sxs-lookup"><span data-stu-id="eb7fc-107">This method belongs to the **ATP** business service.</span></span>  
  
 <span data-ttu-id="eb7fc-108">某些条件[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]时使用 Siebel 业务服务有一定：</span><span class="sxs-lookup"><span data-stu-id="eb7fc-108">Certain conditions that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] imposes while using the Siebel business services:</span></span>  
  
-   <span data-ttu-id="eb7fc-109">如果 Siebel 业务服务方法所采用的没有指定的数据类型的参数，该适配器将作为文本公开自变量。</span><span class="sxs-lookup"><span data-stu-id="eb7fc-109">If a Siebel business service method takes an argument that does not have the data type specified, the adapter exposes the argument as TEXT.</span></span>  
  
-   <span data-ttu-id="eb7fc-110">Siebel 业务服务方法参数可以是以下类型：</span><span class="sxs-lookup"><span data-stu-id="eb7fc-110">A Siebel business service method argument can be of the following types:</span></span>  
  
    -   <span data-ttu-id="eb7fc-111">字符串 （作为 xsd: string 公开）</span><span class="sxs-lookup"><span data-stu-id="eb7fc-111">String (exposed as xsd:string)</span></span>  
  
    -   <span data-ttu-id="eb7fc-112">数 (公开为 xsd： 十进制)</span><span class="sxs-lookup"><span data-stu-id="eb7fc-112">Number (exposed as xsd: decimal)</span></span>  
  
    -   <span data-ttu-id="eb7fc-113">日期 （时间部分必须设置为 00:00:00 的化，使用模式方面，该值指示作为公开）</span><span class="sxs-lookup"><span data-stu-id="eb7fc-113">Date (exposed as xsd:DateTime, with pattern facet indicating that time part must be set to 00:00:00)</span></span>  
  
    -   <span data-ttu-id="eb7fc-114">层次结构 （公开为 xsd: string）</span><span class="sxs-lookup"><span data-stu-id="eb7fc-114">Hierarchy (exposed as xsd:string)</span></span>  
  
    -   <span data-ttu-id="eb7fc-115">集成对象 （作为 xsd: string 公开）</span><span class="sxs-lookup"><span data-stu-id="eb7fc-115">Integration Object (exposed as xsd:string)</span></span>  
  
     <span data-ttu-id="eb7fc-116">此外，业务服务方法验证传递给自变量的值是否符合相应的类型。</span><span class="sxs-lookup"><span data-stu-id="eb7fc-116">Also, the business service method verifies whether the value passed for an argument complies with the corresponding type.</span></span> <span data-ttu-id="eb7fc-117">因此，如果业务服务方法接受或返回不符合相应的自变量类型的值，该适配器可能会引发异常。</span><span class="sxs-lookup"><span data-stu-id="eb7fc-117">So, if a business service method accepts or returns values that do not comply with the corresponding argument type, the adapter may throw an exception.</span></span> <span data-ttu-id="eb7fc-118">如果在调用业务服务方法，该适配器未成功，则可能会失败的架构验证。</span><span class="sxs-lookup"><span data-stu-id="eb7fc-118">If the adapter does succeed in invoking the business service method, the schema validation may fail.</span></span>  
  
 <span data-ttu-id="eb7fc-119">有关的信息：</span><span class="sxs-lookup"><span data-stu-id="eb7fc-119">For information about:</span></span>  
  
-   <span data-ttu-id="eb7fc-120">执行对使用 BizTalk Server 业务服务的操作，请参阅[调用业务服务方法使用 BizTalk Server 和 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="eb7fc-120">Performing operations on business services using BizTalk Server, see [Invoke Business Service Methods Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span></span>  
  
-   <span data-ttu-id="eb7fc-121">消息结构和 SOAP 操作对业务服务执行操作，请参阅[业务服务操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md))。</span><span class="sxs-lookup"><span data-stu-id="eb7fc-121">Message structures and SOAP actions to perform operations on business services, see [Message Schemas for Business Service Operations](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb7fc-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb7fc-122">See Also</span></span>  
 [<span data-ttu-id="eb7fc-123">连接到 SAP 系统使用适配器</span><span class="sxs-lookup"><span data-stu-id="eb7fc-123">Connect to an SAP system using the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)