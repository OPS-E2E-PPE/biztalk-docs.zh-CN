---
title: 使用 WCF LOB 适配器 SDK 时选择的 URI 方案和寻址的格式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3bb4feee-3d39-43ca-82ac-aba38c13bc69
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b8a9e9ffd78e0740dd366f4f09d3a832e74cda94
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005766"
---
# <a name="select-a-uri-scheme-and-addressing-format-when-using-the-wcf-lob-adapter-sdk"></a><span data-ttu-id="5e415-102">使用 WCF LOB 适配器 SDK 时选择的 URI 方案和寻址的格式</span><span class="sxs-lookup"><span data-stu-id="5e415-102">Select a URI scheme and addressing format when using the WCF LOB Adapter SDK</span></span>
<span data-ttu-id="5e415-103">统一资源标识符 (URI) 唯一标识资源类似于 Web 服务，或在开发适配器的情况下[!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)]，若要连接到的系统，以及要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="5e415-103">A Uniform Resource Identifier (URI) uniquely identifies resources like a Web service or, in the case of an adapter developed with the [!INCLUDE[afproductnameshort](../../includes/afproductnameshort-md.md)], the system to connect to as well as the action to perform.</span></span> <span data-ttu-id="5e415-104">本部分提供有关如何构造一个 URI 来唯一地描述终结点地址和您的适配器的操作的建议。</span><span class="sxs-lookup"><span data-stu-id="5e415-104">This section provides a recommendation on how to construct a URI to uniquely describe the endpoint address and the action for your adapter.</span></span>  
  
## <a name="anatomy-of-a-uri"></a><span data-ttu-id="5e415-105">一个 URI 的剖析</span><span class="sxs-lookup"><span data-stu-id="5e415-105">Anatomy of a URI</span></span>  
 <span data-ttu-id="5e415-106">URI 由以下三个组件组成：</span><span class="sxs-lookup"><span data-stu-id="5e415-106">A URI consists of the following three components:</span></span>  
  
- <span data-ttu-id="5e415-107">**方案名称**是潜在客户部分的 URI 字符串，而是第一个级别的命名结构; 示例包括 http、 urn 和 contoso。</span><span class="sxs-lookup"><span data-stu-id="5e415-107">**Scheme name** is the lead part of the URI string and is the first level of the naming structure; examples include http, urn, and contoso.</span></span>  
  
- <span data-ttu-id="5e415-108">**层次结构部分**包含，通常具有层次结构可以包含可选的颁发机构、 主机名和端口信息的信息。</span><span class="sxs-lookup"><span data-stu-id="5e415-108">**Hierarchical part** consists of information that is usually hierarchical and can contain optional authority, hostname, and port information.</span></span> <span data-ttu-id="5e415-109">示例包括 www.microsoft.com 和 UserName =User@microsoft.com:4099。</span><span class="sxs-lookup"><span data-stu-id="5e415-109">Examples include www.microsoft.com and UserName=User@microsoft.com:4099.</span></span>  
  
- <span data-ttu-id="5e415-110">**查询**包含可选信息用问号 （？） 标记，并且通常分组为键/值对分隔与号 (&)。</span><span class="sxs-lookup"><span data-stu-id="5e415-110">**Query** contains optional information marked with a question mark (?) and typically grouped as key/value pairs separated by an ampersand (&).</span></span> <span data-ttu-id="5e415-111">例如，contoso://microsoft.com/functions?name=Find。</span><span class="sxs-lookup"><span data-stu-id="5e415-111">For example, contoso://microsoft.com/functions?name=Find.</span></span>  
  
