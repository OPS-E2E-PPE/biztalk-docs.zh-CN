---
title: 规划发布 Web Services2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, planning
- virtual directories, updating
- BizTalk Server Web Services Publishing Wizard
ms.assetid: 69107557-48e2-4f15-ba42-9fad476a8294
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d0b9d593a3309f7b4477f2fa735f7e265b614c8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264453"
---
# <a name="planning-for-publishing-web-services"></a><span data-ttu-id="36ea9-102">规划发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="36ea9-102">Planning for Publishing Web Services</span></span>
<span data-ttu-id="36ea9-103">您可以从业务流程访问 Web Services，</span><span class="sxs-lookup"><span data-stu-id="36ea9-103">You can access Web services from your orchestrations.</span></span> <span data-ttu-id="36ea9-104">还可以使用 BizTalk Web Services 发布向导发布 Web Services。</span><span class="sxs-lookup"><span data-stu-id="36ea9-104">You can also use the BizTalk Web Services Publishing Wizard to publish your Web service.</span></span>  
  
 <span data-ttu-id="36ea9-105">下表列出了在规划 Web Services 时需要回答的一些问题。</span><span class="sxs-lookup"><span data-stu-id="36ea9-105">The following table lists some of the questions that you need to answer in planning for Web services.</span></span>  
  
|<span data-ttu-id="36ea9-106">规划问题</span><span class="sxs-lookup"><span data-stu-id="36ea9-106">Planning question</span></span>|<span data-ttu-id="36ea9-107">建议</span><span class="sxs-lookup"><span data-stu-id="36ea9-107">Recommendation</span></span>|  
|-----------------------|--------------------|  
|<span data-ttu-id="36ea9-108">是否已构建 BizTalk Server 项目？</span><span class="sxs-lookup"><span data-stu-id="36ea9-108">Have you built your BizTalk Server project?</span></span>|<span data-ttu-id="36ea9-109">请注意，在运行 BizTalk Web Services 发布向导之前，必须构建 BizTalk Server 项目。</span><span class="sxs-lookup"><span data-stu-id="36ea9-109">You must build your BizTalk Server project prior to running the BizTalk Web Services Publishing Wizard.</span></span>|  
|<span data-ttu-id="36ea9-110">是否已将系统配置为可以运行 Web Services？</span><span class="sxs-lookup"><span data-stu-id="36ea9-110">Have you enabled your system to run Web services?</span></span>|<span data-ttu-id="36ea9-111">在运行 BizTalk Web Services 发布向导之前，必须在计算机上启用 Web Services。</span><span class="sxs-lookup"><span data-stu-id="36ea9-111">You must enable Web services on your computer before running the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="36ea9-112">有关启用你的 Web 服务的系统的详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="36ea9-112">For more information about enabling your system for Web services, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>|  
|<span data-ttu-id="36ea9-113">是否已验证架构仅包含有效的 XML 字符和元素？</span><span class="sxs-lookup"><span data-stu-id="36ea9-113">Have you verified that your schema contains only valid XML characters and elements?</span></span>|<span data-ttu-id="36ea9-114">Web Services 不支持 Chinese、Japanese 或 Korean (CJK) Unified Ideograph Extension A 字符。</span><span class="sxs-lookup"><span data-stu-id="36ea9-114">Web services do not support Chinese, Japanese, or Korean (CJK) Unified Ideograph Extension A characters.</span></span> <span data-ttu-id="36ea9-115">同时，某些 XML 架构 (XSD) 元素也存在一定限制。</span><span class="sxs-lookup"><span data-stu-id="36ea9-115">There are also restrictions on certain XML Schema (XSD) elements.</span></span> <span data-ttu-id="36ea9-116">有关有效的 XML 字符和受支持的元素和注意事项的元素的详细信息，请参阅[注意事项发布 Web 服务时](../core/considerations-when-publishing-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="36ea9-116">For more information about valid XML characters and supported elements and considerations for elements, see [Considerations When Publishing Web Services](../core/considerations-when-publishing-web-services.md).</span></span>|  
|<span data-ttu-id="36ea9-117">BizTalk Server 项目中的任一消息类型是否使用用户定义的 .NET 类？</span><span class="sxs-lookup"><span data-stu-id="36ea9-117">Do any of the message types in your BizTalk Server project use user-defined .NET classes?</span></span>|<span data-ttu-id="36ea9-118">您必须在全局程序集缓存 (GAC) 中安装包含可供消息类型引用的用户定义的 .NET 类的程序集。</span><span class="sxs-lookup"><span data-stu-id="36ea9-118">You must install assemblies containing user-defined .NET classes that message types reference in the global assembly cache (GAC).</span></span>|  
|<span data-ttu-id="36ea9-119">执行 Web 客户端使用的提供的凭据**WindowsUser**上下文属性？</span><span class="sxs-lookup"><span data-stu-id="36ea9-119">Do your Web clients use the supplied credentials for the **WindowsUser** context property?</span></span>|<span data-ttu-id="36ea9-120">通过使用已发布的 Web 服务使用的 Web 客户端提供的凭据**WindowsUser**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="36ea9-120">The credentials supplied by the Web clients consuming a published Web service use the **WindowsUser** context property.</span></span> <span data-ttu-id="36ea9-121">参与方解析也可使用此属性。</span><span class="sxs-lookup"><span data-stu-id="36ea9-121">Party Resolution uses this property.</span></span> <span data-ttu-id="36ea9-122">如果你设置了方使用**WindowsUser**上下文属性和 Web 客户端使用具有匹配方的凭据的 Web 服务、 BizTalk Server 标识作为来自相应的预定义方的消息。</span><span class="sxs-lookup"><span data-stu-id="36ea9-122">If you set up a Party using the **WindowsUser** context property and the Web client consumes the Web service with credentials that match the Party, BizTalk Server identifies the message as coming from the corresponding predefined party.</span></span> <span data-ttu-id="36ea9-123">有关与管道组件的参与方解析的详细信息，请参阅[方解析管道组件](../core/party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="36ea9-123">For more information about party resolution with pipeline components, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36ea9-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="36ea9-124">See Also</span></span>  
 [<span data-ttu-id="36ea9-125">发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="36ea9-125">Publishing Web Services</span></span>](../core/publishing-web-services.md)