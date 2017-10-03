---
title: "使用 WCF LOB 适配器 SDK 时选择的 URI 方案和寻址格式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3bb4feee-3d39-43ca-82ac-aba38c13bc69
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6df8145fac74761fee4aabd34ff01d708b646c12
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="a0e72-102">使用 WCF LOB 适配器 SDK 时选择的 URI 方案和寻址的格式</span><span class="sxs-lookup"><span data-stu-id="a0e72-102">Select a URI scheme and addressing format when using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="a0e72-103">统一资源标识符 (URI) 唯一标识资源与 Web 服务类似，或者如果使用的开发适配器[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，要连接到系统，以及要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="a0e72-103">A Uniform Resource Identifier (URI) uniquely identifies resources like a Web service or, in the case of an adapter developed with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], the system to connect to as well as the action to perform.</span></span> <span data-ttu-id="a0e72-104">本部分提供有关如何构造用于唯一地描述了终结点地址和适配器的操作的 URI 的建议。</span><span class="sxs-lookup"><span data-stu-id="a0e72-104">This section provides a recommendation on how to construct a URI to uniquely describe the endpoint address and the action for your adapter.</span></span>  
  
## <a name="anatomy-of-a-uri"></a><span data-ttu-id="a0e72-105">一个 URI 的剖析</span><span class="sxs-lookup"><span data-stu-id="a0e72-105">Anatomy of a URI</span></span>  
 <span data-ttu-id="a0e72-106">一个 URI 由以下三个组件构成：</span><span class="sxs-lookup"><span data-stu-id="a0e72-106">A URI consists of the following three components:</span></span>  
  
-   <span data-ttu-id="a0e72-107">**方案名称**是 URI 字符串的前导部分，而是命名的结构中; 第一个级别示例包括 http、 urn 和 contoso。</span><span class="sxs-lookup"><span data-stu-id="a0e72-107">**Scheme name** is the lead part of the URI string and is the first level of the naming structure; examples include http, urn, and contoso.</span></span>  
  
-   <span data-ttu-id="a0e72-108">**层次结构部分**包含通常分层，并可以包含可选机构、 主机名和端口信息的信息。</span><span class="sxs-lookup"><span data-stu-id="a0e72-108">**Hierarchical part** consists of information that is usually hierarchical and can contain optional authority, hostname, and port information.</span></span> <span data-ttu-id="a0e72-109">示例包括 www.microsoft.com 和用户名 =User@microsoft.com:4099。</span><span class="sxs-lookup"><span data-stu-id="a0e72-109">Examples include www.microsoft.com and UserName=User@microsoft.com:4099.</span></span>  
  
-   <span data-ttu-id="a0e72-110">**查询**包含用问号 （？） 标记和通常分组为用连字符分隔的键/值对的可选信息 (&)。</span><span class="sxs-lookup"><span data-stu-id="a0e72-110">**Query** contains optional information marked with a question mark (?) and typically grouped as key/value pairs separated by an ampersand (&).</span></span> <span data-ttu-id="a0e72-111">例如，contoso://microsoft.com/functions?name=Find。</span><span class="sxs-lookup"><span data-stu-id="a0e72-111">For example, contoso://microsoft.com/functions?name=Find.</span></span>  
  
-   <span data-ttu-id="a0e72-112">**片段**用于存储可能需要的适配器的额外标识信息。</span><span class="sxs-lookup"><span data-stu-id="a0e72-112">**Fragment** is used to store extra identifying information that may be needed by the adapter.</span></span> <span data-ttu-id="a0e72-113">片段分隔由一个哈希 （#）;例如，contoso://microsoft.com/functions?name=Find#public。</span><span class="sxs-lookup"><span data-stu-id="a0e72-113">The fragment is separated by a hash (#); for example, contoso://microsoft.com/functions?name=Find#public.</span></span>  
  
 <span data-ttu-id="a0e72-114">你可能不会使用所有的 URI 语法所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="a0e72-114">You might not use all of the features provided by the URI syntax.</span></span>  
  
