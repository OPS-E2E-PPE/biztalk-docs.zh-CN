---
title: 规划发布 Web Services2 |Microsoft Docs
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
ms.openlocfilehash: 1223dbb434df74728b3f7fe9b21dcecdc5378ba9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65395672"
---
# <a name="planning-for-publishing-web-services"></a><span data-ttu-id="c555c-102">规划发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="c555c-102">Planning for Publishing Web Services</span></span>
<span data-ttu-id="c555c-103">您可以从您的业务流程访问 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="c555c-103">You can access Web services from your orchestrations.</span></span> <span data-ttu-id="c555c-104">此外可以使用 BizTalk Web Services 发布向导发布 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="c555c-104">You can also use the BizTalk Web Services Publishing Wizard to publish your Web service.</span></span>  
  
 <span data-ttu-id="c555c-105">下表列出了一些需要进行 Web 服务时规划回答的问题。</span><span class="sxs-lookup"><span data-stu-id="c555c-105">The following table lists some of the questions that you need to answer in planning for Web services.</span></span>  
  
|<span data-ttu-id="c555c-106">规划问题</span><span class="sxs-lookup"><span data-stu-id="c555c-106">Planning question</span></span>|<span data-ttu-id="c555c-107">建议</span><span class="sxs-lookup"><span data-stu-id="c555c-107">Recommendation</span></span>|  
|-----------------------|--------------------|  
|<span data-ttu-id="c555c-108">已生成了 BizTalk Server 项目？</span><span class="sxs-lookup"><span data-stu-id="c555c-108">Have you built your BizTalk Server project?</span></span>|<span data-ttu-id="c555c-109">必须构建 BizTalk Server 项目在运行 BizTalk Web Services 发布向导之前。</span><span class="sxs-lookup"><span data-stu-id="c555c-109">You must build your BizTalk Server project prior to running the BizTalk Web Services Publishing Wizard.</span></span>|  
|<span data-ttu-id="c555c-110">已启用好系统以运行 Web 服务？</span><span class="sxs-lookup"><span data-stu-id="c555c-110">Have you enabled your system to run Web services?</span></span>|<span data-ttu-id="c555c-111">运行 BizTalk Web Services 发布向导之前，必须在计算机上启用 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="c555c-111">You must enable Web services on your computer before running the BizTalk Web Services Publishing Wizard.</span></span> <span data-ttu-id="c555c-112">有关启用 Web 服务系统的详细信息，请参阅[启用 Web 服务](../core/enabling-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="c555c-112">For more information about enabling your system for Web services, see [Enabling Web Services](../core/enabling-web-services.md).</span></span>|  
|<span data-ttu-id="c555c-113">已验证您的架构包含仅有效的 XML 字符和元素？</span><span class="sxs-lookup"><span data-stu-id="c555c-113">Have you verified that your schema contains only valid XML characters and elements?</span></span>|<span data-ttu-id="c555c-114">Web 服务不支持中文、 日语或 Korean (CJK) Unified Ideograph Extension A 字符。</span><span class="sxs-lookup"><span data-stu-id="c555c-114">Web services do not support Chinese, Japanese, or Korean (CJK) Unified Ideograph Extension A characters.</span></span> <span data-ttu-id="c555c-115">也有对某些 XML 架构 (XSD) 元素的限制。</span><span class="sxs-lookup"><span data-stu-id="c555c-115">There are also restrictions on certain XML Schema (XSD) elements.</span></span> <span data-ttu-id="c555c-116">有关有效的 XML 字符和受支持的元素和元素的注意事项的详细信息，请参阅[注意事项时发布 Web Services](../core/considerations-when-publishing-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="c555c-116">For more information about valid XML characters and supported elements and considerations for elements, see [Considerations When Publishing Web Services](../core/considerations-when-publishing-web-services.md).</span></span>|  
|<span data-ttu-id="c555c-117">任何在 BizTalk Server 项目中的消息类型是否使用用户定义的.NET 类？</span><span class="sxs-lookup"><span data-stu-id="c555c-117">Do any of the message types in your BizTalk Server project use user-defined .NET classes?</span></span>|<span data-ttu-id="c555c-118">必须安装包含用户定义的.NET 类在全局程序集缓存 (GAC) 中的消息类型引用的程序集。</span><span class="sxs-lookup"><span data-stu-id="c555c-118">You must install assemblies containing user-defined .NET classes that message types reference in the global assembly cache (GAC).</span></span>|  
|<span data-ttu-id="c555c-119">Web 客户端使用的提供的凭据**WindowsUser**上下文属性？</span><span class="sxs-lookup"><span data-stu-id="c555c-119">Do your Web clients use the supplied credentials for the **WindowsUser** context property?</span></span>|<span data-ttu-id="c555c-120">使用已发布的 Web 服务使用的 Web 客户端提供的凭据**WindowsUser**上下文属性。</span><span class="sxs-lookup"><span data-stu-id="c555c-120">The credentials supplied by the Web clients consuming a published Web service use the **WindowsUser** context property.</span></span> <span data-ttu-id="c555c-121">参与方解析使用此属性。</span><span class="sxs-lookup"><span data-stu-id="c555c-121">Party Resolution uses this property.</span></span> <span data-ttu-id="c555c-122">如果使用您设置了参与方**WindowsUser**上下文属性和 Web 客户端使用 Web 服务使用与匹配参与方的凭据、 BizTalk Server 将消息标识为来自对应的预定义参与方。</span><span class="sxs-lookup"><span data-stu-id="c555c-122">If you set up a Party using the **WindowsUser** context property and the Web client consumes the Web service with credentials that match the Party, BizTalk Server identifies the message as coming from the corresponding predefined party.</span></span> <span data-ttu-id="c555c-123">有关参与方解析管道组件的详细信息，请参阅[参与方解析管道组件](../core/party-resolution-pipeline-component.md)。</span><span class="sxs-lookup"><span data-stu-id="c555c-123">For more information about party resolution with pipeline components, see [Party Resolution Pipeline Component](../core/party-resolution-pipeline-component.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c555c-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="c555c-124">See Also</span></span>  
 [<span data-ttu-id="c555c-125">发布 Web 服务</span><span class="sxs-lookup"><span data-stu-id="c555c-125">Publishing Web Services</span></span>](../core/publishing-web-services.md)