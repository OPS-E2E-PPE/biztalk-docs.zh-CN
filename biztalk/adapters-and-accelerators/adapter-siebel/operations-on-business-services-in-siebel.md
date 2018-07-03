---
title: 在 Siebel 业务服务上的操作 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- operations, on business services
- business services, operations on
ms.assetid: 29a1a88c-8c7b-46f1-8faf-49ddd32ba2f0
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df24fa8ee0bd51ddf919e5f88a47ceae9d0743fa
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001366"
---
# <a name="operations-on-business-services-in-siebel"></a><span data-ttu-id="7fefd-102">在 Siebel 业务服务上的操作</span><span class="sxs-lookup"><span data-stu-id="7fefd-102">Operations on Business Services in Siebel</span></span>
<span data-ttu-id="7fefd-103">Siebel 业务服务是一系列可以在 Siebel 中直接调用的业务方法。</span><span class="sxs-lookup"><span data-stu-id="7fefd-103">A Siebel business service is a collection of business methods that can be directly invoked in Siebel.</span></span> <span data-ttu-id="7fefd-104">业务组件和业务对象是关联到特定的数据和 Siebel 中的表，而业务服务调用的对象执行特定任务。</span><span class="sxs-lookup"><span data-stu-id="7fefd-104">Whereas business components and business objects are associated to specific data and tables in Siebel, business services invoke the objects to perform specific tasks.</span></span>  
  
 <span data-ttu-id="7fefd-105">[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]呈现业务服务方法，如操作名称，并支持 IN，OUT 和 INOUT 参数。</span><span class="sxs-lookup"><span data-stu-id="7fefd-105">The [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the business service methods as operation names and supports IN, OUT, and INOUT parameters.</span></span> <span data-ttu-id="7fefd-106">例如，[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]图面**ATPRunCheck**作为操作的方法。</span><span class="sxs-lookup"><span data-stu-id="7fefd-106">For example, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] surfaces the **ATPRunCheck** method as an operation.</span></span> <span data-ttu-id="7fefd-107">此方法属于**ATP**业务服务。</span><span class="sxs-lookup"><span data-stu-id="7fefd-107">This method belongs to the **ATP** business service.</span></span>  
  
 <span data-ttu-id="7fefd-108">某些条件的[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]时使用的 Siebel 业务服务施加了：</span><span class="sxs-lookup"><span data-stu-id="7fefd-108">Certain conditions that the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] imposes while using the Siebel business services:</span></span>  
  
- <span data-ttu-id="7fefd-109">如果 Siebel 业务服务方法不具有指定的数据类型的参数，该适配器以文本形式公开参数。</span><span class="sxs-lookup"><span data-stu-id="7fefd-109">If a Siebel business service method takes an argument that does not have the data type specified, the adapter exposes the argument as TEXT.</span></span>  
  
- <span data-ttu-id="7fefd-110">Siebel 业务服务方法参数可以是以下类型之一：</span><span class="sxs-lookup"><span data-stu-id="7fefd-110">A Siebel business service method argument can be of the following types:</span></span>  
  
  - <span data-ttu-id="7fefd-111">字符串 （公开为 xsd: string）</span><span class="sxs-lookup"><span data-stu-id="7fefd-111">String (exposed as xsd:string)</span></span>  
  
  - <span data-ttu-id="7fefd-112">数字 (公开为 xsd: decimal)</span><span class="sxs-lookup"><span data-stu-id="7fefd-112">Number (exposed as xsd: decimal)</span></span>  
  
  - <span data-ttu-id="7fefd-113">日期 （时间部分必须设置为 00:00:00 化，使用模式方面，该值指示作为公开）</span><span class="sxs-lookup"><span data-stu-id="7fefd-113">Date (exposed as xsd:DateTime, with pattern facet indicating that time part must be set to 00:00:00)</span></span>  
  
  - <span data-ttu-id="7fefd-114">层次结构 （公开为 xsd: string）</span><span class="sxs-lookup"><span data-stu-id="7fefd-114">Hierarchy (exposed as xsd:string)</span></span>  
  
  - <span data-ttu-id="7fefd-115">集成对象 （公开为 xsd: string）</span><span class="sxs-lookup"><span data-stu-id="7fefd-115">Integration Object (exposed as xsd:string)</span></span>  
  
    <span data-ttu-id="7fefd-116">此外，业务服务方法验证传递的参数的值是否符合相应的类型。</span><span class="sxs-lookup"><span data-stu-id="7fefd-116">Also, the business service method verifies whether the value passed for an argument complies with the corresponding type.</span></span> <span data-ttu-id="7fefd-117">因此，如果业务服务方法接受或返回不符合相应的参数类型的值，该适配器可能会引发异常。</span><span class="sxs-lookup"><span data-stu-id="7fefd-117">So, if a business service method accepts or returns values that do not comply with the corresponding argument type, the adapter may throw an exception.</span></span> <span data-ttu-id="7fefd-118">如果适配器未成功调用业务服务方法中，架构验证可能会失败。</span><span class="sxs-lookup"><span data-stu-id="7fefd-118">If the adapter does succeed in invoking the business service method, the schema validation may fail.</span></span>  
  
  <span data-ttu-id="7fefd-119">有关信息：</span><span class="sxs-lookup"><span data-stu-id="7fefd-119">For information about:</span></span>  
  
- <span data-ttu-id="7fefd-120">在执行业务服务使用 BizTalk Server 上的操作，请参阅[调用业务服务方法使用 BizTalk Server 和 Siebel 适配器](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="7fefd-120">Performing operations on business services using BizTalk Server, see [Invoke Business Service Methods Using BizTalk Server and the Siebel adapter](../../adapters-and-accelerators/adapter-siebel/invoke-business-service-methods-using-biztalk-server-and-the-siebel-adapter.md).</span></span>  
  
- <span data-ttu-id="7fefd-121">消息结构和 SOAP 操作对业务服务执行操作，请参阅[业务服务操作的消息架构](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md))。</span><span class="sxs-lookup"><span data-stu-id="7fefd-121">Message structures and SOAP actions to perform operations on business services, see [Message Schemas for Business Service Operations](../../adapters-and-accelerators/adapter-siebel/message-schemas-for-business-service-operations.md)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fefd-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="7fefd-122">See Also</span></span>  
 [<span data-ttu-id="7fefd-123">连接到 SAP 系统使用的适配器</span><span class="sxs-lookup"><span data-stu-id="7fefd-123">Connect to an SAP system using the adapter</span></span>](../../adapters-and-accelerators/adapter-sap/connect-to-an-sap-system-using-the-adapter.md)