## <a name="designing-the-uri"></a><span data-ttu-id="a0e72-115">设计 URI</span><span class="sxs-lookup"><span data-stu-id="a0e72-115">Designing the URI</span></span>  
 <span data-ttu-id="a0e72-116">作为适配器开发人员，你将需要设计为目标的业务系统的相应 URI。</span><span class="sxs-lookup"><span data-stu-id="a0e72-116">As an adapter developer, you will have to devise an appropriate URI for your target line-of-business system.</span></span> <span data-ttu-id="a0e72-117">在设计时你的 URI，很重要，使其唯一且有意义。</span><span class="sxs-lookup"><span data-stu-id="a0e72-117">When designing your URI, it is important to make it unique and meaningful.</span></span>  
  
 <span data-ttu-id="a0e72-118">一个唯一的 URI 是指不与现有 Uri 在组织内和跨其他业务领域和 Internet 冲突。</span><span class="sxs-lookup"><span data-stu-id="a0e72-118">A unique URI is one that does not conflict with existing URIs within an organization and across other businesses and the Internet.</span></span> <span data-ttu-id="a0e72-119">例如，选择方案名称，例如"http"或"afs"可能当前识别或已在广泛使用可能导致连接或操作问题因为可能会将请求路由到不同系统，而不适用于你的适配器。</span><span class="sxs-lookup"><span data-stu-id="a0e72-119">For example, choosing a scheme name like "http" or "afs" that may be currently recognized or already in wide use could cause connection or operational problems because requests might be routed to a different system and not to your adapter.</span></span>  
  
 <span data-ttu-id="a0e72-120">URI 设计的另一个重要方面它有意义对进行的开发人员受众使用你的适配器。</span><span class="sxs-lookup"><span data-stu-id="a0e72-120">Another important aspect of URI design is making it meaningful to the developer audience who will be consuming your adapter.</span></span> <span data-ttu-id="a0e72-121">例如，如果你正在编写一个适配器，有关医疗声明处理系统，您可以设计包含您公司的名称，处理系统名称和系统版本的目标声明的 URI 方案： northwind.contoso.cps.v1.0://。</span><span class="sxs-lookup"><span data-stu-id="a0e72-121">For example, if you are writing an adapter for a medical claims processing system, you could design a URI scheme that includes your company name, the target claims processing system name, and system version: northwind.contoso.cps.v1.0://.</span></span>  
  
## <a name="connecting-to-the-target-system"></a><span data-ttu-id="a0e72-122">连接到目标系统</span><span class="sxs-lookup"><span data-stu-id="a0e72-122">Connecting to the Target System</span></span>  
 <span data-ttu-id="a0e72-123">连接字符串具有以下语法：</span><span class="sxs-lookup"><span data-stu-id="a0e72-123">Connection strings have the following syntax:</span></span>  
  
 <span data-ttu-id="a0e72-124">**\<方案 >: //[userinfo"@"]\<LOB 连接字符串 >**</span><span class="sxs-lookup"><span data-stu-id="a0e72-124">**\<scheme>://[userinfo "@"]\<LOB Connection String>**</span></span>  
  
 <span data-ttu-id="a0e72-125">例如，你无法连接到 contoso 目录排序系统 （示例业务线应用程序） 使用以下：</span><span class="sxs-lookup"><span data-stu-id="a0e72-125">For example, you could connect to the contoso catalog ordering system (a sample line of business application) using the following:</span></span>  
  
 <span data-ttu-id="a0e72-126">**northwind.contoso.v1.0://\<服务器名称 >？目录 = Contoso 集成的安全性 = True**</span><span class="sxs-lookup"><span data-stu-id="a0e72-126">**northwind.contoso.v1.0://\<servername>?Catalog=Contoso&Integrated Security=True**</span></span>  
  
 <span data-ttu-id="a0e72-127">你还可以提供可选的颁发机构信息中包括用户名和密码以及其他重要的凭据的 URI。</span><span class="sxs-lookup"><span data-stu-id="a0e72-127">You can also provide optional authority information in the URI including user name and password and other important credentials.</span></span> <span data-ttu-id="a0e72-128">但是，这可以存在安全风险。</span><span class="sxs-lookup"><span data-stu-id="a0e72-128">However, this can present a security risk.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="a0e72-129">不要在 URI 中传递用户凭据和其他敏感信息。</span><span class="sxs-lookup"><span data-stu-id="a0e72-129">Do not pass user credentials and other sensitive information in the URI.</span></span> <span data-ttu-id="a0e72-130">此信息可能被截获和未经授权的用户查看。</span><span class="sxs-lookup"><span data-stu-id="a0e72-130">This information could be intercepted and viewed by unauthorized users.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0e72-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0e72-131">See Also</span></span>  
 [<span data-ttu-id="a0e72-132">规划和设计使用 WCF LOB 适配器 SDK 的适配器</span><span class="sxs-lookup"><span data-stu-id="a0e72-132">Plan and design an adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)