- <span data-ttu-id="5e415-112">**片段**用来存储可能需要的适配器的额外标识信息。</span><span class="sxs-lookup"><span data-stu-id="5e415-112">**Fragment** is used to store extra identifying information that may be needed by the adapter.</span></span> <span data-ttu-id="5e415-113">片段分隔哈希 (）;例如，contoso://microsoft.com/functions?name=Find#public。</span><span class="sxs-lookup"><span data-stu-id="5e415-113">The fragment is separated by a hash (#); for example, contoso://microsoft.com/functions?name=Find#public.</span></span>  
  
  <span data-ttu-id="5e415-114">您可能不会使用所有的 URI 语法所提供的功能。</span><span class="sxs-lookup"><span data-stu-id="5e415-114">You might not use all of the features provided by the URI syntax.</span></span>  
  
## <a name="designing-the-uri"></a><span data-ttu-id="5e415-115">设计 URI</span><span class="sxs-lookup"><span data-stu-id="5e415-115">Designing the URI</span></span>  
 <span data-ttu-id="5e415-116">作为适配器开发人员，您需要设计您的目标业务线系统的相应 URI。</span><span class="sxs-lookup"><span data-stu-id="5e415-116">As an adapter developer, you will have to devise an appropriate URI for your target line-of-business system.</span></span> <span data-ttu-id="5e415-117">在设计你的 URI 时，务必使其唯一且有意义。</span><span class="sxs-lookup"><span data-stu-id="5e415-117">When designing your URI, it is important to make it unique and meaningful.</span></span>  
  
 <span data-ttu-id="5e415-118">一个唯一的 URI 是指不与现有组织内以及跨其他业务领域的 Uri 和 Internet 冲突。</span><span class="sxs-lookup"><span data-stu-id="5e415-118">A unique URI is one that does not conflict with existing URIs within an organization and across other businesses and the Internet.</span></span> <span data-ttu-id="5e415-119">例如，选择一个方案名称，如"http"或"afs"可能当前识别或已在广泛的使用可能会导致连接或操作问题由于可能会将请求路由到不同的系统，而不适用于您的适配器。</span><span class="sxs-lookup"><span data-stu-id="5e415-119">For example, choosing a scheme name like "http" or "afs" that may be currently recognized or already in wide use could cause connection or operational problems because requests might be routed to a different system and not to your adapter.</span></span>  
  
 <span data-ttu-id="5e415-120">URI 设计的另一个重要方面，使有意义向开发人员受众将使用您的适配器。</span><span class="sxs-lookup"><span data-stu-id="5e415-120">Another important aspect of URI design is making it meaningful to the developer audience who will be consuming your adapter.</span></span> <span data-ttu-id="5e415-121">例如，如果你正在编写一个适配器的医疗索赔处理系统，您可以设计包含公司名称、 处理系统名称和系统版本的目标声明的 URI 方案： northwind.contoso.cps.v1.0://。</span><span class="sxs-lookup"><span data-stu-id="5e415-121">For example, if you are writing an adapter for a medical claims processing system, you could design a URI scheme that includes your company name, the target claims processing system name, and system version: northwind.contoso.cps.v1.0://.</span></span>  
  
## <a name="connecting-to-the-target-system"></a><span data-ttu-id="5e415-122">连接到目标系统</span><span class="sxs-lookup"><span data-stu-id="5e415-122">Connecting to the Target System</span></span>  
 <span data-ttu-id="5e415-123">连接字符串有以下语法：</span><span class="sxs-lookup"><span data-stu-id="5e415-123">Connection strings have the following syntax:</span></span>  
  
 <span data-ttu-id="5e415-124">**\<方案\>: //[userinfo"\@"]\<LOB 连接字符串\>**</span><span class="sxs-lookup"><span data-stu-id="5e415-124">**\<scheme\>://[userinfo "\@"]\<LOB Connection String\>**</span></span>  
  
 <span data-ttu-id="5e415-125">例如，你可以连接到 contoso 目录订购系统 （业务线应用程序的示例行） 使用以下：</span><span class="sxs-lookup"><span data-stu-id="5e415-125">For example, you could connect to the contoso catalog ordering system (a sample line of business application) using the following:</span></span>  
  
 <span data-ttu-id="5e415-126">**northwind.contoso.v1.0://\<servername\>？目录 Contoso 和集成的安全性 = = True**</span><span class="sxs-lookup"><span data-stu-id="5e415-126">**northwind.contoso.v1.0://\<servername\>?Catalog=Contoso&Integrated Security=True**</span></span>  
  
 <span data-ttu-id="5e415-127">您还可以提供可选的颁发机构信息中包括用户名和密码以及其他重要的凭据的 URI。</span><span class="sxs-lookup"><span data-stu-id="5e415-127">You can also provide optional authority information in the URI including user name and password and other important credentials.</span></span> <span data-ttu-id="5e415-128">但是，这可能会造成安全风险。</span><span class="sxs-lookup"><span data-stu-id="5e415-128">However, this can present a security risk.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="5e415-129">不要在 URI 中传递用户凭据和其他敏感信息。</span><span class="sxs-lookup"><span data-stu-id="5e415-129">Do not pass user credentials and other sensitive information in the URI.</span></span> <span data-ttu-id="5e415-130">可以截获和未经授权的用户查看此信息。</span><span class="sxs-lookup"><span data-stu-id="5e415-130">This information could be intercepted and viewed by unauthorized users.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e415-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e415-131">See Also</span></span>  
 [<span data-ttu-id="5e415-132">规划和设计适配器使用 WCF LOB 适配器 SDK</span><span class="sxs-lookup"><span data-stu-id="5e415-132">Plan and design an adapter using the WCF LOB Adapter SDK</span></span>](../../adapters-and-accelerators/wcf-lob-adapter-sdk/plan-and-design-an-adapter-using-the-wcf-lob-adapter-sdk.md)